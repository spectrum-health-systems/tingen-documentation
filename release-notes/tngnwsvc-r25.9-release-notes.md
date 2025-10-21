<!-- u251002 -->

<div align="center">

  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://github.com/spectrum-health-systems/tingen-projects/blob/main/logos/tngndocs-dark-400x63.png">
    <source media="(prefers-color-scheme: light)" srcset="https://github.com/spectrum-health-systems/tingen-projects/blob/main/logos/tngndocs-light-400x63.png">
    <img alt="Fallback image description" src="https://github.com/spectrum-health-systems/tingen-projects/blob/main/logos/tngndocs-light-400x63.png">
  </picture>
  <h1>
    R25.9 Release Notes
  </h1>

</div>

# Core

## Core.Logger

* `NEW` **TraceLogLimit**
  > Default: `0`
  * Trace logs now have an individual **traceLevel** and a global **traceLevelLimit**, which allows you to specify which trace logs are created.
  * The *traceLevel* is defined on a per-log basis, and the *traceLevelLimit* is defined in Web.config
  * A trace log will be created if it has a *traceLimit* that is less than the *traceLogLimit*
  * Setting the *traceLogLimit* to "0" will disable all trace logs
  * Setting the *traceLogLimit* to "9" will enable all trace logs

## Web.config file

* `NEW` AvatarSystem  
  The Avatar *System* that the Tingen Web Service will interface with.
  > LIVE, UAT, or SBOX
* `NEW` Mode
* `NEW` BaseWww
* `NEW` BaseData
* `NEW` BuildNumber

# Modules

## Module.OpenIncident

* `NEW` _VerifyOriginalAuthorIsOpening
* `NEW` _VerifyOriginalAuthorIsSubmitting
* If the AvatarUsername is not found in the translation table, the user a popup will appear instructing the user to contact the service desk





## Misc notes

* Web service can now be used in the SBOX, UAT, and LIVE system codes
* Session data now includes the current day/time, the Avatar UserName, and framework details
* Split the *Parser* class into separate, partial classes
* Renamed the *session* object is now *sess*
* Significant rework of logging functionality
* Standard blueprint files have a **.bp** extension, while embedded blueprint files have a **.embp** extension.
* Added non-standard trace logging in TingenWebservice.Runscript()
* Removed the popup when the Tingen Web Service is disabled, since that would actually cause havoc. 
* `REMOVED` AdminMode (functionality has been moved to the Administration Module)
* `REMOVED` The popup that appears when the Tingen Web Service is disabled.

***


* [X] Move trace logs to Sessions
* [X] Test to see what happens when a blueprint is deleted, does it show up when the service execute
* [X] Web service appdata -> root NOTE: Don't do this.
* [X] Test looped debugs to make sure they are created with a 1ms delay
* [X] Parameters that start with "_" use the calling form to parse requests.
* [X] Update blueprints to match documentation
