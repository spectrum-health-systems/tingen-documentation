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

# DEVELOPMENT GUIDELINES

Guidelines for the following can be found [here](https://github.com/APrettyCoolProgram/APrettyCoolProgram):

* Classes/methods
* Syntax
* Formatting
* Versioning
* Comments
* XML documentation
* File headers
* Mermaid

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

## Tingen

```
// The
// ████████╗██╗███╗   ██╗ ██████╗ ███████╗███╗   ██╗
// ╚══██╔══╝██║████╗  ██║██╔════╝ ██╔════╝████╗  ██║
//    ██║   ██║██╔██╗ ██║██║  ███╗█████╗  ██╔██╗ ██║
//    ██║   ██║██║╚██╗██║██║   ██║██╔══╝  ██║╚██╗██║
//    ██║   ██║██║ ╚████║╚██████╔╝███████╗██║ ╚████║
//    ╚═╝   ╚═╝╚═╝  ╚═══╝ ╚═════╝ ╚══════╝╚═╝  ╚═══╝
//                                       Web Service
//                      Development Release XX.yy.zz
//
// https://github.com/APrettyCoolProgram/Tingen-WebService
// Copyright (c) A Pretty Cool Program. All rights reserved.
// Licensed under the Apache 2.0 license.
//
// uYYMMDD_code
// uYYMMDD_documentation

```

## Outpost31

### WelcomeToOutpost31.cs

```
//  Welcome to
//  ██████╗ ██╗   ██╗████████╗██████╗  ██████╗ ███████╗████████╗    ██████╗  ██╗
// ██╔═══██╗██║   ██║╚══██╔══╝██╔══██╗██╔═══██╗██╔════╝╚══██╔══╝    ╚════██╗███║
// ██║   ██║██║   ██║   ██║   ██████╔╝██║   ██║███████╗   ██║        █████╔╝╚██║
// ██║   ██║██║   ██║   ██║   ██╔═══╝ ██║   ██║╚════██║   ██║        ╚═══██╗ ██║
// ╚██████╔╝╚██████╔╝   ██║   ██║     ╚██████╔╝███████║   ██║       ██████╔╝ ██║
//  ╚═════╝  ╚═════╝    ╚═╝   ╚═╝      ╚═════╝ ╚══════╝   ╚═╝       ╚═════╝  ╚═╝
//                                 The back-end logic for the Tingen Web Service
//                                                  Development Release XX.yy.zz
// https://github.com/APrettyCoolProgram/Outpost31
// Copyright(c) A Pretty Cool Program. All rights reserved.
// Licensed under the Apache 2.0 license.
//
// uYYMMDD_code
// uYYMMDD_documentation
```

### Other Outpost31 classes

```
//  ██████  ██  ██ ██████ █████ ██████ █████  ██████   ██████  ███ 
//  ██  ██  ██  ██   ██   █████ ██  ██ ██████   ██        ███   ██ 
//  ██████  ██████   ██   ██    ██████  █████   ██     ██████   ██ 
//                             Outpost31.Core.Avatar.SystemCode.cs
//                                   Logic for Avatar System Codes
// uYYMMDD_code
// uYYMMDD_documentation
```


