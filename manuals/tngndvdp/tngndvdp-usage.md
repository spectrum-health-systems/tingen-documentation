<!-- u250611 -->

> &larr; [Back to Tingen DevDeploy manual homepage](README.md)

<div align="center">

  ![logo](https://github.com/spectrum-health-systems/tingen-dev-deploy/blob/main/.github/image/logo/tngndvdp-194x254.png)

  ![Version 2.1](https://github.com/APrettyCoolProgram/aprettycoolprogram/blob/main/profile/pub/verel/v/v2.1.png)

  ![Manual](https://github.com/APrettyCoolProgram/aprettycoolprogram/blob/main/profile/pub/other/manual.png)

</div>

# Usage

To use Tingen DevDeploy:

1. Open a command line where you extracted Tingen DevDeploy
2. Type `TingenDevDeploy`

## Using Tingen DevDeploy on the hosting server (recommended)

Tingen DevDeploy is intended to be used on the server that hosts the Tingen Web Service.

The Tingen DevDeploy default settings will:

* Archive the existing Tingen Web Service to `C:\Tingen_Data\DevDeploy\Archive`
* Use the the [development branch](https://github.com/spectrum-health-systems/tingen-web-service/tree/development) of the Tingen Web Service respository as a deployment source
* Stage the deployment in the `C:\Tingen_Data\DevDeploy\Stage\`
* Deploy the Tingen Web Service to `C:\Tingen\UAT\`

## Using the Tingen DevDeploy on a local workstation

You can deploy any branch of the Tingen Web Service to any target by modifying the configuration file, but please note that performance may be impacted by a number of factors.
