<!-- u250114 -->

> Last updated: January 14, 2025

<div align="center">

![logo](../.github/Images/Logos/TingenDocumentation-232x308.png)

 <h1>Tingen Development Process</h1>

</div>

### CONTENTS

* [Development components](#development-components)  
* [Development workflow](development-workflow)
* [Daily development](#daily-development)  
* [Monthly development](#monthly-development)
* [Release candidates](#release-candidates)
* [Stable releases](#stable-releases)
* [Community releases](#monthly-releases)

# Development components

The Tingen web service is comprised of the following components:

```mermaid
flowchart TB
  subgraph Other["Other components"]
      direction TB
      %% Components
      ScriptLinkStandard@{shape: notch-rect, label: "ScriptLink Standard"}
      Sandcastle@{shape: notch-rect, label: "Sandcastle"}
      %% Layout
      ScriptLinkStandard ~~~ Sandcastle
  end
  subgraph Documentation["Documentation components"]
      direction TB
      %% Components
      DevelopmentDocumentation@{shape: doc, label: "Development documentation"}
      ApiDocumentation@{shape: doc, label: "API Documentation"}
      Manual@{shape: doc, label: "Manual"}
      %% Layout
      DevelopmentDocumentation ~~~ ApiDocumentation ~~~ Manual
  end
  subgraph WebService["Web service components"]
      direction TB
      %% Components
      Tingen@{shape: notch-rect, label: "**Tingen**<br/>The web service<br/>entry point"}
      Outpost31@{shape: notch-rect, label: "**Outpost31**<br/>The web service logic"}
      %% Layout
      Tingen --> Outpost31
  end
  %% Styles
  style WebService color:#FFF,fill:#37474f,stroke:#FFF,stroke-width:3px
  style Tingen color:#000,fill:#ff9800,stroke:#b71c1c,stroke-width:3px
  style Outpost31 color:#000,fill:#ff9800,stroke:#b71c1c,stroke-width:3px
  style Documentation color:#FFF,fill:#37474f,stroke:#FFF,stroke-width:3px
  style DevelopmentDocumentation color:#000,fill:#ff9800,stroke:#9c27b0,stroke-width:3px
  style ApiDocumentation color:#000,fill:#ff9800,stroke:#9c27b0,stroke-width:3px
  style Manual color:#000,fill:#ff9800,stroke:#9c27b0,stroke-width:3px
  style Other color:#FFF,fill:#37474f,stroke:#FFF,stroke-width:3px
  style ScriptLinkStandard color:#000,fill:#a1887f,stroke:#b71c1c,stroke-width:3px
  style Sandcastle color:#000,fill:#a1887f,stroke:#FFF,stroke-width:3px
  %% Links 
  click Tingen "https://github.com/spectrum-health-systems/Tingen_development"
  click Outpost31 "https://github.com/spectrum-health-systems/Outpost31"
  click DevelopmentDocumentation "https://github.com/spectrum-health-systems/Tingen-Documentation/blob/main/Development"
  click ApiDocumentation "https://github.com/spectrum-health-systems/Tingen-Documentation/blob/main/docs"
  click Manual "https://github.com/spectrum-health-systems/Tingen-Documentation/blob/main/Manual"
  click ScriptLinkStandard "https://github.com/rcskids/ScriptLinkStandard"
  click Sandcastle "https://github.com/EWSoftware/SHFB"
```

# Development workflow

```mermaid
---
title: Overview
---
flowchart LR
  %% Components
  DailyDevelopment@{shape: rounded, label: "Daily development"}
  Documentation@{shape: doc, label: "Documentation"}
  MonthlyArchive@{shape: notch-rect, label: "Monthly archive"}
  ReleaseCandidate@{shape: stadium, label: "Release candidate"}
  StableRelease@{shape: stadium, label: "Stable release"}
  CommunityRelease@{shape: stadium, label: "Community release)"}
  %% Layout
  DailyDevelopment --> Documentation
  DailyDevelopment --> MonthlyArchive
  DailyDevelopment --> ReleaseCandidate --> StableRelease --> CommunityRelease
  %% Styles
  style DailyDevelopment color:#000,fill:#ff9800,stroke:#42a5f5,stroke-width:3px
  style Documentation color:#000,fill:#ff9800,stroke:#9c27b0,stroke-width:3px
  style MonthlyArchive color:#000,fill:#ff9800,stroke:#b71c1c,stroke-width:3px
  style ReleaseCandidate color:#000,fill:#ff9800,stroke:#26c6da,stroke-width:3px
  style StableRelease color:#000,fill:#ff9800,stroke:#4caf50,stroke-width:3px
  style CommunityRelease color:#000,fill:#ff9800,stroke:#ffee58,stroke-width:3px
```




# Daily development

```mermaid
flowchart LR
  %% Components
  Preparation@{shape: circle, label: "**Preparation**\nUpdate file headers\nUpdate tnBuild"}
  subgraph Development["Daily development cycle"]
    direction LR
    %% Components
    DailyDevelopment@{shape: rounded, label: "Daily development"}
    DeployToUat@{shape: rounded, label: "Deploy To UAT"}
    Testing@{shape: rounded, label: "Testing"}
    %% Layout
    DailyDevelopment --> DeployToUat --> Testing --> DailyDevelopment
  end
  %% Layout
  Preparation --> DailyDevelopment   
  %% Styles
  style Preparation color:#000,fill:#eceff1,stroke:#42a5f5,stroke-width:3px
  style DailyDevelopment color:#000,fill:#ff9800,stroke:#42a5f5,stroke-width:3px
  style DeployToUat color:#000,fill:#ff9800,stroke:#42a5f5,stroke-width:3px
  style Testing color:#000,fill:#ff9800,stroke:#42a5f5,stroke-width:3px
```

```mermaid
%%{init: {'theme':'dark'}}%%
flowchart LR
  Refactor --> Pre-Development --> Development --> Testing --> Release
```



## Preparation

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

# Monthly development

These are the steps to create a new monthly development build of Tingen.

```mermaid
flowchart TB
  %% Components
  UpdateExternalComponents@{shape: rounded, label: "Update external components"}
  ArchiveBranches@{shape: rounded, label: "Archive repository branches"}
  UpdateSourceCode@{shape: rounded, label: "Update source code"}
  UpdateDocumentation@{shape: rounded, label: "Update documentation"}
  DailyDevelopment@{shape: rounded, label: "Daily development"}
  %% Layout
  UpdateExternalComponents --> ArchiveBranches --> UpdateSourceCode --> UpdateDocumentation --> DailyDevelopment
  %% Styles
  style UpdateExternalComponents color:#000,fill:#a1887f,stroke:#FFF,stroke-width:3px
  style ArchiveBranches color:#000,fill:#ff9800,stroke:#b71c1c,stroke-width:3px
  style UpdateSourceCode color:#000,fill:#ff9800,stroke:#42a5f5,stroke-width:3px
  style UpdateDocumentation color:#000,fill:#ff9800,stroke:#9c27b0,stroke-width:3px
  style DailyDevelopment color:#000,fill:#ff9800,stroke:#42a5f5,stroke-width:3px
```

## Preparation

### 1. Update external components

```mermaid
flowchart TB
  %% Components
  UpdateExternalComponents@{shape: rounded, label: "Update external components"}
  UpdateAutoHotKey@{shape: rounded, label: "Update AutoHotKey"}
  UpdateSandcastle@{shape: rounded, label: "Update Sandcastle"}
  %% Layout
  UpdateExternalComponents --> UpdateAutoHotKey --> UpdateSandcastle
  %% Styles
  style UpdateExternalComponents color:#000,fill:#a1887f,stroke:#FFF,stroke-width:3px
  style UpdateAutoHotKey color:#FFF,fill:#a1887f,stroke:#FFF,stroke-width:3px
  style UpdateSandcastle color:#FFF,fill:#a1887f,stroke:#FFF,stroke-width:3px
```

#### 1a. AutoHotKey

Update the following components of the AutoHotkey script:

* ALT+CTRL+SHIFT+P
* ALT+CTRL+SHIFT+R
* ALT+CTRL+SHIFT+V
  
#### 1b. Sandcastle

Update the Sandcastle "Help file version" in the following Sandcastle profiles:

* Tingen
* Outpost31
* 
### 2. Archive repository branches

  Create a `YY.DD.##-development+final` branch for each of the following repositories:

* Tingen_development
* Outpost31
* Tingen-Documentation

### 3. Update the source code

#### 3a. AssemblyInfo.cs

Update the following `AssemblyInfo.cs` files with the current version number:

* Tingen_development/Properties/AssemblyInfo.cs
* Outpost31/Properties/AssemblyInfo.cs
  
#### 3b. File headers

Update the file headers for the following files:

* Tingen.Tingen.asmx.cs
* Outpost31.WelcomeToOutpost31.cs

#### 3c. `tnBuild` value

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

### 4. Update the documentation

Search for the following string in the documentation...

```markdown
![BASEDON_VERSION](https://img.shields.io/badge/BASED%20ON%20Tingen%20YY.MM-white?style=for-the-badge)
```

...where `YY.MM` is the Year.Month value for the current documentation, and keeping in mind that the "***%20***" in "**%20***MM*" is a space!

Replace the value of `YY.MM` with the current Year.Month.

For example:

```markdown
![BASEDON_VERSION](https://img.shields.io/badge/BASED%20ON%20Tingen%2025.11-white?style=for-the-badge)
```

# Release candidates

```mermaid
flowchart LR
  %% Components
  DailyDevelopment@{shape: rounded, label: "Daily development"}
  ReleaseCandidate@{shape: stadium, label: "Release candidate"}
  Testing@{shape: rounded, label: "Testing"}
  %% Layout
  DailyDevelopment -- Successful testing --> ReleaseCandidate
  DailyDevelopment -- Fixes/Updates --> ReleaseCandidate
  %% Styles
  style DailyDevelopment color:#000,fill:#ff9800,stroke:#42a5f5,stroke-width:3px
  style ReleaseCandidate color:#000,fill:#ff9800,stroke:#26c6da,stroke-width:3px
  style Testing color:#000,fill:#ff9800,stroke:#42a5f5,stroke-width:3px
```


<!--

Color codes
-----------
Project #b71c1c
Documentation #9c27b0

Outpost31/Tingen #ff9800

Development #42a5f5 
Release candidate #26c6da
Stable release #4caf50 
Community #ffee58

Daily Development
Monthly development

UAT
LIVE

Testing #a1887f

General: #eceff1 
Background#37474f

 #ffc107

-->