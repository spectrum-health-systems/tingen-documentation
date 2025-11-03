<!-- u251103 -->

<div align="center">

  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://github.com/spectrum-health-systems/tingen-projects/blob/main/logos/tngndocs-dark-400x63.png">
    <source media="(prefers-color-scheme: light)" srcset="https://github.com/spectrum-health-systems/tingen-projects/blob/main/logos/tngndocs-light-400x63.png">
    <img alt="Fallback image description" src="https://github.com/spectrum-health-systems/tingen-projects/blob/main/logos/tngndocs-light-400x63.png">
  </picture>

  <h1>Netsmart Web Services</h1>

  <br/>
  <br/>

</div>

<br/>

<!--
  ADD TEXT
  Describe what a Netsmart web service is, and how it is different than a custom web service.

  A list of the current web services?
-->

# Verifying the Avatar Web Services URL Registry Setting

There is a registry setting in Avatar named

 > Initial System Configuration
  > Avatar PM
   > Avatar Web Services
    > Set System Defaults
     > URL Registry Setting Value.

# Adding a Netsmart web service to the Tingen Web Service

## Confirming the Netsmart web service URL

Before adding a Netsmart web service to the Tingen Web Service, confirm that the URL you will be adding is valid by:

1. Pasting the WSDL URL into a browser
2. Verifing that the WSDL page is displayed

## Adding the service

To add a Netsmart Web Service:

1. Right-click on your project
2. Click **Add**
3. Click **Service Reference**
4. Click the **Advanced** button
5. Click the **Add Web Service** button
6. In the *URL* field, put the name of the Web Service you want to add. It should look something like this:

LIVE  
`<https://ORGANIZATIONcsp.netsmartcloud.com/csp/ORGANIZATION/avpm/WEBSVC.UserManagement.CLS?WSDL>`

Keep in mind that different Avatar Systems will have different URLs:

SBOX
`<https://ORGANIZATIONcsp.netsmartcloud.com/csp/ORGANIZATIONsbox/avpm/WEBSVC.UserManagement.CLS?WSDL>`

UAT
`<https://ORGANIZATIONcsp.netsmartcloud.com/csp/ORGANIZATIONuat/avpm/WEBSVC.UserManagement.CLS?WSDL>`

7. Click the arrow icon to the right of the URL. The Web Service should be found.

8. In the *Web reference name* field, give the web service a name that your project will use to reference the Web Service using the following syntax:  

`NtstWscv{AvatarSystem}{NetsmartWebServiceName}`

for example:

  `NtstWscvSboxUserManagement`

9. Click **Add Reference**.
