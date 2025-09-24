# TingenWebService.asmx.cs

## CriticalErrorOccurred()

```mermaid
flowchart TB
    %% Components
    RunScript@{shape: rect, label: "TingenWebService.RunScript()"}
    MissingData@{shape: diam, label: "Is the OptionObject and/or\nScriptParameter null or empty?}
    CurrentMode@{shape: diam, label: "Current\nmode"}
    ReturnTrue@{shape: rounded, label: "Return True"}
    ReturnFalse@{shape: rounded, label: "Return False"}
    %% Layout
    RunScript --> EmptyOptionObjectOrScriptParameter
    MissingData --True--> ReturnFalse
    MissingData --False--> CurrentMode
    CurrentMode --Enabled--> ReturnFalse
    CurrentMode --Passthrough--> ReturnFalse
    CurrentMode --Disabled--> ReturnTrue
    CurrentMode --unknown--> ReturnTrue
    %% Styles
```

## RunScript()

```mermaid
flowchart TB
    %% Components
    Start@{shape: sm-circ, label: "Start"}
    RuntimeConfig.Load@{shape: fr-rect, label: "TingenWebService.Configuration.RuntimeConfig.Load"}
    CriticalFailureOccurred@{shape: diam, label: "CriticalFailureOccurred()"}
    CurrentMode@{shape: diam, label: "Current\nmode"}
    Instance.Start@{shape: fr-rect, label: "Outpost31.Core.TngnWsvcSession.Instance.Start()"}
    ParseParameter@{shape: fr-rect, label: "Outpost31.Core.Avatar.AvatarScriptParameter.ParseParameter()"}
    ReturnOptionObject@{shape: fr-rect, label: "Return completed\nOptionObject"}
    Stop@{shape: fr-circ, label: "Release"}
    %% Layout
    Start --> RuntimeConfig.Load --> CriticalFailureOccurred
    CriticalFailureOccurred --True--> ReturnOptionObject
    CriticalFailureOccurred --False--> CurrentMode
    CurrentMode --Enabled--> Instance.Start
    CurrentMode --Passthrough--> Instance.Start
    Instance.Start --> ParseParameter
    ParseParameter --> ReturnOptionObject
    CurrentMode --unknown--> ReturnOptionObject
    ReturnOptionObject -->  Stop
    %% Styles
```