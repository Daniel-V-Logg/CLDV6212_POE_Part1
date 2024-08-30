# Azure Storage Solution - Part 1

## Introduction

This project demonstrates the implementation of an Azure storage solution as part of the CLDV6212 Proof of Expertise (POE) for cloud development. The project involves setting up Azure SQL Database, Blob Storage, Queue Storage, Table Storage, and File Storage, and integrating these services into an ASP.NET Core web application.

## Project Structure

1. **Blob Storage** - Manages file storage with Azure Blob Storage.
2. **Queue Storage** - Handles messaging with Azure Queue Storage.
3. **Table Storage** - Stores structured data using Azure Table Storage.
4. **File Storage** - Manages file operations with Azure File Storage.
5. **SQL Database** - Stores relational data using Azure SQL Database.

## Prerequisites

- Azure account with an active subscription.
- Visual Studio Code or another IDE for development.
- .NET Core SDK installed.

## Setup Instructions

### 1. Configuring Azure Environment

#### Create a New Resource Group

1. **Sign In to Azure Portal:**
   - Go to [Azure Portal](https://portal.azure.com/).
   - Sign in with your Azure account credentials.

2. **Create Resource Group:**
   - In the Azure Portal, select **Resource groups** from the left-hand menu.
   - Click on **+ Create** at the top.
   - Enter a name for your resource group (e.g., `MyResourceGroup`).
   - Select the Azure region (e.g., `East US`).
   - Click **Review + Create**, then **Create**.

#### Create and Configure Storage Accounts

1. **Navigate to Storage Accounts:**
   - In the Azure Portal, select **Storage accounts** from the left-hand menu.

2. **Create a Storage Account:**
   - Click **+ Create**.
   - Choose the appropriate **Storage account name**.
   - Select the **Region** where you want to deploy the storage.
   - Choose the **Performance** and **Replication** options.
   - Click **Review + Create**, then **Create**.

3. **Configure Storage Services:**
   - **Blob Storage:**
     - Navigate to your storage account.
     - Select **Containers** under Blob service.
     - Click **+ Container** to create a new container.
     - Set **Access level** (e.g., Private, Blob, Container) and click **Create**.
   - **Queue Storage:**
     - Navigate to **Queues** under Queue service.
     - Click **+ Queue** to create a new queue.
   - **Table Storage:**
     - Navigate to **Tables** under Table service.
     - Click **+ Table** to create a new table.
   - **File Storage:**
     - Navigate to **Files** under File service.
     - Click **+ File share** to create a new file share.

### 2. Code Implementation

The code for handling Azure services is organized into the following classes:

- **`BlobStorageService`** - Handles file upload and management in Azure Blob Storage.
- **`QueueStorageService`** - Manages message queues in Azure Queue Storage.
- **`TableService`** - Handles operations with Azure Table Storage.
- **`FileService`** - Manages file operations with Azure File Storage.

### 3. Configuration

**`appsettings.json`**:

Ensure that your `appsettings.json` file contains the correct connection strings for your Azure services:

```json
{
  "ConnectionStrings": {
    "AzureSqlDatabase": "Server=tcp:<your-server-name>.database.windows.net,1433;Database=<your-database-name>;User ID=<your-username>;Password=<your-password>;Trusted_Connection=False;Encrypt=True;"
  },
  "AzureStorage": {
    "BlobConnectionString": "DefaultEndpointsProtocol=https;AccountName=<your-account-name>;AccountKey=<your-account-key>;BlobEndpoint=<your-blob-endpoint>;",
    "QueueConnectionString": "DefaultEndpointsProtocol=https;AccountName=<your-account-name>;AccountKey=<your-account-key>;QueueEndpoint=<your-queue-endpoint>;",
    "TableConnectionString": "DefaultEndpointsProtocol=https;AccountName=<your-account-name>;AccountKey=<your-account-key>;TableEndpoint=<your-table-endpoint>;",
    "FileConnectionString": "DefaultEndpointsProtocol=https;AccountName=<your-account-name>;AccountKey=<your-account-key>;FileEndpoint=<your-file-endpoint>;"
  },
  "Logging": {
    "LogLevel": {
      "Default": "Information",
      "Microsoft.AspNetCore": "Warning"
    }
  },
  "AllowedHosts": "*"
}
```

### 4. Usage

**Running the Application:**

1. Open your project in Visual Studio Code or another IDE.
2. Restore dependencies and build the project.
3. Run the application using the built-in server or IIS Express.

**Accessing the Application:**

- Navigate to `https://localhost:5001` in your web browser to view the application.

### 5. Testing and Validation

- **Blob Storage:** Upload and verify files in the configured Blob container.
- **Queue Storage:** Send and receive messages from the configured Queue.
- **Table Storage:** Add, retrieve, and delete entities in the configured Table.
- **SQL Database:** Test CRUD operations on the Azure SQL Database.

### 6. Documentation

Ensure that you have detailed documentation for each service, including:

- **Architecture Diagram:** Visual representation of how services are integrated.
- **Code Comments:** Explanation of the code functionality and logic.
- **Deployment Instructions:** Steps for deploying and running the application.

### 7. Conclusion

Summarize the achievements, challenges faced, and potential improvements for the storage solution. Reflect on the lessons learned during the project.
