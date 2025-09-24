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
    A((RunScript)) --> B[RuntimeConfig.Load]
    B --> C{TingenWebService.CriticalFailureOccurred}
    C -- True --> D[Return origOptObj.ToReturnOptionObject]
    C -- False --> E{Mode}
    E -- enabled --> F[Instance.Start]
    E -- passthrough --> F
    E -- other --> J[Return origOptObj.ToReturnOptionObject]
    F --> G[AvatarScriptParameter.ParseParameter]
    G --> H[LogEvent.Session]
    H --> I[Return sess.OptObj.Completed]
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
