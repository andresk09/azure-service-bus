# azure-service-bus

Microsoft Quickstart for Service Bus queues

Create resources

```
# Create a resource group
resourceGroupName="learn-rg-$RANDOM"

az group create --name $resourceGroupName --location westeurope

# Create a Service Bus messaging namespace with a unique name
namespaceName=learn-namespace-$RANDOM
az servicebus namespace create --resource-group $resourceGroupName --name $namespaceName --location westeurope

# Create a Service Bus queue
az servicebus queue create --resource-group $resourceGroupName --namespace-name $namespaceName --name BasicQueue

# Get the connection string for the namespace
connectionString=$(az servicebus namespace authorization-rule keys list --resource-group $resourceGroupName --namespace-name $namespaceName --name RootManageSharedAccessKey --query primaryConnectionString --output tsv)

```