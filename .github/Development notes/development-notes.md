# Tingen Development Notes

# General

* Blacklists and whitelists

# Tingen_development.Tingen_development.asmx.cs

## Issues

* **Finalizing the OptionObject**  
  It's important that the return object is formatted correctly before `return tnSession.AvData.ReturnOptionObject;`.  

  Currently OptionObjects are formatted closer to the work being done, but we need to make sure that is happenening.  

  This might actually be done in TingenApp.Stop(). Regardless, we should have a failsafe to make sure the return object is formatted correctly before it gets returned to Avatar.

## Todo

* [ ] Review all XML comments

## Notes

None.

<br>

***

<br>

# Outpost31.Core.Avatar.AvatarData.cs

## Issues

None.

## Todo

* [ ] Review all XML comments

## Notes

None.

<br>

***

<br>

# Outpost31.Core.Avatar.ReturnObject.cs

## Issues

None.

## Todo

* [ ] Review all XML comments
* [ ] Verify there are no issues with a Trace Log being generated.  

## Notes

* Limit what is passed to these methods (not the entire session object)?
* Gracefully exit with default case

<br>

***

<br>

# Outpost31.Core.Configuration.ConfigSettings.cs

## Issues

None.

## Todo

* [ ] Review all XML comments

## Notes

* Rename this directory to "Configs"?
* Create a "blacklist" that will allow certain users to bypass Tingen?

<br>

***

<br>

# Outpost31.Core.Framework.Catalog.PublicPaths.cs

* [ ] Review all XML comments
* Is there a better way to do RequiredPaths()?

<br>

***

<br>

# Outpost31.Core.Framework.Catalog.RemotePaths.cs

* [ ] Review all XML comments
* Is there a better way to do RequiredPaths()?

<br>

***

<br>

# Outpost31.Core.Framework.Catalog.SystemCodePaths.cs

* [ ] Review all XML comments
* Is there a better way to do RequiredPaths()?

<br>

***

<br>

# Outpost31.Core.Framework.Catalog.TingenPaths.cs

* [ ] Review all XML comments
* Is there a better way to do RequiredPaths()?

<br>

***

<br>

# Outpost31.Core.Framework.Maintenance.cs

## Issues

None.

## Todo

* [ ] Review all XML comments
* [ ] Verify that `if (directoryPath.Contains("Primeval"))` works as expected (it used to be `!directoryPath.Contains("Primeval")`).

## Notes

* Limit what is passed to the methods in `VerifyFramework()` (not the entire session object)?

<br>

***

<br>

# Outpost31.Core.Framework.Paths.cs

## Issues

None.

## Todo

* [ ] Review all XML comments


## Notes

* Limit what is passed to the methods in `VerifyFramework()` (not the entire session object)?

<br>

***

<br>

# Outpost31.Core.Framework.Refresh.cs

## Issues

None.

## Todo

* [ ] Review all XML comments


## Notes

* Limit what is passed to the methods (not the entire session object)?
* Is there an efficient way to refresh status files when Tingen is enabled?
* When `RefreshUnknown` is called, there is a popup message. Should there be a message? And if so, what should the message be?

<br>

***

<br>

# Outpost31.Core.Logger.LogEvent.cs

## Issues

None.

## Todo

* [ ] Review all XML comments


## Notes

* Is there a more efficient way of doing this (see https://rules.sonarsource.com/csharp/RSPEC-6608/):
* Better way of doing `var calledClass = calledPath.Split('\\').Last();`
* Make sure that passing the entire TingenSession object OR the traceInfo object work the same.

<br>

***

<br>

# Outpost31.Core.Logger.LoggerCatalog.cs

## Issues

None.

## Todo

* [ ] Review all XML comments

## Notes

None.

<br>

***

<br>

# Outpost31.Core.Logger.PrimevalLog.cs

## Issues

None.

## Todo

* [ ] Review all XML comments

## Notes

None.

<br>

***

<br>

# Outpost31.Core.Logger.TraceLog.cs

## Issues

None.

## Todo

* [ ] Review all XML comments

## Notes

None.

<br>

***

<br>


# Outpost31.Core.NtstWebServiceSecurity.cs

## Issues

* Remove this for now.

## Todo

* [ ] Review all XML comments

## Notes

None.

<br>

***

<br>


















<!-- -->

# Class.cs

## Issues

None.

## Todo

* [ ] Review all XML comments

## Notes

None.

<br>

***

<br>

<!-- -->








## Current settings file

* Fix formatting
* Add other module data
* Sebastian's last update

## Ability to save field data to local drive

* Should be saved to a folder that is always nuked (e.g., "TingenData\UAT\Ephmereal\")
* Should be encrypted

## Save an OptionObject locally

* Can be used for testing?
* Can be used so Commander/Lieutenant can call Tingen directly?

## Session.md files

* Elapsed time
* Sebastian's last update (for module)

## Trace log statements

* Put comments where trace logs can't go, and why.

## Admin module

- Enable/disable

## Modes

- Should "disable" work? Or just "disabled", specifically?

## Emails

* When service staus changes
* Summary information

## Remote\

* Summary reports
* Session data naming conventions

## Remote access

* [x] Make sure Jonathan/Courtney have access to TingenData\Remote\
* [x] Make sure BuisIntel has access to TingenData\LIVE\Imports\FromAvatar\

## Performance

* Runaway processes
* Out of disk space
* IIS worker threads


## Open Incident

* Module enable/disable <- that's it
* Module whitelist/blacklist

* In config:
  * Messages
  * Error codes
  * true/false create remote session details for opening forms

## Sebastian's report
* Somebody added last minute won't be there
* Name changes (Courtney)
  