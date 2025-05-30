<!-- u250530 -->

<!--
  I'm sure the Mermaid.js code here looks awful, but it was a real pain to get
  all it looking the way it does, so I don't plan on touching it going forward.

  The rest of the document will be updated normally.
-->

[View [Markdown version](https://github.com/spectrum-health-systems/tingen-documentation/blob/main/docs/development/workflows.md)]

# Workflows

[Sandcastle/GitHub Pages](#sandcastlegithub-pages)
[Tingen Web Service](#tingen-web-service)

## Sandcastle/GitHub pages

<div align="center">

```mermaid
flowchart TB
  %% Components
  Start@{shape: sm-circ, label: "Start the workflow\n[sm-circ]"}
  CleanSolution@{shape: rounded, label: "Clean Visual Studio solution"}
  BuildSolution@{shape: rounded, label: "Build  Visual Studio solution"}
  BuildSandcastle@{shape: rounded, label: "Build Sandcastle documentation"}
  CommitChanges@{shape: rounded, label: "Commit changes to\nTingen-Documentation repository"}
  DeployPages@{shape: rounded, label: "Deploy GitHub pages"}

  %% Layout
  Start --> CleanSolution:::R2_ --> BuildSolution:::R2_ --> BuildSandcastle:::U2_ --> CommitChanges:::G2_ --> DeployPages:::G2_
  %% Styles
  classDef R2_ stroke:#f9ebea,stroke-width:3px,fill:#CD6155,color:#f9ebea
  classDef P2_ stroke:#f5eef8,stroke-width:3px,fill:#af7ac5,color:#f5eef8
  classDef U2_ stroke:#eaf2f8,stroke-width:3px,fill:#5499c7,color:#eaf2f8
  classDef G2_ stroke:#e9f7ef,stroke-width:3px,fill:#52be80,color:#e9f7ef
  classDef Hidden display: none;
```

***

# Tingen Web Service

```mermaid


flowchart TB
  %% Components
  Avatar@{shape: circ, label: "Avatar"}
  TingenWebService.asmx.cs@{shape: rounded, label: "TingenWebService.asmx.cs"}
  InitNewSession@{shape: rounded, label: "Initialize\nnew (empty) session"}

  %% Subgraph - TngnSession.New
  subgraph TngnSession.New ["TngnSession.New()"]
    direction TB

    %% Subgraph - Runtime.RuntimeSettings.New
    subgraph Runtime.RuntimeSettings.New ["Runtime.RuntimeSettings.New()"]
      direction LR

      %% Components
      SetBuild@{shape: rounded, label: "Set\nTngnBuild"}
      SetSystemCode@{shape: rounded, label: "Set\nTngnSystemCode"}
      SetTngnDataPath@{shape: rounded, label: "Set\nTngnDataPath"}
      SetMode@{shape: rounded, label: "Set\nTngnMode"}
      SetDateStamp@{shape: rounded, label: "Set\nDateStamp"}
      SetTimeStamp@{shape: rounded, label: "Set\nTimeStamp"}

      %% Layout
      SetBuild --> SetSystemCode --> SetMode --> SetDateStamp --> SetTimeStamp
    
    end
    %% Subgraph - Runtime.RuntimeSettings.New

    subgraph TngnConfiguration.New ["Runtime.Configuration.New()"]
      direction LR
      %%SetVersion@{shape: rounded, label: "Set\nTngnVersion"}
      %%SetBuild@{shape: rounded, label: "Set\nTngnBuild"}
      %%SetSystemCode@{shape: rounded, label: "Set\nngnSystemCode"}
      %%SetMode@{shape: rounded, label: "Set\nTngnMode"}
      SetVersion --> SetBuild@{shape: rounded, label: "Set TngnBuild"} --> SetSystemCode@{shape: rounded, label: "Set TngnSystemCode"} --> SetMode@{shape: rounded, label: "Set TngnMode"} --> SetDatestamp@{shape: rounded, label: "Set Datestamp"} --> SetTimeStamp@{shape: rounded, label: "Set Timestamp"}
    end

    SetVersion@{shape: rounded, label: "Set\nTngnVersion"}
    SetBuild@{shape: rounded, label: "Set\nTngnBuild"}
    SetSystemCode@{shape: rounded, label: "Set\nngnSystemCode"}
    SetMode@{shape: rounded, label: "Set\nTngnMode"}
    SetDatestamp@{shape: rounded, label: "Set\nDatestamp"}
    SetTimeStamp@{shape: rounded, label: "Set\nTimestamp"}

    SetVersion --> SetBuild@{shape: rounded, label: "Set TngnBuild"} --> SetSystemCode@{shape: rounded, label: "Set TngnSystemCode"} --> SetMode@{shape: rounded, label: "Set TngnMode"} --> SetDatestamp@{shape: rounded, label: "Set Datestamp"} --> SetTimeStamp@{shape: rounded, label: "Set Timestamp"}

  end 
  %% Subgraph - TngnSession.New

  subgraph Runtime.Spin.Up ["Runtime.Spin.Up()"]
    direction TB


  
    subgraph Runtime.RuntimeSettings.AreValid ["Runtime.RuntimeSettings.AreValid()"]
      direction LR
      ValidateMode@{shape: rounded, label: "Validate\nTngnMode"}
      ValidateSystemCode@{shape: rounded, label: "Validate\nTngnSystemCode"}
      ValidateBuild@{shape: rounded, label: "Validate\nTngnBuild"}

      ValidateMode@{shape: rounded, label: "Validate\nTngnMode"} --> ValidateSystemCode@{shape: rounded, label: "Validate\nTngnSystemCode"} --> ValidateBuild@{shape: rounded, label: "Validate\nTngnBuild"}
    end 
  
    Runtime.RuntimeSettings.Load --> Runtime.RuntimeSettings.AreValid

  end 

  Avatar --> TingenWebService.asmx.cs --> InitNewSession
  InitNewSession --> TngnSession.New



```