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
    Start --> RuntimeConfig_Load --> CriticalFailureOccurred
    CriticalFailureOccurred -- True --> ReturnOriginalOptionObject
    CriticalFailureOccurred -- False --> Mode
    Mode -- enabled --> Instance.Start
    Mode -- passthrough --> Instance.Start
    Mode -- other --> ReturnOriginalOptionObject
    Instance.Start --> ParseParameter
    ParseParameter --> LogSessio
    LogSession --> ReturnUpdatedOptionObject
    %%
    click RuntimeConfig_Load "https://github.com/spectrum-health-systems/tingen-documentation-project/blob/main/static/diagrams/TingenWebService.Configuration.md#tingenwebserviceconfigurationruntimeconfigcs"
```

## CriticalFailureOccurred()

> Last updated 9/24/25

```mermaid
flowchart TD
    A[CriticalFailureOccurred] --> B{origOptObj is null or origScriptParam is null/empty?}
    B -- Yes --> C[LogEvent.Debug]
    C --> D[Return true]
    B -- No --> E{tngnWsvcMode value}
    E -- enabled or passthrough --> F[Return false]
    E -- disabled --> G[LogEvent.Debug]
    G --> H[Return true]
    E -- default/unknown --> I[LogEvent.Debug]
    I --> J[Return true]
```

***

[[🏠︎](../../README.md)] ❬ [Static documentation](../README.md) ❬ [Diagrams](README.md)



```mermaid
flowchart TD
    %% Components

    Start@{shape: sm-circ, label: ""} --> RuntimeConfig_Load@{shape: fr-rect, label: "RuntimeConfig.Load()"}
    RuntimeConfig_Load --> CriticalFailureOccurred@{shape: rounded, label: "CriticalFailureOccurred()"}
    CriticalFailureOccurred -- True --> ReturnOriginalOptionObject@{shape: dbl-circ, label: "Return original\nOptionObject"}
    CriticalFailureOccurred -- False --> Mode@{shape: diam, label: "Mode"}
    Mode -- enabled --> Instance.Start@{shape: fr-rect, label: "Instance.Start()"}
    Mode -- passthrough --> Instance.Start
    Mode -- other --> ReturnOriginalOptionObject
    Instance.Start --> ParseParameter@{shape: fr-rect, label: "AvatarScriptParameter.ParseParameter()"}
    ParseParameter --> LogSession@{shape: fr-rect, label: "LogEvent.Session()"}
    LogSession --> ReturnUpdatedOptionObject@{shape: dbl-circ, label: "Return updated\nOptionObject"}
    %%
    click RuntimeConfig_Load "https://github.com/spectrum-health-systems/tingen-documentation-project/blob/main/static/diagrams/TingenWebService.Configuration.md#tingenwebserviceconfigurationruntimeconfigcs"
```