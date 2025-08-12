<!-- u250812 -->

⦗[🏠︎](/README.md)⦘ ⦗[Tingen Project Manuals](./README.md)⦘

<div align="center">

  ![logo](/.github/img/logo/man/TngnDocProj-TngnDvdpMan-194x254.png)

</div>

# Configuring Tingen DevDeploy

The first time Tingen DevDeploy is executed, it looks for the `devdeploy-config.json file`.

If the `devdeploy-config.json file` doesn't exist, one is created using the default values that will work with any standard installation of the Tingen Web Service.

## Modifying the configuration

### ArchivePath

> Default value: `C:\Tingen_Data\DevDeploy\Archive`

The location where the existing Tingen Web Service will be archived.

The `ArchivePath` must be one of the following:

* A local directory
* A network share/mapped drive

### Source

> Default value: `https://github.com/spectrum-health-systems/Tingen-WebService/archive/refs/heads/development.zip`

The location of the Tingen Web Service that will be deployed.

The `Source` isn't necessarily a "path", since it can be either a directory or a URL.

If the `Source` is a URL:

* It must point to a ".zip" file<
* It must formatted correctly

If the `Source` is a directory, it must be one of the following:

* A local directory
* A network share/mapped drive

### SourceType

> Default value: ""

The type of source, either `path` or `url`.

This value is set at runtime, so don't modify the value in the configuration file.

### StagingPath

> Default value: `C:\Tingen_Data\DevDeploy\Stage`

The location where the Tingen Web Service is staged for deployment.

The `StagingPath` must be one of the following:

* A local directory
* A network share/mapped drive

### Deploy Path

> Default value: `C:\Tingen\UAT`

The location where the Tingen Web Service is deployed.

The `DeployPath` must be one of the following:

* A local directory
* A network share/mapped drive

<br>

***

⦗[🏠︎](/README.md)⦘ ⦗[Tingen Project Manuals](./README.md)⦘
