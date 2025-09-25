<!-- u250924 -->

[[🏠︎](../../README.md)] ❬ [Static documentation](../README.md) ❬ [Diagrams](README.md)

# TingenWebService

### CONTENTS

* asmx.cs
    * [GetVersion()](#getversion)
    * [RunScript()](#runscript)
    * [CriticalFailureOccurred()](#criticalfailureoccurred)

***

## GetVersion()

> Last updated 9/24/25

## RunScript()

> Last updated 9/24/25

<div align="center">

```mermaid
flowchart TD
    %% Components
    Start@{shape: sm-circ, label: ""}
    RuntimeConfig_Load@{shape: fr-rect, label: "RuntimeConfig.Load()"}
    CriticalFailureOccurred@{shape: rounded, label: "CriticalFailureOccurred()"}
    ReturnOriginalOptionObject@{shape: dbl-circ, label: "Return original\nOptionObject"}
    Mode@{shape: diam, label: "Mode"}
    Instance.Start@{shape: fr-rect, label: "Instance.Start()"}
    ParseParameter@{shape: fr-rect, label: "AvatarScriptParameter.ParseParameter()"}
    LogSession@{shape: fr-rect, label: "LogEvent.Session()"}
    ReturnUpdatedOptionObject@{shape: dbl-circ, label: "Return updated\nOptionObject"}
    %% Layout
    Start --> RuntimeConfig_Load:::E3_ --> CriticalFailureOccurred:::E3_
    CriticalFailureOccurred -- True --> ReturnOriginalOptionObject:::E3_
    CriticalFailureOccurred -- False --> Mode:::E3_
    Mode -- enabled --> Instance.Start:::U3_
    Mode -- passthrough --> Instance.Start
    Mode -- other --> ReturnOriginalOptionObject
    Instance.Start --> ParseParameter:::U3_
    ParseParameter --> LogSession:::U3_
    LogSession --> ReturnUpdatedOptionObject:::E3_
    %% Styles
    classDef E3_ stroke:#fdf2e9,stroke-width:3px,fill:#ca6f1e,color:#fdf2e9
    classDef U3_ stroke:#eaf2f8,stroke-width:3px,fill:#2471a3,color:#eaf2f8
    %% Links
    click RuntimeConfig_Load "https://github.com/spectrum-health-systems/tingen-documentation-project/blob/main/static/diagrams/TingenWebService.Configuration.md#tingenwebserviceconfigurationruntimeconfigcs"
    click CriticalFailureOccurred "https://github.com/spectrum-health-systems/tingen-documentation-project/blob/main/static/diagrams/TingenWebService.md#criticalfailureoccurred"
```

</div>

## CriticalFailureOccurred()

> Last updated 9/24/25

```mermaid
flowchart TD
    %% Content
    Start@{shape: sm-circ, label: ""}
    InvalidAvatarData@{shape: diam, label: "Invalid data\nfrom Avatar"}
    WriteTrueLog@{shape: rounded, label: "Write log"}
    ReturnTrue@{shape: rect, label: "Return true"}
    InvalidAvatarData
    Mode@{shape: diam, label: "Mode"}
    ReturnFalse@{shape: rect, label: "Return false"}
    %% Layout
    Start --> InvalidAvatarData
    InvalidAvatarData -- Yes --> WriteFalseLog --> ReturnTrue
    InvalidAvatarData -- No --> Mode
    Mode -- enabled --> ReturnFalse
    Mode -- passthrough --> ReturnFalse
    Mode -- disabled --> WriteTrueLog
    WriteTrueLog --> ReturnTrue
    Mode -- default --> WriteTrueLog
    Mode -- unknown --> WriteTrueLog
    WriteTrueLog --> ReturnTrue
```

***

[[🏠︎](../../README.md)] ❬ [Static documentation](../README.md) ❬ [Diagrams](README.md)