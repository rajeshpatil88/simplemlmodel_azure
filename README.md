# Flask App Deployment to Azure Web App

Welcome to the Flask App Deployment guide! This repository provides you with step-by-step instructions for deploying a Flask app to Azure Web App. The app includes a simple machine learning model that demonstrates the process of deploying a web service.

## Table of Contents

- [Getting Started](#getting-started)
- [Deployment Instructions](#deployment-instructions)
- [Accessing Your Deployed App](#accessing-your-deployed-app)
- [Redeploying the App](#redeploying-the-app)
- [Contributing](#contributing)

## Getting Started:

1. **Fork this Repository:** Fork this repository to your GitHub account. This creates a personal copy of the repository that you can modify and deploy.

2. **Clone Your Fork:** Clone the forked repository to your local machine using the following command:
   ```sh
   git clone https://github.com/YourGitHubUsername/YourGitHubRepo.git

- Modify the App (Optional): Make any necessary improvements or modifications to the Flask app on your local machine and push it to your remote repo.

## Deployment Instructions:

Follow these steps to deploy your modified Flask app to Azure Web App:

1. Log in to Azure: Open your terminal or command prompt and log in to your Azure account using the Azure CLI:

   ```sh
   az login

2. Create Resources: If needed, create a resource group:

    ```sh
   az group create --name YourResourceGroupName --location YourAzureRegion
    
3. Create an Azure App Service Plan for Web App:
   
     ```sh
    az appservice plan create --name YourAppServicePlanName --resource-group YourResourceGroupName --sku FREE --is-linux
     
4. Deploy to Azure Web App: Run the following command to deploy your app to Azure:
   
   ```sh
   az webapp create --name YourWebAppName --resource-group YourResourceGroupName --plan YourAppServicePlanName --runtime "PYTHON|3.8" --deployment-source-url    https://github.com/YourGitHubUsername/YourGitHubRepo.git --deployment-source-branch main

## Accessing Your Deployed App:

Once the deployment is complete, access your deployed Flask app using the provided URL:

https://YourWebAppName.azurewebsites.net

Congratulations! You've successfully deployed your Flask app to Azure Web App.

## Redeploying the App:
If you need to redeploy your app with the latest code changes, you can use the following command:

- Below command tells Azure to sync and redeploy your web app using the latest source code.

   ```sh
   az webapp deployment source sync --name YourWebAppName --resource-group YourResourceGroupName

## Contributing:

If you'd like to contribute to this project or have suggestions, feel free to create issues or pull requests.
