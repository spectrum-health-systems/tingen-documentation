<!-- u250421 -->

<!--
  I'm sure the Mermaid.js code here looks awful, but it was a real pain to get
  all it looking the way it does, so I don't plan on touching it going forward.

  The rest of the document will be updated normally.
-->

> Last updated: May 21, 2025

<div align="center">

![logo](/.github/image/logo/TingenDevelopmentDocumentation_logo_320x420.png)

  <h1>Documentation workflows</h1>

</div>

<br>

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

</div>

<br>
