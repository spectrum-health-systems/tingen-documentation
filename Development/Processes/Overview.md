<!-- u241104 -->

<div align="center">

  ![BranchWarning](https://img.shields.io/badge/WORK%20IN%20PROGRESS-yellow?style=for-the-badge)

  ![logo](../../.github/Images/Logos/TingenDocumentation-232x308.png)

  <h1>
    Tingen development processes overview
  </h1>

</div>

# Overview

This is an overview of the Tingen development processes.

# Tingen development

The Tingen web service is comprised of the following components:

```mermaid
flowchart TB
  subgraph DocumentationComponents["Documentation components"]
      direction TB
      %% Components
      DevelopmentDocumentationComponent@{shape: doc, label: "Development documentation"}
      ApiDocumentationComponent@{shape: doc, label: "API Documentation"}
      ManualComponent@{shape: doc, label: "Tingen Manual"}
      %% Layout
      DevelopmentDocumentationComponent ~~~ ApiDocumentationComponent ~~~ ManualComponent
  end
  subgraph WebServiceComponents["Web service components"]
      direction TB
      %% Components
      TingenComponent@{shape: rect, label: "**Tingen**<br/>The web service<br/>entry point"}
      Outpost31Component@{shape: rect, label: "**Outpost31**<br/>The web service logic"}
      %% Layout
      TingenComponent --> Outpost31Component
  end
  %% Styles #f7dc6f #f5b041 #b9770e
  style WebServiceComponents color:#FFF,fill:#2c3e50,stroke:#FFF,stroke-width:2px
  style TingenComponent color:#FFF,fill:sienna,stroke:#FFF,stroke-width:2px
  style Outpost31Component color:#FFF,fill:sienna,stroke:#FFF,stroke-width:2px
  style DocumentationComponents color:#FFF,fill:#2c3e50,stroke:#FFF,stroke-width:2px
  style DevelopmentDocumentationComponent color:#000,fill:#f7dc6f,stroke:#ba4a00,stroke-width:2px
  style ApiDocumentationComponent color:#000,fill:#f5b041,stroke:#ba4a00,stroke-width:2px
  style ManualComponent color:#FFF,fill:#b9770e,stroke:#ba4a00,stroke-width:2px
  %% Links 
  click TingenComponent "https://github.com/spectrum-health-systems/Tingen_development"
  click Outpost31Component "https://github.com/spectrum-health-systems/Outpost31"
```

## Development timelines

### Daily development

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

### Release candidates

```mermaid
flowchart LR
  %% Components
  DailyDevelopment@{shape: rect, label: "Daily development"}
  TestingSuccessful@{shape: rounded, label: "Testing (successful)"}
  ReleaseCandidate@{shape: stadium, label: "Release candidate"}
  %% Layout
  DailyDevelopment --> TestingSuccessful --> ReleaseCandidate
  %% Styles 
  style DailyDevelopment color:#FFF,fill:#16a085,stroke:#FFF,stroke-width:2px
  style TestingSuccessful color:#FFF,fill:steelblue,stroke:#FFF,stroke-width:2px
  style ReleaseCandidate color:#000,fill:#af7ac5,stroke:#FFF,stroke-width:2px
```

### Stable releases

```mermaid
flowchart LR
  %% Components
  ReleaseCandidate@{shape: stadium, label: "Release Candidate"}
  StableRelease@{shape: stadium, label: "Stable release"}
  %% Layout
  ReleaseCandidate --x StableRelease
  %% Styles 
  style ReleaseCandidate color:#000,fill:#af7ac5,stroke:#FFF,stroke-width:2px
  style StableRelease color:#FFF,fill:#8e44ad,stroke:#FFF,stroke-width:2px
```

### Community releases

```mermaid
flowchart LR
  %% Components
  StableRelease@{shape: stadium, label: "Stable release"}
  CommunityRelease@{shape: stadium, label: "Community release"}
  %% Layout
  StableRelease --x CommunityRelease
  %% Styles 
  style StableRelease color:#FFF,fill:#8e44ad,stroke:#FFF,stroke-width:2px
  style CommunityRelease color:#FFF,fill:#512e5f,stroke:#FFF,stroke-width:2px
```

### Monthly archives

```mermaid
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

# Documentation process

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

## Release candidate documentation

```mermaid
flowchart LR
  %% Components
  ReleaseCandidate@{shape: stadium, label: "Release candidate"}
  ApiDocumentation@{shape: doc, label: "API Documentation"}
  Manual@{shape: doc, label: "Tingen Manual"}
  %% Layout
  ReleaseCandidate -.-> ApiDocumentation
  ReleaseCandidate -.-> Manual
  %% Styles
  style ReleaseCandidate color:#000,fill:#af7ac5,stroke:#FFF,stroke-width:2px
  style ApiDocumentation color:#000,fill:#f5b041,stroke:#ba4a00,stroke-width:2px
  style Manual color:#FFF,fill:#b9770e,stroke:#ba4a00,stroke-width:2px
```

## Development process

Development of Tingen.

```mermaid
flowchart LR
  %% Components
  DailyDevelopment@{shape: rect, label: "Daily development"}
  DeployToUat@{shape: rounded, label: "Deploy To UAT"}
  Testing@{shape: diamond, label: "Testing"}
  ReleaseCandidate@{shape: stadium, label: "Release candidate"}
  StableRelease@{shape: stadium, label: "Stable release"}
  CommunityRelease@{shape: stadium, label: "Community release"}
  MonthlyArchive@{shape: stadium, label: "Monthly Archive"}
  DevelopmentDocumentation@{shape: doc, label: "Development documentation"}
  ApiDocumentation@{shape: doc, label: "API Documentation"}
  Manual@{shape: doc, label: "Tingen Manual"}
  %% Layout
  DailyDevelopment --> DeployToUat --> Testing
  Testing -- Failure --> DailyDevelopment
  Testing -- Success --> ReleaseCandidate
  DailyDevelopment -.-> DevelopmentDocumentation
  DailyDevelopment -.-> Manual
  ReleaseCandidate --> StableRelease
  ReleaseCandidate -.-> ApiDocumentation
  ReleaseCandidate -.-> Manual
  StableRelease --> CommunityRelease
  StableRelease --> MonthlyArchive
  %% Styles
  style DailyDevelopment color:#FFF,fill:#16a085,stroke:#FFF,stroke-width:2px
  style DeployToUat color:#FFF,fill:grey,stroke:#FFF,stroke-width:2px
  style Testing color:#FFF,fill:steelblue,stroke:#FFF,stroke-width:2px
  style ReleaseCandidate color:#000,fill:#af7ac5,stroke:#FFF,stroke-width:2px
  style StableRelease color:#FFF,fill:#8e44ad,stroke:#FFF,stroke-width:2px
  style CommunityRelease color:#FFF,fill:#512e5f,stroke:#FFF,stroke-width:2px
  style MonthlyArchive color:#FFF,fill:#0e6655,stroke:#FFF,stroke-width:2px
  style DevelopmentDocumentation color:#000,fill:#f7dc6f,stroke:#ba4a00,stroke-width:2px
  style ApiDocumentation color:#000,fill:#f5b041,stroke:#ba4a00,stroke-width:2px
  style Manual color:#FFF,fill:#b9770e,stroke:#ba4a00,stroke-width:2px
```
