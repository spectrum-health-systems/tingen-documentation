<!-- u250925 -->

<div align="center">

  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://github.com/spectrum-health-systems/tingen-projects/blob/main/logos/tngnproj-dark-400x63.png">
    <source media="(prefers-color-scheme: light)" srcset="https://github.com/spectrum-health-systems/tingen-projects/blob/main/logos/tngnproj-light-400x63.png">
    <img alt="Fallback image description" src="https://github.com/spectrum-health-systems/tingen-projects/blob/main/logos/tngnproj-light-400x63.png">
  </picture>
  <h1>
    TINGEN ROADMAPS
  </h1>

</div>

> This is also the roadmap for the [Tingen Web Service](https://github.com/spectrum-health-systems/tingen-web-service.).

***

* [Release](#release)
* [IIS](#iis)
* [Documentation](#documentation)

# Release

## R25.10

TBD

## R25.9

- [ ] Setup custom messages for OptObj error messages
- [X] Move trace logs to Sessions
- [ ] Session logs can be simple or verbose
- [ ] Make all session stuff internal (?)
- [X] Test to see what happens when a blueprint is deleted, does it show up when the service execute
- [X] Web service appdata -> root NOTE: Don't do this.
- [ ] Verify classes/methods are public/private/internal
- [ ] Verify that the automated reports are being updated
- [ ] Verify deploy is non-destructive-isg
- [ ] Very simple test return
- [X] Test looped debugs to make sure they are created with a 1ms delay
- [ ] Functionality: Dosing
- [ ] Functionality: Form access
- [ ] Functionality: TeleHealth
- [ ] Whitelists
- [ ] Greylists
- [ ] Blacklists
- [ ] Parameters that start with "_" use the calling form to parse requests.
- [ ] Autmatically create status logs every day
- [ ] Re-enable trace logs for each method
- [ ] Build a trace log package for easier trace logging
- [ ] Limit passed parameters to methods
- [ ] Verify automated reports are being updated
- [ ] Mode terminology Should "disable" work? Or just "disabled", specifically?
- [ ] Performance considerations - Runaway processes - Out of disk space - IIS worker threads
- [ ] Email functionality
- [ ] Fix issue with deploying taking multiple deployments
- [X] Update blueprints to match documentation
- [ ] New critical error: the Avatar Systems don't match
- [ ] Email critical errors
- [ ] Trace logs where they need to be
- [ ] Auto-generated data copied from deployment folder
- [ ] Fallback for name conversion (Sebastian's idea)
- [ ] Disable Scripts For Error (what is this?)

# IIS

- [ ] Remove the ISS site from Tingen_www, and add two sites to:
  - Tingen_www\UAT
  - Tingen_www\LIVE
  - Tingen_www\SBOX

# Documentation

- [ ] Document what white/grey/blacklists are for
