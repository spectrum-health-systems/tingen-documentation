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

## OpenIncident Module
  * `NEW` _VerifyOriginalAuthorIsOpening
  * `NEW` _VerifyOriginalAuthorIsSubmitting
* If the AvatarUsername is not found in the translation table, the user a popup will appear instructing the user to contact the service desk

## Web.config
  * `NEW` AvatarSystem
  * `NEW` Mode
  * `NEW` BaseWww
  * `NEW` BaseData
  * `NEW` BuildNumber

## Trace logging
  * `NEW` **TraceLogLimit**
    * Trace logs now have an individual <b>traceLevel</b> and a global <b>traceLevelLimit</b>, which allows you to specify which trace logs are created.
    * The <i>traceLevel</i> is defined on a per-log basis, and the <i>traceLevelLimit</i> is defined in Web.config.
    * Setting the *traceLogLimit* to "0" will disable all trace logs, regardless of their *traceLevel*
    * If a trace log has a  *traceLimit* of "1" , it will always be created regardless of the *traceLogLimit*
    * Otherwise, a trace log will be created if it has a *traceLimit* that is less than the *traceLogLimit*

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
