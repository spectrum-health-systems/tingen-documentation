# Tingen Development Processes

**CONTENTS**
[Components](#components)
[Daily development]()

## Components

```mermaid
flowchart TB
  subgraph Documentation
    direction TB
	  DevelopmentDocumentation["Development documentation"] ~~~ ApiDocumentation["API documentation"] 
	  ApiDocumentation["API documentation"] ~~~ Manual["Manual"]
  end
  subgraph WebService
    direction TB
	  Tingen["Web service entry point"] --> Outpost31["Web service logic"] 
  end

  classDef allNodes stroke-width:2px;
  class DevelopmentDocumentation,ApiDocumentationt,Manual,Tingen,Outpost31 allNodes;
  
  click Tingen "https://github.com/spectrum-health-systems/Tingen_development"
  click Outpost31 "https://github.com/spectrum-health-systems/Outpost31"
  click Manual "https://github.com/spectrum-health-systems/Tingen-Documentation/blob/main/Manual/Tingen-Manual.md"
  click DevelopmentDocumentation "https://github.com/spectrum-health-systems/Tingen-Documentation/blob/main/Development"
  click ApiDocumentation "https://github.com/spectrum-health-systems/Tingen-Documentation/blob/main/docs/README.md"
```

## Daily development

```mermaid
---
title: Overview
---
flowchart LR
  DailyDevelopment("Daily development") --> DeployToUat("Deploy to UAT")
  DeployToUat --> Testing("Testing") 
  Testing --> DailyDevelopment

  classDef allNodes stroke-width:2px;
  class DailyDevelopment,DeployToUat,Testing allNodes;
```

The following steps are taken when a new daily development session begins:

### 1. Update file headers

Update the file headers for the following files:

* Tingen.Tingen.asmx.cs
* Outpost31.WelcomeToOutpost31.cs

### 2. Update the `tnBuild` value

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
