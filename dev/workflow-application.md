<!-- u250905 -->

# Tingen Web Service/Outpost31 process flow

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
  StartSession@{ shape: rounded, label: "Start new\n session" }
  Stop_Disabled@{ shape: fr-circ }
  %% Layout
  Start_TingenWebService --> GetVersionOrRunScript
  GetVersionOrRunScript --GetVersion\(\)--> OutputVersion --> Stop_GetVersion
  GetVersionOrRunScript --RunScript\(\)--> ValidDataPassed
  ValidDataPassed --NO--> CriticalNoValidData --> Stop_ValidDataNotPassed
  ValidDataPassed --YES--> ServiceMode
  ServiceMode --ENABLED--> StartSession
  ServiceMode --DISABLED--> ReturnUnmodified --> Stop_Disabled
  %% Styles
```

> NOTES:  
> [1] The Tingen Web Service requires that both a valid `OptionObject` and `Script Parameter` are passed.

<br>

****

## Starting a new session

```mermaid
flowchart LR
  %% Content
  From_TingenWebService.asmx.cs@{ shape: rounded, label: "TingenWebService.asmx.cs" }
  CreateSessionFolder@{ shape: rounded, label: "Create session folder" }
  subgraph Outpost31.Core.Session.Instance.Start ["Outpost31.Core.Session.Instance.Start[1]"]
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
  From_TingenWebService.asmx.cs --> Outpost31.Core.Session.Instance.Start --> CreateSessionFolder
  %% Styles 
```

> NOTES:  
> [1] Some of these use existing Web.config settings, some are set when the session starts.