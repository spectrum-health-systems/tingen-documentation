<!-- u250618 -->

⦗[🏠︎](/README.md)⦘ ⦗[Tingen Manuals](./README.md)⦘ ⦗[Tingen DevDeploy Manual](../README.md)⦘

<div align="center">

  ![logo](/.github/img/logo/man/TngnDocProj-TngnDvdpMan-194x254.png)

</div>

# Using Tingen DevDeploy

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

<br>

***

⦗[🏠︎](/README.md)⦘ ⦗[Tingen Manuals](./README.md)⦘ ⦗[Tingen DevDeploy Manual](../README.md)⦘
