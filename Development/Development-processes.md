<!-- u250114 -->

> Last updated: January 14, 2025

<div align="center">

![logo](../.github/Images/Logos/TingenDocumentation-232x308.png)

 <h1>Tingen Development Process</h1>

</div>

### CONTENTS

[Development components](#development-components)  
[Daily development](#daily-development)  
[Monthly development](#monthly-development)

# Development components

The Tingen web service is comprised of the following components:

```mermaid
flowchart TB
  subgraph Documentation["Documentation components"]
      direction TB
      %% Components
      DevelopmentDocumentation@{shape: doc, label: "Development documentation"}
      ApiDocumentation@{shape: doc, label: "API Documentation"}
      Manual@{shape: doc, label: "Tingen Manual"}
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
  %% Styles #f7dc6f #f5b041 #b9770e
  style WebService color:#FFF,fill:#37474f,stroke:#FFF,stroke-width:2px
  style Tingen color:#000,fill:#ffc107,stroke:#b71c1c,stroke-width:2px
  style Outpost31 color:#000,fill:#ff9800,stroke:#b71c1c,stroke-width:2px
  style Documentation color:#FFF,fill:#37474f,stroke:#FFF,stroke-width:2px
  style DevelopmentDocumentation color:#000,fill:#ffc107,stroke:#9c27b0,stroke-width:2px
  style ApiDocumentation color:#000,fill:#ffc107,stroke:#9c27b0,stroke-width:2px
  style Manual color:#000,fill:#ffc107,stroke:#9c27b0,stroke-width:2px
  %% Links 
  click Tingen "https://github.com/spectrum-health-systems/Tingen_development"
  click Outpost31 "https://github.com/spectrum-health-systems/Outpost31"
  click DevelopmentDocumentation "https://github.com/spectrum-health-systems/Tingen-Documentation/blob/main/Development"
  click ApiDocumentation "https://github.com/spectrum-health-systems/Tingen-Documentation/blob/main/docs"
  click Manual "https://github.com/spectrum-health-systems/Tingen-Documentation/blob/main/Manual"


```

# Daily development

```mermaid
---
title: Overview of the daily development process
---
flowchart LR
  %% Components
  Preparation@{shape: circle, label: "**Preparation**\nUpdate file headers\nUpdate tnBuild"}
  subgraph Development["Daily development cycle"]
    direction LR
    DailyDevelopment@{shape: rounded, label: "Daily development"}
    DeployToUat@{shape: rounded, label: "Deploy To UAT"}
    Testing@{shape: rounded, label: "Testing"}
    %% Layout
    DailyDevelopment --> DeployToUat --> Testing --> DailyDevelopment
  end
  %% Layout
  Preparation --> Development   
  %% Styles
  style Preparation color:#FFF,fill:#16a085,stroke:#FFF,stroke-width:2px
  style DailyDevelopment color:#FFF,fill:#16a085,stroke:#FFF,stroke-width:2px
  style DeployToUat color:#FFF,fill:grey,stroke:#FFF,stroke-width:2px
  style Testing color:#FFF,fill:steelblue,stroke:#FFF,stroke-width:2px
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

```mermaid
---
title: Overview of the monthly development process
---
flowchart LR
  %% Components
  DailyDevelopment@{shape: rect, label: "Daily development"}
  MonthlyArchive@{shape: stadium, label: "Monthly Archive"}
  %% Layout
  DailyDevelopment --x MonthlyArchive
  %% Styles
  style DailyDevelopment color:#FFF,fill:#16a085,stroke:#FFF,stroke-width:2px
  style MonthlyArchive color:#FFF,fill:#0e6655,stroke:#FFF,stroke-width:2px
```


These are the steps to create a new monthly development build of Tingen.

## 1. Update the AutoHotKey script

Update the following components of the AutoHotkey script:

* ALT+CTRL+SHIFT+P
* ALT+CTRL+SHIFT+R
* ALT+CTRL+SHIFT+V
## 2. Archive current repository branches

  Create a `YY.DD.##-development+final` branch for each of the following repositories:

* Tingen_development
* Outpost31
* Tingen-Documentation
# 3. Update the AssemblyInfo.cs files

  Update the following `AssemblyInfo.cs` files with the current version number:

* Tingen_development/Properties/AssemblyInfo.cs
* Outpost31/Properties/AssemblyInfo.cs
* 
## 4. Update file headers

Update the file headers for the following files:

* Tingen.Tingen.asmx.cs
* Outpost31.WelcomeToOutpost31.cs

## 5. Update the `tnBuild` value

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

## 6. Update the documentation

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

## 7. Update the Sandcastle help file versions

Update the Sandcastle "Help file version" in the following Sandcastle profiles:

* Tingen
* Outpost31
