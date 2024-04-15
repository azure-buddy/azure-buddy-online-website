---
title: "How to host your own Retro Arcade Game Pac-Man with ACI and CosmosDB"
date: 2024-04-14
draft: false
description: "Short example to experiment in an entertaining way ACI and Cosmos DB  during holidays like Easter."
slug: "intro-aci-cosmosdb"
tags: ["tips", "tricks", "ACI", "CosmosDB", "Introduction", "PacMan", "NodeJS", "Containers", "Development", "Bicep" ]
authors:
  - "avwsolutions"
---

# Introduction

Easter is always fun with family time and telling stories. Yesterday I was explaining to my youngest about classic games I do like, better known as retro arcade games. They shine due their simplicity, no fancy graphics , just for fun! Who didn’t go to the arcade halls these old days, spending their last pennies.

To show them such a classic we watched the movie Pac-Man together. After this I got inspired to host my own Pac-Man game, play together and write this blog to share the tip and tricks how to set this up with Azure Container Instances (ACI) and Azure Cosmos DB (CDB).

{{< alert >}}
Enjoy reading and you can always share your **high score** with `AzureBuddy` on Social Media like LinkedIn!
{{< /alert >}}


# Running container workloads with ACI

When multiple containers or dependencies are involved you may want to go for AKS, but running a simple `Node.JS` app you may want to look at Azure Container Instances, in short ACI. One of the biggest advantages is that you don't have to manage the container orchestration tool like with AKS. All management of the orchestration platform and underlying instances is done by the Azure team. Next to that you don't pay for the instance capacity, but solely for the resources the container image is consuming. In this use case a very good and easy fit for hosting my **Pac-Man** `Node.JS` app.

Let's start with our experiment!

For convenience I have created a repository with all the sample material during this blog. This repository contains my saved ARM templates and other reference material. We will use Bicep to deploy the services, but for this I have chosen to convert the ARM templates (aka JSON style) to Bicep syntax. 
This can be done using the following command.

```
 az bicep decompile --file template.json
```

This creates a **template.json** which we have to fix a minor thing to support **float** values. This can be fixed by replacing *'float(memory)'* for *'json(memory)'*.
More can be found on this [Github Issue 1386](https://github.com/Azure/bicep/issues/1386), which is the feature request for Bicep to natively support float values.

Adjust the **parameters.json** for your needs and we are ready to deploy our container.

```
az deployment group create --resource-group 'my-playground-sandbox' --template-file template_custom.bicep --parameters '@parameters.json'
```

Now let’s open the newly started service FQDN (found under Essentials) in a browser and open a session to port 8080. You will see the actual game  Pac-Man loading ...

![Pac-Man loading...](img/initial-screen.png "Pac-Man loading...")

If you see this screen you now have  succesfully deployed the **Pac-Man** `Node.JS` app as ACI workload, but how is persistency arranged? Let's look further how to ensure our high scores are stored in a persistent way and don't get lost. To implement this we are going to use an Azure Cosmos DB. More specific we are going to look at *MongoDB* compatible engine. How to set up this service is described in the section below. 

You may already have seen errors in the container logs? If not, just try the command below to look for  *MongoDB connection failures*.

```
az container logs --resource-group my-playground-sandbox --name pacman-aci-demo
```

For now, start a new game to enjoy stateless Pac-Man.

# Running MongoDB databases with CosmosDB

As may have noticed, the high scores are not saved yet, since there is no persistency in the backend. In the logging we already learned about a required MongoDB. This is what we can deploy with Azure Cosmos DB for MongoDB account. We wil use the classic Requst Units (RU) based implementation.

Also here we are going to create a template within the Azure portal and convert this using the `az bicep decompile` command.

This creates a *template.bicep* which seems to work well, but notice the warnings that are displayed.

Adjust the **parameters.json** for your needs and we are ready to deploy our Azure Cosmos DB account. Take notice that `pacman` can already be taken as account name.

```
az deployment group create --resource-group 'my-playground-sandbox' --template-file template_custom.bicep --parameters '@parameters.json'
```

After the acccount is created we also need to create a **Cosmos DB Container**, which is the actual a **Database**. Within that **Database** we create a new **Collection**, which is actually the data collection in *MongoDB* where the documents are stored.

The only thing we have to keep in mind is that **Cosmos DB** is *MongoDB Compatible*, but does have some specific requirements. 
More information can be found [here](https://learn.microsoft.com/en-us/azure/cosmos-db/mongodb/introduction). An example is that **Cosmos DB** requires the field a query requests a sort on to be indexed. If this is not the case, *sort* will fail with *error=2*. Read more about these common errors and solutions [here](https://learn.microsoft.com/en-us/azure/cosmos-db/mongodb/error-codes-solutions). That's why we have created [idx.json](https://github.com/azure-buddy/intro-pacman-aci-cosmosdb/blob/main/README.md).

Below an example of such `idx.json` file

```
[
    {
        "key": {
            "keys": [
                "_id"
            ]
        },
        "options": null
    },
    {
        "key": {
            "keys": [
                "score"
            ]
        },
        "options": null
    }
]
```
Now it's time to create the **Database** and the **Collection** with an defined index as shown above.

Creation of these resouces can be easily done using the Azure portal or the Command below.

```
az cosmosdb mongodb collection create --account-name pacman --name highscore --database-name highscore --idx '@idx.json' --resource-group my-playground-sandbox
```

After approx 2 minutes the creation is finished and you may want to browse through the collection, which currently contains no **Documents**.


# Updating ACI Container workload with stateful Scoreboard  

After a succcesfull creation write down the following connection information, which can be found within your newly created `Pacman` account settings,under `Connection strings` which we need to setup the app credentials.

|   Setting  | Value |
| -------- | ------- |
| Host  | pacman.mongo.cosmos.azure.com  |
| Port  | 10255 |
| Database | highscore |
| Username | pacman |
| Password | MySecret |

Now that we can this info we can start adjusting our ACI deployment. This can be done by updating our current deployment, but we have some challenges here to not store our *MONGO_AUTH_PWD* in plain text. To ensure we can set an environment variable (using a *.env file*) when doing the deployment. Unfortenately JSON parameter files don't support this, so we are going to convert our `parameters_DB.json` to *Bicepparam* format.

First things first, let's update the `template_custom.bicep` with the following information. Below an example code snippet to start extending your bicep code with some additional parameters. 
Do you notice the difference between *value* and *secureValue* ? Indeed that's why we added *secure()* to ensure string masking.

```
secure()
param environmentVariable0 string
param environmentVariable1 string

environmentVariables: [
  {
    name: 'MONGO_AUTH_PWD'
    secureValue: environmentVariable0
  }
  {
    name: 'MONGO_SERVICE_HOST'
    value: environmentVariable1
  }
]
```

Now complete this `environmentVariables` array with the table below.

| Variable  | Value |
| -------- | ------- |
| MONGO_SERVICE_HOST  | pacman.mongo.cosmos.azure.com  |
| MY_MONGO_PORT  | 10255 |
| MONGO_DATABASE | highscore |
| MONGO_AUTH_USER | pacman |
| MONGO_AUTH_PWD | null |
| MONGO_USE_SSL | true |
| MONGO_VALIDATE_SSL | false |

Don't forget to update your `parameters.json`, but as mentioned above we have to convert it towards *bicepparam* for environment variable support.
First some examples how to include the environment variables and store the changes in a new file called `parameters_DB.json`.

Adding all values be done using this code snippet.
```
"environmentVariable0": {
  "value": null 
},
"environmentVariable1": {
  "value": "pacman.mongo.cosmos.azure.com"
},
```

Let's give the conversion of our `parameters_DB.json` a try and ensure you have the latest version of the Azure CLI installed.

```
az bicep decompile-params --file parameters_DB.json
```

After running above command a new file called `parameters_DB.bicepparam` is created for us. Great now let's update some settings here.

Replace the `Using ''` to your newly created bicep template with DB parameters set.

```
Using 'template_custom_DB.bicep'
```

Now we are going to update our *environmentVariable0* to be read from an *Environment Variable*.

```
param environmentVariable0 = readEnvironmentVariable('MONGO_AUTH_PWD')
```

Save the file and we are ready to deploy using native Bicep code.

```
source .env
cd arm/deployment-template-aci
az deployment group create --resource-group 'my-playground-sandbox' --template-file template_custom_DB.bicep --parameters parameters_DB.bicepparam
```

Great. First you may want to verify the actual resources are created

```
az resource list  --resource-group my-playground-sandbox --output=table
```






# Conclusion

If you are looking for an easy way of deploying containerized resources you may want to have a look at ACI. It provides a straightforward process and takes away the complexity of managing a full-blown Kubernetes environment. Afaik there are some limitations, but these are mainly related when you are requiring more advanced features such as networking or development integration you may be better off with AKS. During our experiment we still found some limitations, such as pulling container images directly from *quay.io*.  This resulted in container *Waiting* state. 

Hopefully you liked this Tip & tricks how to article, which explains the basics of getting up & running with Azure Container Instances and Azure Cosmos DB. Now it’s time to host and play your own retro arcade game Pac-Man! 

# Interested in the code?

All code samples, including local scripts is available at [Azure Buddy Github](https://github.com/azure-buddy/intro-pacman-aci-cosmosdb).

Contributions or follow-up articles are more than appreciated!