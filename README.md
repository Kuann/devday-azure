# DevDay on Azure

Let deploy your applications in Azure and enjoy It's cool features.


# Tools

You need to install these tools below:

#### 1. Azure CLI

You need `Azure CLI` to interact to your Azure resources:

https://docs.microsoft.com/en-us/cli/azure/install-azure-cli?view=azure-cli-latest

#### 2. kubectl

You need `kubectl` to interact to Kubernetes service on Azure:

https://kubernetes.io/docs/tasks/tools/install-kubectl

#### 3. psql

You need `psql` to interact to Postgres database server that you will create. Note: you don't need to have a full Postgres database in your machine.

https://www.compose.com/articles/postgresql-tips-installing-the-postgresql-client/

# Contents

#### 1. Azure resource group:

An Azure resource group is simply a group of resources, in which Azure resources (Database servers, Kubernetes clusters, virtual machines... ) are deployed and managed.

Today, you have to create only 1 resource group that wraps all your resources. Please name it `teamname-rs`. Because there are 2 teams working on a same Azure account.

https://portal.azure.com/#blade/HubsExtension/BrowseResourceGroups

#### 2. Postgres database on Azure:

You need a database for your application. Let create 1 database server:

https://portal.azure.com/#blade/HubsExtension/BrowseResourceBlade/resourceType/Microsoft.DBforPostgreSQL%2Fservers

Now, create a database. `psql` can be used in this case.

Note:

By default, database servers created are not accessible for other services and the Internet so you need to find a way to re-config it's firewall to open access.

Install necessary extensions for you database if any.


#### 3. Dockerize your application:

https://spring.io/guides/gs/spring-boot-docker/

https://docs.microsoft.com/en-us/azure/aks/tutorial-kubernetes-prepare-app

#### 4. Create Azure Container Registry:

Your private registry for storing your container images.

https://docs.microsoft.com/en-us/azure/aks/tutorial-kubernetes-prepare-acr

#### 5. Create a Kubernetes cluster:

https://docs.microsoft.com/en-us/azure/aks/tutorial-kubernetes-deploy-cluster

#### 6. Deploy your image:

https://docs.microsoft.com/en-us/azure/aks/tutorial-kubernetes-deploy-application

After this step, you should be able to access your application from the Internet via a public ip. But when your deployment changes, Does your app ip remain the same? 

Find a way to reserve a static ip in Azure and assign it to you application on Kubernetes.

#### 7. Customize environment variables:

You might have a need to customize you containers for different environments (Dev, Test, Staging, Production).

There are many things you can consider to parameterize like datasource urls, api keys...

One of the good practices is to use environment variables.

Find ways to override environment variables with Kubernetes.

#### 8. Scaling:

Scaling applications in Kuberneter is much easier than ever!

1. Let run your application in multiple replicas.
2. What if 1 replica fails?
3. Try to make a no-downtime deployment.
4. How to handle in case your cluster runs out of resources?

# Pipeline

Automate your build and release process with Azure DevOps.

Let create one individual project for your team `teamname-devops`. Remember there are 2 teams working on a same account.

Create a `classic editor` job that includes tasks such as `maven` builds, `npm`, `docker` and of course, `Kubernetes` deployments.

https://azure.microsoft.com/en-us/services/devops/

Note: 

# Monitoring

When your application is on cloud. Monitoring is much easier than ever.

Azure offer you many cool features for monitoring your applications.

Try to

1. See how Azure lets you know when there are errors.
2. Collect error logs.
3. Metrics.
4. Alerts.
5. etc

https://docs.microsoft.com/en-us/azure/azure-monitor/overview
