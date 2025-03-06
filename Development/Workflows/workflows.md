<!-- u250304 -->

> Last updated: March 4, 2025

<div align="center">

![logo](/.github/image/logo/TingenDevelopmentDocumentation_logo_320x420.png)

  <h1>Workflows</h1>

</div>

<br>

<div align="center">

```mermaid
flowchart TB
  %% Components
  Start@{shape: sm-circ, label: "Start the workflow\n[sm-circ]"}
  Archive@{shape: rounded, label: "Archive"}
  UpdateComponents@{shape: rounded, label: "Update\ncomponents"}
  Development@{shape: rounded, label: "Development"}
  Release@{shape: circ, label: "Release"}

  %% Subgraphs
  %% (none)

  %% Layout
  Start --> Archive:::R0_ --> UpdateComponents:::P0_ --> Development:::U0_ --> Release:::G2_

  %% Styles
  classDef R0_ stroke:#f9ebea,stroke-width:3px,fill:#f9ebea,color:#641e16
  classDef P0_ stroke:#f5eef8,stroke-width:3px,fill:#f5eef8,color:#512e5f
  classDef U0_ stroke:#eaf2f8,stroke-width:3px,fill:#eaf2f8,color:#154360
  classDef G2_ stroke:#e9f7ef,stroke-width:3px,fill:#52be80,color:#e9f7ef
  classDef Hidden display: none;
```

</div>

<br>
<br>

<!--
ARCHIVE WORKFLOW
This HTML is ugly, but needs to be this way to work.
-->

# ARCHIVE

```mermaid
flowchart TB
  %% Components
  Start@{shape: sm-circ, label: "Start the workflow\n[sm-circ]"}
  UpdateComponents@{shape: rounded, label: "Update\ncomponents"}
  Development@{shape: rounded, label: "Development"}
  Release@{shape: circ, label: "Release"}

  %% Subgraphs
  subgraph _Archive ["Archive"]
    direction LR
      subgraph _ArchiveRepositories ["Repositories"]
        direction LR
        %% Components
        ArchiveTingenWebService@{shape: rounded, label: "Archive\nTingen\nWeb Service"}
        ArchiveOutpost31@{shape: rounded, label: "Archive\nOutpost31"}
        ArchiveTingenDocumentation@{shape: rounded, label: "Archive\nTingen\ndocumentation"}
        %% Layout
        RepoStart:::Hidden -.-> ArchiveTingenWebService:::R2_ --> ArchiveOutpost31:::R2_ --> ArchiveTingenDocumentation:::R2_ -.-> RepoEnd:::Hidden
      end
  end

  %% Layout
  Start --> _Archive:::R5_ --> UpdateComponents:::B7a_ --> Development:::B7a_ --> Release:::B7a_
  _ArchiveRepositories:::R6_
      
  %% Styles
  classDef R0_ stroke:#f9ebea,stroke-width:3px,fill:#f9ebea,color:#641e16
  classDef R1_ stroke:#f9ebea,stroke-width:3px,fill:#E6B0AA,color:#641e16
  classDef R2_ stroke:#f9ebea,stroke-width:3px,fill:#CD6155,color:#f9ebea
  classDef R5_ stroke:#641e16,stroke-width:3px,fill:#f9ebea,color:#641e16
  classDef R6_ stroke:#641e16,stroke-width:3px,fill:#E6B0AA,color:#641e16
  classDef B7a_ stroke:#7b7d7d,stroke-width:3px,fill:#000000,color:#7b7d7d,font-size: 10pt
  classDef Hidden display: none;
  linkStyle 0,1,2,3 stroke:#000000,stroke-width:1px
```

## Archive repositories

Create a `YY.DD.##-development+final` branch for each of the following repositories:

* Tingen-WebService
* Outpost31
* Tingen-Documentation

<br>

***

<br>

<!--
UPDATE COMPONENTS WORKFLOW
This HTML is ugly, but needs to be this way to work.
-->

# UPDATE COMPONENTS

```mermaid
flowchart TB 
  %% Components
  Start@{shape: sm-circ, label: "Start the workflow\n[sm-circ]"}
  Archive@{shape: rounded, label: "Archive"}
  Development@{shape: rounded, label: "Development"}
  Release@{shape: circ, label: "Release"}

  %% Subgraphs
  subgraph _UpdateComponents ["Update Components"]
    direction LR
    %% Components
    UpdateAutoHotKey@{shape: rounded, label: "Update\nAutoHotKey script"}
    UpdateSandCastleProfiles@{shape: rounded, label: "Update\nSandcastle profiles"}
    UpdateStart:::Hidden -.-> UpdateAutoHotKey:::P6_ --> UpdateSandCastleProfiles:::P6_ --> _UpdateSourceCode:::P6_ --> _UpdateDocumentation:::P6_ -.-> UpdateEnd:::Hidden
  end

  subgraph _UpdateSourceCode ["Update source code"]
    direction TB
    %% Components
    UpdateAssemblyInfo@{shape: rounded, label: "Update\nAssemblyInfo.cs"}
    UpdateClassHeaders@{shape: rounded, label: "Update\nclass headers"}
    UpdateTngnBuild@{shape: rounded, label: "Update\nTngnBuild value"}
    UpdateAssemblyInfo:::P7_ --> UpdateClassHeaders:::P7_ --> UpdateTngnBuild:::P7_
  end

  subgraph _UpdateDocumentation ["Update documentation"]
    direction TB
    %% Components
    UpdateTingenManual@{shape: docs, label: "Update\nTingen Manual"}
    UpdateAPIDocumentation@{shape: docs, label: "Update\nAPI documentation"}
    UpdateDevelopmentDocumentation@{shape: docs, label: "Update\nDevelopment documentation"}
    UpdateTingenManual:::P7_ --> UpdateAPIDocumentation:::P7_ --> UpdateDevelopmentDocumentation:::P7_
  end

  %% Layout
  Start --> Archive:::B7a_ --> _UpdateComponents:::P5_ --> Development:::B7a_ --> Release:::B7a_

  %% Styles
  classDef P0_ stroke:#f5eef8,stroke-width:3px,fill:#f5eef8,color:#512e5f
  classDef P1_ stroke:#f5eef8,stroke-width:3px,fill:#d7bde2,color:#512e5f
  classDef P2_ stroke:#f5eef8,stroke-width:3px,fill:#af7ac5,color:#f5eef8
  classDef P3_ stroke:#f5eef8,stroke-width:3px,fill:#884ea0,color:#f5eef8
  classDef P4_ stroke:#f5eef8,stroke-width:3px,fill:#512e5f,color:#f5eef8
  classDef P5_ stroke:#512e5f,stroke-width:3px,fill:#f5eef8,color:#512e5f
  classDef P5a_ stroke:#512e5f,stroke-width:3px,fill:#f5eef8,color:#512e5f,font-size:8p
  classDef P6_ stroke:#512e5f,stroke-width:3px,fill:#d7bde2,color:#512e5f
  classDef P7_ stroke:#512e5f,stroke-width:3px,fill:#af7ac5,color:#f5eef8
  classDef P8_ stroke:#512e5f,stroke-width:3px,fill:#884ea0,color:#f5eef8
  classDef P9_ stroke:#512e5f,stroke-width:3px,fill:#512e5f,color:#f5eef8
  classDef B7a_ stroke:#7b7d7d,stroke-width:3px,fill:#000000,color:#7b7d7d,font-size: 10pt
  classDef P5_ stroke:#f5eef8,stroke-width:3px,fill:#f5eef8,color:#512e5f
  classDef Hidden display: none;
  linkStyle 0,1,2,3,4,5,6,7,8 stroke:#000000,stroke-width:1px
```

## Update the AutoHotKey script

Update the following components of the AutoHotkey script:

* ALT+CTRL+SHIFT+P
* ALT+CTRL+SHIFT+R
* ALT+CTRL+SHIFT+V
  
## Update Sandcastle profiles

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

<br>

***

<br>

<!--
DEVELOPMENT WORKFLOW
This HTML is ugly, but needs to be this way to work.
-->

```mermaid
flowchart TB 
  %% Components
  Start@{shape: sm-circ, label: "Start the workflow\n[sm-circ]"}
  Archive@{shape: rounded, label: "Archive"}
  UpdateComponents@{shape: rounded, label: "Update\ncomponents"}
  Release@{shape: circ, label: "Release"}
  %% Subgraphs
  subgraph _Development ["Development"]
    direction TB
      DeployToUat@{shape: rounded, label: "Deploy To UAT"}
      Test@{shape: diamond, label: "Test"}
      subgraph _SourceCodeModifications ["Source code modifications"]
        direction TB
        %% Components
        NewFunctionality@{shape: rounded, label: "New\nfunctionality"}
        UpdateExistingFunctionality@{shape: rounded, label: "Update existing\nfunctionality"}
        BugFixes@{shape: rounded, label: "Bug fixes"}
        Refactor@{shape: rounded, label: "Refactoring"}
      end
      subgraph _Documentation ["Documentation"]
        direction LR
        %% Components
        TingenManual@{shape: docs, label: "Tingen Manual"}
        APIDocumentation@{shape: docs, label: "API documentation"}
        DevelopmentDocumentation@{shape: docs, label: "Development documentation"}
        TingenManual--> APIDocumentation --> DevelopmentDocumentation
      end
      StartDevelopment:::Hidden -.-> _SourceCodeModifications --> DeployToUat --> Test  
  end

  %% Layout
  Start --> Archive:::B7a_ --> UpdateComponents:::B7a_ --> _Development:::U5_ --> Release:::B7a_
  Test -- Fail --> _Development
  Test -- Success --> _Documentation
  _Documentation --> _Development
  %% Styles
  classDef U0_ stroke:#eaf2f8,stroke-width:3px,fill:#eaf2f8,color:#154360
  classDef U1_ stroke:#eaf2f8,stroke-width:3px,fill:#a9cce3,color:#154360
  classDef U2_ stroke:#eaf2f8,stroke-width:3px,fill:#5499c7,color:#eaf2f8
  classDef U3_ stroke:#eaf2f8,stroke-width:3px,fill:#2471a3,color:#eaf2f8
  classDef U4_ stroke:#eaf2f8,stroke-width:3px,fill:#154360,color:#eaf2f8
  classDef U5_ stroke:#154360,stroke-width:3px,fill:#eaf2f8,color:#154360
  classDef U6_ stroke:#154360,stroke-width:3px,fill:#a9cce3,color:#154360
  classDef U7_ stroke:#154360,stroke-width:3px,fill:#5499c7,color:#eaf2f8
  classDef U8_ stroke:#154360,stroke-width:3px,fill:#2471a3,color:#eaf2f8
  classDef U9_ stroke:#154360,stroke-width:3px,fill:#154360,color:#eaf2f8

  classDef R0_ stroke:#f9ebea,stroke-width:3px,fill:#f9ebea,color:#641e16
  classDef P5_ stroke:#f5eef8,stroke-width:3px,fill:#f5eef8,color:#512e5f
  classDef P5a_ stroke:#512e5f,stroke-width:3px,fill:#f5eef8,color:#512e5f,font-size:8pt 
  classDef P6_ stroke:#512e5f,stroke-width:3px,fill:#d7bde2,color:#512e5f
  classDef G2_ stroke:#e9f7ef,stroke-width:3px,fill:#52be80,color:#e9f7ef
  classDef B7a_ stroke:#7b7d7d,stroke-width:3px,fill:#000000,color:#7b7d7d,font-size: 10pt
  classDef Hidden display: none;
  %%linkStyle 0,1,2,3,4,5,6,7,8,9,10,11 stroke:#000000,stroke-width:1px
```












```mermaid
flowchart LR
  %% Components
  Development@{shape: rounded, label: "Development"}
  DeployToUat@{shape: rounded, label: "Deploy To UAT"}
  %% Document@{shape: docs, label: "Documentation"}
  Test@{shape: diamond, label: "Test"}
  %% Release@{shape: rounded, label: "Release"}
  %% Layout
  Start:::Hidden -.-> Development:::U5a_ -.-> DeployToUat:::U6_
  DeployToUat --> Test

  %% Styles
  classDef U5a_ stroke:#154360,stroke-width:3px,fill:#eaf2f8,color:#154360
  classDef U6_ stroke:#154360,stroke-width:3px,fill:#a9cce3,color:#154360
  linkStyle 3 stroke:#A93226,stroke-width:3px, color: pink;
  linkStyle 4 stroke:#145a32,stroke-width:3px
  %% Styles - Global
  classDef Hidden display: none;
```

During the refactor phase the following components are cleand up and/or refactored:

* Source code
* Source code comments
* XML documentation
* Documentation
Development consists of:

* Determining new functionality
* Adding new functionality
* Updating/modifying current functionality
* Testing
* Squishing bugs
* Adding new documentation
* Updating/modifying current documentation

<div align="center">



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

-->

```mermaid
flowchart LR
  classDef R0_ stroke:#f9ebea,stroke-width:3px,fill:#f9ebea,color:#641e16
  classDef R1_ stroke:#f9ebea,stroke-width:3px,fill:#E6B0AA,color:#641e16
  classDef R2_ stroke:#f9ebea,stroke-width:3px,fill:#CD6155,color:#f9ebea
  classDef R3_ stroke:#f9ebea,stroke-width:3px,fill:#A93226,color:#f9ebea
  classDef R4_ stroke:#f9ebea,stroke-width:3px,fill:#641e16,color:#f9ebea
  classDef R5_ stroke:#641e16,stroke-width:3px,fill:#f9ebea,color:#641e16
  classDef R6_ stroke:#641e16,stroke-width:3px,fill:#E6B0AA,color:#641e16
  classDef R7_ stroke:#641e16,stroke-width:3px,fill:#CD6155,color:#f9ebea
  classDef R8_ stroke:#641e16,stroke-width:3px,fill:#A93226,color:#f9ebea
  classDef R9_ stroke:#641e16,stroke-width:3px,fill:#641e16,color:#f9ebea
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