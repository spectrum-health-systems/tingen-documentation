<!-- u250304 -->

> Last updated: March 4, 2025

<div align="center">

![logo](/.github/image/logo/TingenDevelopmentDocumentation_logo_320x420.png)

  <h1>Workflows</h1>

</div>

<br>

<div align="center">

```mermaid
flowchart LR
  %% Components
  Start@{shape: sm-circ, label: "Start the workflow\n[sm-circ]"}
  Archive@{shape: rounded, label: "Archive"}
  UpdateComponents@{shape: rounded, label: "Update\ncomponents"}
  Development@{shape: rounded, label: "Development"}
  Release@{shape: circ, label: "Release"}
  %% Layout
  Start -->Archive:::R0_ --> UpdateComponents:::P0_ --> Development:::U0_ --> Release:::G2_

  %% Styles
  classDef R0_ stroke:#f9ebea,stroke-width:3px,fill:#f9ebea,color:#641e16
  classDef P0_ stroke:#f5eef8,stroke-width:3px,fill:#f5eef8,color:#512e5f
  classDef U0_ stroke:#eaf2f8,stroke-width:3px,fill:#eaf2f8,color:#154360
  classDef G2_ stroke:#e9f7ef,stroke-width:3px,fill:#52be80,color:#e9f7ef
  classDef Y5_ stroke:#7d6608,stroke-width:3px,fill:#fef9e7,color:#7d6608
  classDef E5_ stroke:#784212,stroke-width:3px,fill:#fdf2e9,color:#784212
  %% Styles - Global
  classDef Hidden display: none;
```

</div>

<br>

***

<!--
ARCHIVE WORKFLOW
This HTML is ugly, but needs to be this way to work.
-->

<details>
  <summary>

 ```mermaid
  flowchart LR
    %% Components
    Archive@{shape: rounded, label: "Archive"}
    ArchiveRepostitories@{shape: rounded, label: "Archive\nRepositories"}
    %% Layout
    Start:::Hidden -.->Archive:::R5_ --> ArchiveRepostitories:::R1_ -.-> Continue:::Hidden
    %% Styles
    classDef R5_ stroke:#641e16,stroke-width:3px,fill:#f9ebea,color:#641e16,font-size:8pt 
    classDef R1_ stroke:#f9ebea,stroke-width:3px,fill:#E6B0AA,color:#641e16
    %% Styles - Global
    classDef Hidden display: none;
  ```

</summary>

## Archive repositories

Create a `YY.DD.##-development+final` branch for each of the following repositories:

* Tingen-WebService
* Outpost31
* Tingen-Documentation

</details>

<br>

<!--
UPDATE COMPONENTS WORKFLOW
This HTML is ugly, but needs to be this way to work.
-->

<details>
  <summary>

  ```mermaid
  flowchart LR
    %% Components
    UpdateComponents@{shape: rounded, label: "Update\ncomponents"}
    UpdateAutoHotKey@{shape: rounded, label: "Update\nAutoHotKey script"}
    UpdateSandCastleProfiles@{shape: rounded, label: "Update\nSandcastle profiles"}
    UpdateSourceCode@{shape: rounded, label: "Update\nsource code"}
    UpdateDocumentation@{shape: rounded, label: "Update\ndocumentation"}
    %% Layout
    UpdateComponents:::P5_ --> UpdateAutoHotKey:::P6_ --> UpdateSandCastleProfiles:::P6_ -->  UpdateSourceCode:::P6_ --> UpdateDocumentation:::P6_
    %% Styles
    classDef R5_ stroke:#641e16,stroke-width:3px,stroke-dasharray: 5 5,fill:#f9ebea,color:#641e16,font-size:8pt
    classDef P5_ stroke:#512e5f,stroke-width:3px,fill:#f5eef8,color:#512e5f
    classDef P6_ stroke:#512e5f,stroke-width:3px,fill:#d7bde2,color:#512e5f
    %% Styles - Global
    classDef Hidden display: none;
  ```

  </summary>

### Update the AutoHotKey script

Update the following components of the AutoHotkey script:

* ALT+CTRL+SHIFT+P
* ALT+CTRL+SHIFT+R
* ALT+CTRL+SHIFT+V
  
### Update Sandcastle profiles

Update the Sandcastle "Help file version" in the following Sandcastle profiles:

* Tingen
* Outpost31

## Update the source code

### AssemblyInfo.cs

Update the following `AssemblyInfo.cs` files with the current version number:

* Tingen_development/Properties/AssemblyInfo.cs
* Outpost31/Properties/AssemblyInfo.cs
  
### Class file headers

Update the file headers for the following files:

* Tingen.Tingen.asmx.cs
* Outpost31.WelcomeToOutpost31.cs

### The `tnBuild` value

Update `tnBuild` value in `Core.Session.TingenSession.BuildStaticVars()` to the current `YYMMDD.HHMM` value.

For example:

```csharp
return new Dictionary<string, string>
{
    { "tnBuild",              "241205.0944" },
    { "avSystemCode",         "UAT" },
    { "tnDataRoot",           @"C:\TingenData" },
    { "tnConfigFileName",     "Tingen.config" },
    { "ntstSecurityFileName", "NtstSecurity.config" }
};
```

## Update the documentation

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

</details> <!-- PREPARATION WORKFLOW -->

<!--
REFACTOR WORKFLOW
This HTML is ugly, but needs to be this way to work.
-->

<details>
<summary> Refactor workflow

```mermaid
flowchart LR
  %% Components
  Preparation@{shape: rounded, label: "Preparation"}
  Refactor@{shape: rounded, label: "Refactor"}
  Development@{shape: rounded, label: "Development"}
  Release@{shape: rounded, label: "Release"}
  %% Layout
  Preparation:::S02 --> Refactor --> Development:::S02 --> Release:::S02
  %% Styles
  classDef Refactor stroke:#154360,stroke-width:3px,fill:#a9cce3,color:#154360,font-size:16pt
  classDef S02 stroke:#000000,stroke-width:3px,fill:#7b7d7d,color:#000000,font-size:10pt
  class Refactor Refactor
  class Preparation,Development,Release GreyedOut
```

</summary>

During the refactor phase the following components are cleand up and/or refactored:

* Source code
* Source code comments
* XML documentation
* Documentation

</details> <!-- REFACTOR WORKFLOW -->

<!--
DEVELOPMENT WORKFLOW
This HTML is ugly, but needs to be this way to work.
-->

<details>
<summary> Development workflow

```mermaid
flowchart LR
  %% Components
  Preparation@{shape: rounded, label: "Preparation"}
  Refactor@{shape: rounded, label: "Refactor"}
  Development@{shape: rounded, label: "Development"}
  Release@{shape: rounded, label: "Release"}
  %% Layout
  Preparation --> Refactor --> Development --> Release
  %% Styles
  classDef Development stroke:#145a32,stroke-width:3px,fill:#a9dfbf,color:#145a32,font-size:16pt
  classDef GreyedOut stroke:#000000,stroke-width:3px,fill:#7b7d7d,color:#ffffff,font-size:10pt
  class Development Development
  class Preparation,Refactor,Release GreyedOut
```

</summary>

Development consists of:

* Determining new functionality
* Adding new functionality
* Updating/modifying current functionality
* Testing
* Squishing bugs
* Adding new documentation
* Updating/modifying current documentation

<div align="center">

```mermaid
---
title: Development overview
---
flowchart LR
  %% Components
  Development@{shape: rounded, label: "Development"}
  DeployToUat@{shape: rounded, label: "Deploy To UAT"}
  Document@{shape: docs, label: "Documentation"}
  Test@{shape: diamond, label: "Test"}
  Release@{shape: rounded, label: "Release"}
  %% Layout
  Development -.-> Document
  Development --> DeployToUat --> Test
  Test -- Fail --> Development
  Test -- Success --> Release
  %% Styles
  classDef Development stroke:#00000,stroke-width:3px,stroke-dasharray: 5 5,fill:#a9dfbf,color:#145a32
  classDef DeployToUat stroke:#145a32,stroke-width:3px,fill:#52be80,color:#e9f7ef
  classDef Document stroke:#6e2c00,stroke-width:3px,fill:#edbb99,color:#6e2c00
  classDef Test stroke:#e9f7ef,stroke-width:3px,fill:#145a32,color:#e9f7ef
  classDef Release stroke:#7d6608,stroke-width:3px,fill:#f9e79f,color:#7d6608
  class Development Development
  class DeployToUat DeployToUat
  class Test Test
  class Document Document
  class Release Release
  linkStyle 3 stroke:#A93226,stroke-width:3px, color: pink;
  linkStyle 4 stroke:#145a32,stroke-width:3px
```

</div>

</details> <!-- DEVELOPMENT WORKFLOW -->

<details>
  <summary>Release workflow

```mermaid
flowchart LR
  %% Components
  Preparation@{shape: rounded, label: "Preparation"}
  Refactor@{shape: rounded, label: "Refactor"}
  Development@{shape: rounded, label: "Development"}
  Release@{shape: rounded, label: "Release"}
  %% Layout
  Preparation --> Refactor --> Development --> Release
  %% Styles
  classDef Release stroke:#7d6608,stroke-width:3px,fill:#f9e79f,color:#7d6608,font-size:16pt
  classDef GreyedOut stroke:#000000,stroke-width:3px,fill:#7b7d7d,color:#ffffff,font-size:10pt
  class Release Release
  class Preparation,Refactor,Development GreyedOut
```
  
</summary>


</details> <!-- RELEASE WORKFLOW -->

***




<div align="center">

```mermaid
---
title: Release overview
---
flowchart LR
  %% Components
  Release@{shape: rounded, label: "Release"}
  ReleaseCandidate@{shape: rounded, label: "Release\nCandidate"}
  Stable@{shape: rounded, label: "Stable\nrelease"}
  Community@{shape: rounded, label: "Community\nrelease"}
  %% Layout
  Release --> ReleaseCandidate
  ReleaseCandidate --> Stable
  Stable --> Community
  %% Styles
  classDef Release stroke:#000000,stroke-width:3px,stroke-dasharray: 5 5,fill:#f9e79f,color:#7d6608
  classDef ReleaseCandidate stroke:#7d6608,stroke-width:3px,fill:#f4d03f,color:#7d6608
  classDef Stable stroke:#fef9e7,stroke-width:3px,fill:#d4ac0d,color:#fef9e7
  classDef CommunityRelease stroke:#7d6608,stroke-width:3px,fill:#f9e79f,color:#7d6608
  class Release Release
  class ReleaseCandidate ReleaseCandidate
  class Stable Stable
```

</div>


### Release candidate

### Stable

### Community


- December 20: Abatab WinterYY
- March 20: Abatab SpringYY
- June 20: Abatab SummerYY
- September 20: Abatab AutumnYY

For example: `Abatab Autumn23`










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