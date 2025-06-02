<!-- u250602 -->

<!--
  I'm sure the Mermaid.js code here looks awful, but it was a real pain to get
  all it looking the way it does, so I don't plan on touching it going forward.

  The rest of the document will be updated normally.
-->

# Daily workflow

This is the daily workflow for all Tingen projects.

<div align="center">

```mermaid
flowchart TB 
  %% Components
  Start@{shape: sm-circ, label: ""}
  Preparation@{shape: rounded, label: "Preparation"}
  Development@{shape: rounded, label: "Development"}
  Finish@{shape: rounded, label: "Finish"}
  %% Subgraphs
  %% Layout
  Start --> Preparation:::R2_ --> Development:::P2_ --> Finish:::U2_
  %% Styles
  classDef P2_ stroke:#f5eef8,stroke-width:3px,fill:#af7ac5,color:#f5eef8
  classDef R2_ stroke:#f9ebea,stroke-width:3px,fill:#CD6155,color:#f9ebea
  classDef U2_ stroke:#eaf2f8,stroke-width:3px,fill:#5499c7,color:#eaf2f8
  classDef Hidden display: none;
```

</div>

## Preparation

<div align="center">

```mermaid
flowchart TB
  %% Components
  Start@{shape: sm-circ, label: ""}
  AutoHotKey@{shape: rounded, label: "Start\nAutoHotkey"}
  VSCodeWorkspaces@{shape: rounded, label: "Open VS Code\nworkspaces"}
  VS2022Solutions@{shape: rounded, label: "Open Visual Studio\nsolutions"}
  GitHubDesktop@{shape: rounded, label: "Start GitHub\nDesktop"}
  Development@{shape: rounded, label: "Development"}
  Finish@{shape: rounded, label: "Finish"}
  %% Subgraphs
  %% Layout
  Start --> AutoHotKey:::R2_ --> VSCodeWorkspaces:::R2_ --> VS2022Solutions:::R2_  -->GitHubDesktop:::R2_ --> Development:::P2_ --> Finish:::U2_
  %% Styles
  classDef P2_ stroke:#f5eef8,stroke-width:3px,fill:#af7ac5,color:#f5eef8
  classDef R2_ stroke:#f9ebea,stroke-width:3px,fill:#CD6155,color:#f9ebea
  classDef U2_ stroke:#eaf2f8,stroke-width:3px,fill:#5499c7,color:#eaf2f8
  classDef Hidden display: none;
```

</div>

## Development

<div align="center">

```mermaid
flowchart TB 
  %% Components
  Start@{shape: sm-circ, label: ""}
  Preparation@{shape: rounded, label: "Preparation"}
  subgraph _Development ["Development"]
    direction LR
      DeployToUat@{shape: rounded, label: "Deploy To UAT"}
      Test@{shape: diamond, label: "Test"}
      subgraph _SourceCodeModifications ["Source code modifications"]
        direction LR
        %% Components
        NewFunctionality@{shape: rounded, label: "New\nfunctionality"}
        UpdateExistingFunctionality@{shape: rounded, label: "Update existing\nfunctionality"}
        BugFixes@{shape: rounded, label: "Bug fixes"}
        Refactoring@{shape: rounded, label: "Refactoring"}
        Other@{shape: rounded, label: "Other"}
        NewFunctionality:::P8_ --> UpdateExistingFunctionality:::P8_ --> BugFixes:::P8_ --> Refactoring:::P8_ --> Other:::P8_
      end
      subgraph _Documentation ["Documentation"]
        direction TB
        %% Components
        SourceCodeDocumentation@{shape: docs, label: "Source code documentation"}
        ProjectManual@{shape: docs, label: "Project Manual"}
        APIDocumentation@{shape: docs, label: "API documentation"}
        DevMiscDocumentation@{shape: docs, label: "Development\\miscellaneous\ndocumentation"}
        SourceCodeDocumentation:::P8_ ~~~ ProjectManual:::P8_ ~~~ APIDocumentation:::P8_ ~~~ DevMiscDocumentation:::P8_
      end
      _SourceCodeModifications:::P8_ --> DeployToUat:::P4_ --> Test:::P4_ 
  end
  Finish@{shape: rounded, label: "Finish"}
  %% Subgraphs
  %% Layout
  Start --> Preparation:::R2_ --> _Development:::P2_ --> Finish:::U2_
  Test -- Fail --> _SourceCodeModifications
  Test -- Success --> _Documentation:::P1_
  _Documentation --> _SourceCodeModifications:::P1_
  %% Styles
  classDef G9_ stroke:#145a32,stroke-width:3px,fill:#145a32,color:#e9f7ef
  classDef P0_ stroke:#f5eef8,stroke-width:3px,fill:#f5eef8,color:#512e5f
  classDef P1_ stroke:#f5eef8,stroke-width:3px,fill:#d7bde2,color:#512e5f
  classDef P2_ stroke:#f5eef8,stroke-width:3px,fill:#af7ac5,color:#f5eef8
  classDef P3_ stroke:#f5eef8,stroke-width:3px,fill:#884ea0,color:#f5eef8
  classDef P4_ stroke:#f5eef8,stroke-width:3px,fill:#512e5f,color:#f5eef8
  classDef P5_ stroke:#512e5f,stroke-width:3px,fill:#f5eef8,color:#512e5f
  classDef P6_ stroke:#512e5f,stroke-width:3px,fill:#d7bde2,color:#512e5f
  classDef P7_ stroke:#512e5f,stroke-width:3px,fill:#af7ac5,color:#f5eef8
  classDef P8_ stroke:#512e5f,stroke-width:3px,fill:#884ea0,color:#f5eef8
  classDef P9_ stroke:#512e5f,stroke-width:3px,fill:#512e5f,color:#f5eef8
  classDef R2_ stroke:#f9ebea,stroke-width:3px,fill:#CD6155,color:#f9ebea
  classDef R9_ stroke:#641e16,stroke-width:3px,fill:#641e16,color:#f9ebea
  classDef U2_ stroke:#eaf2f8,stroke-width:3px,fill:#5499c7,color:#eaf2f8
  classDef Hidden display: none;
  linkStyle 0 stroke:#000000 ,stroke-width:4px,color:red;
  linkStyle 1 stroke:#000000 ,stroke-width:4px,color:red;
  linkStyle 2 stroke:#000000 ,stroke-width:4px,color:red;
  linkStyle 3 stroke:#000000 ,stroke-width:4px,color:red;
  linkStyle 12 stroke:#641e16 ,stroke-width:4px,color:red;
  linkStyle 13 stroke:#145a32 ,stroke-width:4px,color:green;

```
