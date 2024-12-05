<!-- u241104 -->

<div align="center">

  ![logo](../../.github/Images/Logos/TingenDocumentation-232x308.png)

  ![BASEDON_VERSION](https://img.shields.io/badge/BASED%20ON%20Tingen%2024.12-white?style=for-the-badge)

  <h1>
    Tingen daily development
  </h1>

</div>

# Overview

```mermaid
flowchart LR
  %% Components
  DailyDevelopment@{shape: rect, label: "Daily development"}
  DeployToUat@{shape: rounded, label: "Deploy To UAT"}
  Testing@{shape: rounded, label: "Testing"}
  %% Layout
  DailyDevelopment --> DeployToUat --> Testing --> DailyDevelopment
  %% Styles
  style DailyDevelopment color:#FFF,fill:#16a085,stroke:#FFF,stroke-width:2px
  style DeployToUat color:#FFF,fill:grey,stroke:#FFF,stroke-width:2px
  style Testing color:#FFF,fill:steelblue,stroke:#FFF,stroke-width:2px
```

## Development documentation

```mermaid
flowchart LR
  %% Components
  DailyDevelopment@{shape: rect, label: "Daily development"}
  DevelopmentDocumentation@{shape: doc, label: "Development documentation"}
  Manual@{shape: doc, label: "Tingen Manual"}
  %% Layout
  DailyDevelopment -.-> DevelopmentDocumentation
  DailyDevelopment -.-> Manual
  %% Styles
  style DailyDevelopment color:#FFF,fill:#16a085,stroke:#FFF,stroke-width:2px
  style DevelopmentDocumentation color:#000,fill:#f7dc6f,stroke:#ba4a00,stroke-width:2px
  style Manual color:#FFF,fill:#b9770e,stroke:#ba4a00,stroke-width:2px
```

# Daily Development

When development starts for the day:

## 1. Update file headers

Update the file headers for both `Tingen.Tingen.asmx.cs` and `Outpost31.WelcomeToOutpost31.cs` with the current the datestamp information:

For example:

```text
// ================================================================ 241031 =====
```

## 2. Update the tnBuild value

Update `tnBuild` value in `Core.Session.TingenSession.BuildStaticVars()` to the current `HHMM` value.

For example:

```csharp
return new Dictionary<string, string>
{
    { "tnBuild",              "0919" },
    { "avSystemCode",         "UAT" },
    { "tnDataRoot",           @"C:\TingenData" },
    { "tnConfigFileName",     "Tingen.config" },
    { "ntstSecurityFileName", "NtstSecurity.config" }
};
```
