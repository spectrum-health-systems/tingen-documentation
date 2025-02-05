<!-- u250114 -->

> Last updated: January 14, 2025

<div align="center">

![logo](../../.github/Images/Logos/TingenDevelopmentDocumentation-320x425.png)

 <h1>Development workflow</h1>

</div>

# Overview

```mermaid
gantt
  title Monthly development phases
  dateFormat X
  axisFormat %d
  Planning : 0, 2d
  Refactor : 4d
  Development : 24d
  Release : 1d
```

## Planning

During the planning phase:

* The current development branch is archived
* Source code and documentation version numbers are updated
* External components are updated
* Upcoming features are ironed out

### Archiving the current development branch

TBD

### Preparing for a new monthly release

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

#### 1a. AutoHotKey

Update the following components of the AutoHotkey script:

* ALT+CTRL+SHIFT+P
* ALT+CTRL+SHIFT+R
* ALT+CTRL+SHIFT+V
  
#### 1b. Sandcastle

Update the Sandcastle "Help file version" in the following Sandcastle profiles:

* Tingen
* Outpost31
  
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
![TINGEN_VERSION](https://img.shields.io/badge/BASED%20ON%20Tingen%20YY.MM-white?style=for-the-badge)
```

...where `YY.MM` is the Year.Month value for the current documentation, and keeping in mind that the "***%20***" in "**%20***MM*" is a space!

Replace the value of `YY.MM` with the current Year.Month.

For example:

```markdown
![TINGEN_VERSION](https://img.shields.io/badge/BASED%20ON%20Tingen%2025.11-white?style=for-the-badge)
```


## Refactor

During the refactor phase:

* The codebase is cleaned up
* Documentation is cleaned up

## Development

During the development phase:

* New functionality is added
* Existing functionality is updated/modified
* Bugs are squished
* New documentation is added
* Existing documentation is updated/modified
* Iterative testing is done in a non-production environment

## Release

During the release phase:

* TBD


## Monthly development





```mermaid
flowchart TB
  %% Subgraph 1
  subgraph LR[MonthlyDevelopment]
  end
  %% Subgraph 2
  subgraph LR[DailyDevelopment]
  end
  %% Layout
  MonthlyDevelopent --> DailyDevelopment

```









```mermaid
flowchart LR
  %% Components
  Development@{shape: rounded, label: "Development"}
  Documentation@{shape: doc, label: "Documentation"}
  MonthlyArchive@{shape: notch-rect, label: "Monthly archive"}
  ReleaseCandidate@{shape: stadium, label: "Release candidate"}
  StableRelease@{shape: stadium, label: "Stable release"}
  CommunityRelease@{shape: stadium, label: "Community release)"}
  %% Layout
  Development --> Documentation
  Development --> ReleaseCandidate --> StableRelease --> CommunityRelease
  StableRelease --> MonthlyArchive
  %% Styles
  style Development color:#000,fill:#ff9800,stroke:#42a5f5,stroke-width:3px
  style Documentation color:#000,fill:#ff9800,stroke:#9c27b0,stroke-width:3px
  style MonthlyArchive color:#000,fill:#ff9800,stroke:#b71c1c,stroke-width:3px
  style ReleaseCandidate color:#000,fill:#ff9800,stroke:#26c6da,stroke-width:3px
  style StableRelease color:#000,fill:#ff9800,stroke:#4caf50,stroke-width:3px
  style CommunityRelease color:#000,fill:#ff9800,stroke:#ffee58,stroke-width:3px
```








***



```mermaid
flowchart LR
  %% Components
  Preparation@{shape: circle, label: "Preparation"}
  Refactor@{shape: rounded, label: "Refactor"}
  Development@{shape: rounded, label: "Development"}
  Release@{shape: rounded, label: "Release"}
  %% Layout
  Preparation --> Refactor --> Development --> Release
  %% Styles
  style Preparation color:#FFF,stroke:#42a5f5,stroke-width:3px
  style Refactor color:#000,fill:#ff9800,stroke:#42a5f5,stroke-width:3px
  style Development color:#000,fill:#ff9800,stroke:#42a5f5,stroke-width:3px
  style Release color:#000,fill:#ff9800,stroke:#42a5f5,stroke-width:3px
```









```mermaid
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
  DailyDevelopment --> ReleaseCandidate --> StableRelease --> CommunityRelease
  StableRelease --> MonthlyArchive
  %% Styles
  style DailyDevelopment color:#000,fill:#ff9800,stroke:#42a5f5,stroke-width:3px
  style Documentation color:#000,fill:#ff9800,stroke:#9c27b0,stroke-width:3px
  style MonthlyArchive color:#000,fill:#ff9800,stroke:#b71c1c,stroke-width:3px
  style ReleaseCandidate color:#000,fill:#ff9800,stroke:#26c6da,stroke-width:3px
  style StableRelease color:#000,fill:#ff9800,stroke:#4caf50,stroke-width:3px
  style CommunityRelease color:#000,fill:#ff9800,stroke:#ffee58,stroke-width:3px
```




During monthly development and testing:

* The current development branches are archived
* 
* The existing codebase is refactored and cleaned up
* New functionality is added, and existing functionality is updated/modified
* Bugs are squished
* Code is refactored
* New documentation is added, and existing documentation is updated/modified
* Iterative testing is done in a non-production environment
