# ForeRightAPI

Back-end api for both the ForeRight mobile app and the BlazorBM web site.

## Features

- **Blazor Framework**: Utilizes Blazor for building interactive web UIs.
- **Component-Based Architecture**: Modular and reusable components for better maintainability.
- **Full-Stack C#**: Write both client-side and server-side logic in C#.
- **Modern Web Standards**: Built with modern web technologies for performance and scalability.
- **Bootstrap 5**: Bootstrap 5.0 CSS tools
- **Data from ForeRight API**: Accesses the live database from the ForeRight golf app via HTTPClient


## Repository



## Deployment
The Azure site deploys via Github actions. Whenever a new commit is published to Github, 
the workflow (YAML) file is run to deploy to Azure via dotnet publish (and thus Kudu).

KuduSync utility is run on Azure to sync the deployed zip contents with the files on the target. This is 
initiated by the Deploy.cmd in the Deployment/Tools folder. 

The -x parameter in IGNORE_MANIFEST_PARAM for KuduSync within deploy.cmd is used to ignore the manifest file during synchronization. Normally, KuduSync tracks changes between deployments using a manifest file, but when -x is set, it bypasses this tracking mechanism, allowing files to be copied without checking for differences. Otherwise, it will only copy changed files and delete files that don't exist in the destination but only if they were part of the previous deployment. This is what we need to retain the Content files that are not part of the deployment. 

Kudusync checks the env var IGNORE_MANIFEST to determine whether to use the -x parameter. This is set within the app service.



## Getting Started

1. Clone the repository:
   ```bash
   git clone <repository-url>
   ```
2. Navigate to the project directory:
   ```bash
   cd BlazorBM
   ```
3. Open the solution in Visual Studio or your preferred IDE.
4. Build and run the project.

## Prerequisites

- .NET SDK (latest version)
- Visual Studio or Visual Studio Code
- A modern web browser



## License

This project is licensed under the MIT License. See the `LICENSE` file for details.
