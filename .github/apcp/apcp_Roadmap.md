# apcp_ROADMAP: Tingen Web Service

> Internal apcp development only!

## R25.9


- [ ] Setup custom messages for OptObj error messages
- [ ] Move logs to Sessions
- [ ] Session logs can be simple or verbose
- [ ] Make all session stuff internal
- [X] Test to see what happens when a blueprint is deleted, does it show up when the service execute
- [X] web service appdata -> root NOTE: Don't do this.

public/private/internal

- [ ] very simple test return


- [ ] Remove the ISS site from Tingen_www, and add two sites to:
  - Tingen_www\UAT
  - Tingen_www\LIVE




















* A random number generator determines if things are done:
    * Status updates
    * Framework checks
    * temp file cleaning

* WsvcMissingArgs.txt allows for placeholders that are replaced by the actual values.

* All current functionality
 - Open incident
 - Kristy's report
 - dose
 - ?

* Blacklists
* Whitelists
* .tinplates
* ModOpenIncident functionality

* Update all XML documentation/comments
* Update all extensions (SFHB, Json, etc.)

* Limit passed parameters to methods
Item statusDraft
APrettyCoolProgram opened on Oct 17, 2024
Description
APrettyCoolProgram
on Oct 17, 2024 (edited)
Should we limit what is passed to various methods (e.g., not the entire session object)?
Outpost31.Core.Framework.Paths.VerifyFramework()
Outpost31.Core.Framework.Refresh.VerifyFramework()
There may be more...

* RefreshUnknown popup message
Item statusDraft
APrettyCoolProgram opened on Oct 17, 2024
Description
APrettyCoolProgram
on Oct 17, 2024 (edited)
When RefreshUnknown is called, there is a popup message.

Should there be a message? And if so, what should the message be?

* Refreshing status files automatically
Item statusDraft
APrettyCoolProgram opened on Oct 17, 2024
Description
APrettyCoolProgram
on Oct 17, 2024 (edited)
Is there an efficient way to refresh status files when Tingen is enabled?

For example, when Tingen is disabled/enable

* More efficient way of logging events
Item statusDraft
APrettyCoolProgram opened on Oct 17, 2024
Description
APrettyCoolProgram
on Oct 17, 2024 (edited)
Is there a more efficient way of doing this (see https://rules.sonarsource.com/csharp/RSPEC-6608/)
Better way of doing var calledClass = calledPath.Split('\\').Last();
Make sure that passing the entire TingenSession object OR the traceInfo object work the same.

* Current settings file modifications
Item statusDraft
APrettyCoolProgram opened on Oct 17, 2024
Description
APrettyCoolProgram
on Oct 17, 2024 (edited)
Fix formatting
Add other module data
Sebastian's last update

* Ability to save field data to local drive
Item statusDraft
APrettyCoolProgram opened on Oct 17, 2024
Description
APrettyCoolProgram
on Oct 17, 2024 (edited)
Should be saved to a folder that is always nuked (e.g., "TingenData\UAT\Ephmereal")
Should be encrypted

* Save an OptionObject locally
Item statusDraft
APrettyCoolProgram opened on Oct 17, 2024
Description
APrettyCoolProgram
on Oct 17, 2024 (edited)
Can be used for testing?
Can be used so Commander/Lieutenant can call Tingen directly?

* Mode terminology
Item statusDraft
APrettyCoolProgram opened on Oct 17, 2024
Description
APrettyCoolProgram
on Oct 17, 2024 (edited)
Should "disable" work? Or just "disabled", specifically?

* Email functionality
Item statusDraft
APrettyCoolProgram opened on Oct 17, 2024
Description
APrettyCoolProgram
on Oct 17, 2024 (edited)
When service staus changes
Summary information

* Performance considerations
Item statusDraft
APrettyCoolProgram opened on Oct 17, 2024
Description
APrettyCoolProgram
on Oct 17, 2024 (edited)
Runaway processes
Out of disk space
IIS worker threads

* Sebastian's report
Item statusDraft
APrettyCoolProgram opened on Oct 17, 2024
Description
APrettyCoolProgram
on Oct 17, 2024 (edited)
Somebody added last minute won't be there
Name changes (Courtney)

* System Status files
Item statusDraft
APrettyCoolProgram opened on Oct 17, 2024
Description
APrettyCoolProgram
on Oct 17, 2024 (edited)
Are these only written to Remote\?


## Tingen-WebServiceNX

Tingen Web Service NX will be based on .NET.

