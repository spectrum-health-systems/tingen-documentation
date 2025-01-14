<!-- u250114 -->

<div align="center">

![logo](../github/Images/Logos/TingenDocumentation-232x308.png)

![logo](../../github/Images/Logos/TingenDocumentation-232x308.png)


![logo](../../../github/Images/Logos/TingenDocumentation-232x308.png)

 <h1>Tingen Development: Processes</h1>

</div>
sdf


![[../../github/Images/Logos/TingenDocumentation-232x308.png]]

> Last updated: January 14, 2025
# Tingen Development: Processes

[Daily development](#daily-development)
[Monthly development](#monthly-development)

# Daily development

```mermaid
---
title: Overview of the source code development process
---
flowchart LR
  DailyDevelopment("Daily development") --> DeployToUat("Deploy to UAT")
  DeployToUat --> Testing("Testing") 
  Testing --> DailyDevelopment

  classDef allNodes stroke-width:2px;
  class DailyDevelopment,DeployToUat,Testing allNodes;
```


## 1. Update file headers

Update the file headers for the following files:

* Tingen.Tingen.asmx.cs
* Outpost31.WelcomeToOutpost31.cs

## 2. Update the `tnBuild` value

Update `tnBuild` value in `Core.Session.TingenSession.BuildStaticVars()` to the current `YYMMDD.HHMM` value.

For example:

```csharp
return new Dictionary<string, string>
{
    { "tnBuild",              "241205.0944" },
    { "avSystemCode",         "UAT" },
    { "tnDataRoot",           @"C:\TingenData" },
    { "tnConfigFileName",     "Tingen.config" },
    { "ntstSecurityFileName", "NtstSecurity.config" }
};
```
