<!-- u250905 -->

# Tingen Web Service/Outpost31 process flow

## Overview

```mermaid
flowchart LR
  %% Content
  Start@{ shape: fr-circ }
  Initialize@{ shape: rounded, label: "Initialize" }
  CreateSession@{ shape: rounded, label: "Create session" }
  ParseRequest@{ shape: rounded, label: "Parse request" }
  Stop@{ shape: fr-circ }
  %% Layout
  Start --> Initialize:::FP8 --> CreateSession:::FP8 --> ParseRequest:::FP8 --> Stop
  %% Styles
  classDef FP8 font-size:8pt
```

## Initializing the Tingen Web Service

```mermaid
flowchart LR
  %% Content
  Start_TingenWebService@{ shape: circle, label: "Avatar" }
  GetVersionOrRunScript@{ shape: diam, label: "GetVersion()\nor\nRunScript()?" }
  OutputVersion@{ shape: lean-l, label: "Output\nversion" }
  Stop_GetVersion@{ shape: fr-circ }
  ValidDataPassed@{ shape: diam, label: "Valid data\npassed?[1]" }
  CriticalNoValidData@{ shape: lean-l, label: "Write\ncritical log" }
  Stop_ValidDataNotPassed@{ shape: fr-circ }
  ServiceMode@{ shape: diam, label: "Service\nmode" }
  ReturnUnmodified@{ shape: rounded, label: "Return unmodified\nOptionObject" }
  To_Outpost31.Core.Session.Instance.Start@{ shape: stadium, label: "Outpost31.Core.Session.Instance.Start()" }
  Stop_Disabled@{ shape: fr-circ }
  %% Layout
  Start_TingenWebService --> GetVersionOrRunScript
  GetVersionOrRunScript --GetVersion\(\)--> OutputVersion --> Stop_GetVersion
  GetVersionOrRunScript --RunScript\(\)--> ValidDataPassed
  ValidDataPassed --NO--> CriticalNoValidData --> Stop_ValidDataNotPassed
  ValidDataPassed --YES--> ServiceMode
  ServiceMode --ENABLED--> To_Outpost31.Core.Session.Instance.Start
  ServiceMode --DISABLED--> ReturnUnmodified --> Stop_Disabled
  %% Styles
```

> NOTES:  
> [1] The Tingen Web Service requires that both a valid `OptionObject` and `Script Parameter` are passed.

<br>

****

## Outpost31.Core.Session.Instance.Start()

```mermaid
flowchart TB
  %% Content
  From_TingenWebService.asmx.cs@{ shape: stadium, label: "TingenWebService.asmx.cs" }
  CreateSessionFolder@{ shape: rounded, label: "Create session folder" }
  To_ParseRequest@{ shape: stadium, label: "Outpost31.Core.Request.Parser.ParseRequest()" }
  subgraph CreateNewSessionInstance ["Create session object[1]"]
    direction LR
      %% Content
      SetCurrentStamp@{ shape: rect, label: "Set current\ndate/time" }
      SetAvatarInfo@{ shape: rect, label: "Set Avatar System\nand User ID" }
      SetServiceInfo@{ shape: rect, label: "Set service version,\nmode, and framework" }
      SetLoggingInfo@{ shape: rect, label: "Set log\nsettings" }    
      SetOptionObjects@{ shape: rect, label: "Set\nOptionObjects" }
      SetScriptParameter@{ shape: rect, label: "Set Script\nParameter details" }
      %% Layout
      SetCurrentStamp --> SetAvatarInfo --> SetServiceInfo --> SetLoggingInfo --> SetOptionObjects --> SetScriptParameter
      %% Styles
  end
  %% Layout
  From_TingenWebService.asmx.cs --> CreateNewSessionInstance --> CreateSessionFolder --TingenWebService.asmx.cs--> To_ParseRequest
  %% Styles 
```

> NOTES:  
> [1] Some of these use existing Web.config settings, some are set when the session starts.


<br>

****

## Outpost31.Core.Request.Parser.ParseRequest()

```mermaid
flowchart LR
  %% Content
  From_TingenWebService.asmx.cs@{ shape: stadium, label: "TingenWebService.asmx.cs" }
  ScriptParameterStartsWith@{ shape: diam, label: "Script Parameter\nstarts with[1]" }
  To_Outpost31.Core.Request.Parser.ParseStandardRequest@{ shape: stadium, label: "Outpost31.Core.Request.Parser.ParseStandardRequest()" }
  To_Outpost31.Core.Request.Parser.ParseAdminRequest@{ shape: stadium, label: "Outpost31.Core.Request.Parser.ParseAdminRequest()" }
  To_Outpost31.Core.Request.Parser.ParsePrototypeRequest@{ shape: stadium, label: "Outpost31.Core.Request.Parser.ParsePrototypeRequest()" }
  %% Layout
  From_TingenWebService.asmx.cs --> ScriptParameterStartsWith
  ScriptParameterStartsWith --> To_Outpost31.Core.Request.Parser.ParseStandardRequest
  ScriptParameterStartsWith --_a --> To_Outpost31.Core.Request.Parser.ParseAdminRequest
  ScriptParameterStartsWith --_p --> To_Outpost31.Core.Request.Parser.ParsePrototypeRequest
```

> NOTES:  
> [1] There are three types of requests:
> * Standard requests do not have a prefix  
> * Administrative requests start with **"_a"**
> * Prototype requests start with **"_p"**
