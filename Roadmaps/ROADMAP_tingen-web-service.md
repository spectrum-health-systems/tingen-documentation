# ROADMAP: Tingen Web Service

> NOTE
> This roadmap also includes Outpost31

### CONTENTS

- [Current version](#current-version)
- [Next version](#next-version)
- [Future version](#future-version)
- [Other](#other)

## Current version

- [ ] Validate Session information
    - [ ] All required directories
    - [ ] All required files
    - [ ] ?


- [ ] Settings files
    - [ ] Write settings files to remote\admin
    - [ ] "Service version: YY.MM.x.y (YYMMDD)
    - [ ] Proper MD formatting (spaces, etc.)


## Next version

TBD

## Future version

TBD

## Other



- **Auto refresh status/settings exports**  
Currently a bunch of stuff is refreshed when Tingen is disabled, but those things need to be manually refreshed when it's enabled again. Is there an efficient way to check to see if there is a change back to enabled, and refresh things.

- **Allow users to specify the `Tingen_Data` location on the host machine**  
Currently the `c:\Tingen_Data` path is hardcoded. Eventually this path should be customizable, perhaps stored in an external file in `.\AppData\Runtime`.

- **Store the Tingen Web Service `ValidEnvironments` and `ValidModes` in external files**  
These should be modifiable by the user.