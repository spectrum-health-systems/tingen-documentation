<!-- u250611 -->

> &larr; [Back to Tingen DevDeploy manual homepage](README.md)

<div align="center">

  ![logo](https://github.com/spectrum-health-systems/tingen-dev-deploy/blob/main/.github/image/logo/tngndvdp-194x254.png)

  ![Version 2.1](https://github.com/APrettyCoolProgram/aprettycoolprogram/blob/main/profile/pub/verel/v/v2.1.png)

  ![Documentation](https://github.com/APrettyCoolProgram/aprettycoolprogram/blob/main/profile/pub/other/manual.png)

</div>

# Configuration

The first time Tingen DevDeploy is executed, it looks for the `devdeploy-config.json file`.

If the `devdeploy-config.json file` doesn't exist, one is created using the default values that will work with any standard installation of the Tingen Web Service.

## Modifying the configuration

The `devdeploy-config.json file` file contains the following configuration settings:

* ArchivePath  
  The location where the existing Tingen Web Service will be archived.

* Source  
  The location of the Tingen Web Service that will be deployed.

* SourceType  
  The type of source, either a URL or a directory path.

* StagePath  
  The location where the Tingen Web Service is staged for deployment.

* DeployPath  
  The location where the Tingen Web Service is deployed.

### ArchivePath

> Default value: `C:\Tingen_Data\DevDeploy\Archive`

This can be:

* A local directory
* A network share/mapped drive

### Source

> Default value: `https://github.com/spectrum-health-systems/Tingen-WebService/archive/refs/heads/development.zip`

This isn't necessarily a "path", since it can be either a directory or a URL.

If the RepositoryPath is a URL:
* It must point to a ".zip" file<
* It must formatted correctly

If the RepositoryPath is a directory:
* It can be a local directory
* It can be a network share/mapped drive

### SourceType

> Default value: ""

### StagingPath

> Default value: `C:\Tingen_Data\DevDeploy\Stage`

This can be:

* A local directory
* A network share/mapped drive

### Deploy Path

> Default value: `C:\Tingen\UAT`

This can be:

* A local directory
* A network share/mapped drive

> &larr; [Back to Tingen DevDeploy manual homepage](README.md)