# Tingen Web Service

# FLOW

```mermaid
flowchart TB

  subgraph TingenWebService
    direction TB
    %% Components
    GetExeAsmName@{shape: rounded, label: "Get executing\nassembly name"}
    GetTngnVer@{shape: rounded, label: "Get Tingen Web\nService version"}
    CreateEmptyTngnSession@{shape: rounded, label: "Create empty\nTngnSession"}
    %% Layout
    GetExeAsmName --> GetTngnVer --> CreateEmptyTngnSession
    %% Styles
    class GetExeAsmName,GetTngnVer,CreateEmptyTngnSession Yellow
  end

  TingenWebService ==> Outpost31.Runtime.Spin.Up

  subgraph Outpost31
    direction TB

 subgraph Outpost.Runtime.Spin.Up
    direction TB

    subgraph Outpost.Configuration.RuntimeSettings
      direction LR
      %% Components
      Load
      AreValid@{shape: diamond}
      %% Layout
      Configuration.RuntimeSettings.Load --> Configuration.RuntimeSettings.AreValid
      Configuration.RuntimeSettings.AreValid --NO--> EXIT
      Configuration.RuntimeSettings.AreValid --YES --> Continue_Outpost31.Session.New("Continue to Outpost31.Session.New")
      %% Styles
    end

    %% Components
    Configuration.RuntimeSettings.Load
    Configuration.RuntimeSettings.AreValid@{shape: diamond}
    %% Layout
    Configuration.RuntimeSettings.Load --> Configuration.RuntimeSettings.AreValid
    Configuration.RuntimeSettings.AreValid --NO--> EXIT
    Configuration.RuntimeSettings.AreValid --YES --> Continue_Outpost31.Session.New("Continue to Outpost31.Session.New")
    %% Styles
  end
  end

 


  
  




  %% Components
  EXIT

  %% Layout


  %% Styles - Global
  classDef Hidden display: none;
  classDef Yellow color:#000000,fill:#EDDA74,stroke:#F6BE00,stroke-width:2px

```

  GetExecutingAssemblyName --> GetTngnVersion["Get TngnVersion"] --> CreateEmptyTngnSession["Create Empty TngnSession"] --> Outpost31.Runtime.Spin.Up

  subgraph Outpost31.Runtime.Spin.Up
    direction TB
    Configuration.RuntimeSettings.Load --> Configuration.RuntimeSettings.AreValid
    Configuration.RuntimeSettings.AreValid{"Configuration.RuntimeSettings.AreValid"} --NO--> EXIT
    Configuration.RuntimeSettings.AreValid --YES --> Continue_Outpost31.Session.New("Continue to Outpost31.Session.New")
  end

  Outpost31.Runtime.Spin.Up --> Outpost31.Session.New

  subgraph Outpost31.Session.New
    direction TB
    DoSomething --> DoSomethingElse
  end


# SNIPPETS

```
/// <summary>The executing Assembly name.</summary>
/// <remarks>A required component for writing log files, defined here so it can be used throughout the class.</remarks>
public static string ExeAsm { get; set; } = Assembly.GetExecutingAssembly().GetName().Name;
```

```
/* Logging infrastructure hasn't been initialized yet, so if you need to create a log file here, use a Primeval Log.
 */
```

# HEADERS

```
//  ██████  ██  ██ ██████ █████ ██████ █████  ██████   ██████  ███ 
//  ██  ██  ██  ██   ██   █████ ██  ██ ██████   ██        ███   ██ 
//  ██████  ██████   ██   ██    ██████  █████   ██     ██████   ██ 
//                             Outpost31.Core.Avatar.SystemCode.cs
//                                   Logic for Avatar System Codes
// u250227_code
// u250227_documentation
```


# COLORS

```mermaid
---
title: Red
---
flowchart LR
  %% Components
  Light@{shape: rounded, label: "Light"}
  LightString@{shape: brace, label: "#641E16,stroke-width:3px,fill:#E6B0AA,color:#641E16"}
  Mid@{shape: rounded, label: "Mid"}
  MidString@{shape: brace, label: "stroke:#641E16,stroke-width:3px,fill:#CD6155,color:#F9EBEA"}
  Dark@{shape: rounded, label: "Dark"}
  DarkString@{shape: brace, label: "stroke:#F9EBEA,stroke-width:3px,fill:#A93226,color:#F9EBEA"}
  %% Layout
  Light --> LightString
  Mid --> MidString
  Dark --> DarkString
  %% Styles
  classDef Light stroke:#641E16,stroke-width:3px,fill:#E6B0AA,color:#641E16
  classDef Mid stroke:#641E16,stroke-width:3px,fill:#CD6155,color:#F9EBEA
  classDef Dark stroke:#F9EBEA,stroke-width:3px,fill:#A93226,color:#F9EBEA
  class Light Light
  class Mid Mid
  class Dark Dark
```

```mermaid
---
title: Purple
---
flowchart LR
  %% Components
  Light@{shape: rounded, label: "Light"}
  LightString@{shape: brace, label: "stroke:#512e5f,stroke-width:3px,fill:#d7bde2,color:#512e5f "}
  Mid@{shape: rounded, label: "Mid"}
  MidString@{shape: brace, label: "stroke:#512e5f,stroke-width:3px,fill:#af7ac5,color:#f5eef8"}
  Dark@{shape: rounded, label: "Dark"}
  DarkString@{shape: brace, label: "stroke:#stroke:#f5eef8,stroke-width:3px,fill:#884ea0,color:#f5eef8"}
  %% Layout
  Light --> LightString
  Mid --> MidString
  Dark --> DarkString
  %% Styles
  classDef Light stroke:#512e5f,stroke-width:3px,fill:#d7bde2,color:#512e5f 
  classDef Mid stroke:#512e5f,stroke-width:3px,fill:#af7ac5,color:#f5eef8
  classDef Dark stroke:#f5eef8,stroke-width:3px,fill:#884ea0,color:#f5eef8
  class Light Light
  class Mid Mid
  class Dark Dark
```

```mermaid
---
title: Blue
---
flowchart LR
  %% Components
  Light@{shape: rounded, label: "Light"}
  LightString@{shape: brace, label: "stroke:#512e5f,stroke-width:3px,fill:#d7bde2,color:#512e5f"}
  Mid@{shape: rounded, label: "Mid"}
  MidString@{shape: brace, label: "stroke:#512e5f,stroke-width:3px,fill:#af7ac5,color:#f5eef8"}
  Dark@{shape: rounded, label: "Dark"}
  DarkString@{shape: brace, label: "stroke:#stroke:#f5eef8,stroke-width:3px,fill:#884ea0,color:#f5eef8"}
  %% Layout
  Light --> LightString
  Mid --> MidString
  Dark --> DarkString
  %% Styles
  classDef Light stroke:#154360,stroke-width:3px,fill:#a9cce3,color:#154360  
  classDef Mid stroke:#154360,stroke-width:3px,fill:#5499c7,color:#eaf2f8
  classDef Dark stroke:#eaf2f8,stroke-width:3px,fill:#2471a3,color:#eaf2f8
  class Light Light
  class Mid Mid
  class Dark Dark
```

```mermaid
---
title: Green
---
flowchart LR
  %% Components
  Light@{shape: rounded, label: "Light"}
  LightString@{shape: brace, label: "stroke:#145a32,stroke-width:3px,fill:#a9dfbf,color:#145a32"}
  Mid@{shape: rounded, label: "Mid"}
  MidString@{shape: brace, label: "stroke:#145a32,stroke-width:3px,fill:#52be80,color:#e9f7ef"}
  Dark@{shape: rounded, label: "Dark"}
  DarkString@{shape: brace, label: "stroke:#e9f7ef,stroke-width:3px,fill:#145a32,color:#e9f7ef"}
  %% Layout
  Light --> LightString
  Mid --> MidString
  Dark --> DarkString
  %% Styles
  classDef Light stroke:#145a32,stroke-width:3px,fill:#a9dfbf,color:#145a32  
  classDef Mid stroke:#145a32,stroke-width:3px,fill:#52be80,color:#e9f7ef
  classDef Dark stroke:#e9f7ef,stroke-width:3px,fill:#145a32,color:#e9f7ef
  class Light Light
  class Mid Mid
  class Dark Dark
```

```mermaid
---
title: Yellow
---
flowchart LR
  %% Components
  Light@{shape: rounded, label: "Light"}
  LightString@{shape: brace, label: "stroke:#7d6608,stroke-width:3px,fill:#f9e79f,color:#7d6608"}
  Mid@{shape: rounded, label: "Mid"}
  MidString@{shape: brace, label: "stroke:#7d6608,stroke-width:3px,fill:#f4d03f,color:#7d6608"}
  Dark@{shape: rounded, label: "Dark"}
  DarkString@{shape: brace, label: "stroke:#fef9e7,stroke-width:3px,fill:#d4ac0d,color:#fef9e7"}
  %% Layout
  Light --> LightString
  Mid --> MidString
  Dark --> DarkString
  %% Styles
  classDef Light stroke:#7d6608,stroke-width:3px,fill:#f9e79f,color:#7d6608  
  classDef Mid stroke:#7d6608,stroke-width:3px,fill:#f4d03f,color:#7d6608
  classDef Dark stroke:#fef9e7,stroke-width:3px,fill:#d4ac0d,color:#fef9e7
  class Light Light
  class Mid Mid
  class Dark Dark
```

```mermaid
---
title: Orange
---
flowchart LR
  %% Components
  Light@{shape: rounded, label: "Light"}
  LightString@{shape: brace, label: "stroke:#7d6608,stroke-width:3px,fill:#f9e79f,color:#7d6608"}
  Mid@{shape: rounded, label: "Mid"}
  MidString@{shape: brace, label: "stroke:#7d6608,stroke-width:3px,fill:#f4d03f,color:#7d6608"}
  Dark@{shape: rounded, label: "Dark"}
  DarkString@{shape: brace, label: "stroke:#fef9e7,stroke-width:3px,fill:#d4ac0d,color:#fef9e7"}
  %% Layout
  Light --> LightString
  Mid --> MidString
  Dark --> DarkString
  %% Styles
  classDef Light stroke:#6e2c00,stroke-width:3px,fill:#edbb99,color:#6e2c00  
  classDef Mid stroke:#6e2c00,stroke-width:3px,fill:#dc7633,color:#fbeee6
  classDef Dark stroke:#fbeee6,stroke-width:3px,fill:#ba4a00,color:#fbeee6
  class Light Light
  class Mid Mid
  class Dark Dark
```

```mermaid
---
title: White/Black
---
flowchart LR
  %% Components
  White@{shape: rounded, label: "White"}
  WhiteString@{shape: brace, label: "stroke:#000000,stroke-width:3px,fill:#ffffff,color:#000000  "}
  GreyOne@{shape: rounded, label: "Grey #1"}
  GreyOneString@{shape: brace, label: "stroke:#7d6608,stroke-width:3px,fill:#f4d03f,color:#7d6608"}
  GreyTwo@{shape: rounded, label: "Grey #2"}
  GreyTwoString@{shape: brace, label: "stroke:#7d6608,stroke-width:3px,fill:#f4d03f,color:#7d6608"}
  Black@{shape: rounded, label: "Black"}
  BlackString@{shape: brace, label: "stroke:#ffffff,stroke-width:3px,fill:#000000,color:#ffffff"}
  %% Layout
  White --> WhiteString
  GreyOne --> GreyOneString
  GreyTwo --> GreyTwoString
  Black --> BlackString
  %% Styles
  classDef White stroke:#000000,stroke-width:3px,fill:#ffffff,color:#000000  
  classDef GreyOne stroke:#000000,stroke-width:3px,fill:#7b7d7d,color:#ffffff
  classDef GreyTwo stroke:#FFFFFF,stroke-width:3px,fill:#7b7d7d,color:#ffffff
  classDef Black stroke:#ffffff,stroke-width:3px,fill:#000000,color:#ffffff
  class White White
  class GreyOne GreyOne
  class GreyTwo GreyTwo
  class Black Black
```