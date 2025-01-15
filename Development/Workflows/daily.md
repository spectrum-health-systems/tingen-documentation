<!-- u250114 -->

> Last updated: January 14, 2025

<div align="center">

![logo](../../.github/Images/Logos/TingenDevelopmentDocumentation-320x425.png)

 <h1>Daily development</h1>

</div>

```mermaid
flowchart LR
  %% Components
  Preparation@{shape: circle, label: "Preparation"}
  subgraph DailyDevelopment["Daily development cycle"]
    direction LR
    %% Components
    Development@{shape: rounded, label: "Development"}
    DeployToUat@{shape: rounded, label: "Deploy To UAT"}
    Testing@{shape: diamond, label: "Testing"}
    %% Layout
    Development --> DeployToUat --> Testing
    Testing -- Failure --> Development
  end
  %% Components
  ReleaseCandidate@{shape: stadium, label: "Release candidate"}
  %% Layout
  Preparation --> DailyDevelopment   
  Testing -.- Success -.-> ReleaseCandidate
  %% Styles
  style Preparation color:#FFF,stroke:#42a5f5,stroke-width:3px
  style DailyDevelopment color:#FFF,stroke:#42a5f5,stroke-width:3px
  style Development color:#000,fill:#ff9800,stroke:#42a5f5,stroke-width:3px
  style DeployToUat color:#000,fill:#ff9800,stroke:#42a5f5,stroke-width:3px
  style Testing color:#000,fill:#ff9800,stroke:#42a5f5,stroke-width:3px
  style ReleaseCandidate color:#000,fill:#ff9800,stroke:#26c6da,stroke-width:3px, stroke-dasharray: 5 5
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
