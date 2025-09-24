# TingenWebService.asmx.cs

## CriticalErrorOccurred()

```mermaid
flowchart TD
    A[RunScript()] --> B[Load runtimeConfig]
    B --> C{CriticalFailureOccurred?}
    C -- Yes --> D[Return origOptObj.ToReturnOptionObject]
    C -- No --> E{Mode?}
    E -- enabled --> F[Instance.Start]
    E -- passthrough --> F
    E -- other --> J[Return origOptObj.ToReturnOptionObject]
    F --> G[AvatarScriptParameter.ParseParameter]
    G --> H[LogEvent.Session]
    H --> I[Return sess.OptObj.Completed]
```