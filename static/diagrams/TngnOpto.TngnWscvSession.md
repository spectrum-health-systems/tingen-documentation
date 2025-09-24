<!-- u250924 -->

[[🏠︎](../../README.md)] ❬ [Static documentation](../README.md) ❬ [Diagrams](README.md)

# Outpost31.TngnWsvcSession

### CONTENTS
[Outpost31.TngnWsvcSession.Instance.Load](#instanceload)  
[TingenWebService.Configuration.RuntimeConfig.cs](#tingenwebserviceconfigurationruntimeconfigcs)  

***

# Instance.Load()

> Last updated 250924

```mermaid
flowchart TD
    A[Instance.Load] --> B[Call Details.Load]
    B --> C[Call Folders.Load]
    C --> D[Call LogSettings.Load]
    D --> E[Create AvatarOptionObject]
    E --> F[Create AvatarScriptParameter ]
    F --> G[Return new Instance]
```

# Instance.Load()

> Last updated 250924

```mermaid
flowchart TD
    A[Instance.Start] --> B[Instance.Load]
    B --> C[Instance created]
    C --> D[Folders.CreateSessionFolder]
    D --> E[Return session]
```










## TingenWebService.asmx.cs

> Last updated 250924

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

> Last updated 250924

```mermaid
flowchart TD
    A[RuntimeConfig.Load] --> B[Receive webConfig and tngnWsvcVer]
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

***

[[🏠︎](../../README.md)] ❬ [Static documentation](../README.md) ❬ [Diagrams](README.md)
