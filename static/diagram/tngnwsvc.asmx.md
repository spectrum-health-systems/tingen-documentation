<!-- u250924 -->

[[🏠︎](../../README.md)] ❬ [Static documentation](../README.md) ❬ [Diagrams](README.md)

# TingenWebService

### CONTENTS
[TingenWebService.asmx.cs](#tingenwebserviceasmxcs)
[]()

## TingenWebService.asmx.cs

```mermaid
flowchart TD
    A[TingenWebService.RunScript] --> B[RuntimeConfig.Load]
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

## TingenWebService.Configuration.RuntimeConfig.cs

```mermaid
flowchart TD
    A[Start: Load called] --> B[Receive webConfig and tngnWsvcVer]
    B --> C[Create new Dictionary]
    C --> D[Add Version]
    D --> E[Add BuildNumber]
    E --> F[Add AvatarSys]
    F --> G[Add Mode]
    G --> H[Add BaseWww]
    H --> I[Add BaseData]
    I --> J[Add TraceLogLimit]
    J --> K[Return Dictionary]
```
