# TingenWebService.asmx.cs

## CriticalErrorOccurred()

```mermaid
flowchart TB
    %% Components
    RunScript@{shape: rect, label: "TingenWebService.RunScript()"}
    MissingData@{shape: diam, label: "Is the OptionObject\nand/or\nScriptParameter null or empty?"}
    CurrentMode@{shape: diam, label: "Current\nmode"}
    ReturnTrue@{shape: rounded, label: "Return True"}
    ReturnFalse@{shape: rounded, label: "Return False"}
    %% Layout
    RunScript --> MissingData
    MissingData --True--> ReturnFalse
    MissingData --False--> CurrentMode
    CurrentMode --Enabled<br>or<br>Passthrough--> ReturnFalse
    CurrentMode --Disabled<br>or<br>unknown--> ReturnTrue
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

```mermaid
classDiagram
    class TingenWebService {
        +string TngnWsvcVersion
        +string GetVersion()
        +OptionObject2015 RunScript(OptionObject2015 origOptObj, string origScriptParam)
        +static bool CriticalFailureOccurred(OptionObject2015 origOptObj, string origScriptParam, string tngnWsvcMode)
    }
    class OptionObject2015 {
        +string EntityID
        +double EpisodeNumber
        +double ErrorCode
        +string ErrorMesg
        +string Facility
        +List~FormObject~ Forms
        +string NamespaceName
        +string OptionId
        +string OptionStaffId
        +string OptionUserId
        +string ParentNamespace
        +string ServerName
        +string SystemCode
        +string SessionToken
        +OptionObject2015 ToReturnOptionObject(int errorCode, string errorMessage)
    }
    class AvatarScriptParameter {
        <<static>>
        +void ParseParameter(Instance sess)
    }
    class Instance {
        <<static>>
        +Instance Start(OptionObject2015 origOptObj, string origScriptParam, Dictionary~string,string~ runtimeConfig)
        +OptionObject2015 OptObj
    }
    class LogEvent {
        <<static>>
        +void Debug(string message)
        +void Session(Instance sess)
    }
    class RuntimeConfig {
        <<static>>
        +Dictionary~string,string~ Load(Settings webConfig, string tngnWsvcVer)
    }
    class Settings {
        <<external>>
    }
    TingenWebService ..> OptionObject2015 : uses
    TingenWebService ..> AvatarScriptParameter : uses
    TingenWebService ..> Instance : uses
    TingenWebService ..> LogEvent : uses
    TingenWebService ..> RuntimeConfig : uses
    RuntimeConfig ..> Settings : uses
    OptionObject2015 o-- "0..*" FormObject : Forms
```


```mermaid
flowchart TD
    A[RunScript called] --> B[Load runtimeConfig]
    B --> C{CriticalFailureOccurred?}
    C -- Yes --> D[Return origOptObj.ToReturnOptionObject]
    C -- No --> E{Mode == "enabled" or "passthrough"?}
    E -- Yes --> F[Instance.Start]
    F --> G[AvatarScriptParameter.ParseParameter]
    G --> H[LogEvent.Session]
    H --> I[Return sess.OptObj.Completed]
    E -- No --> J[Return origOptObj.ToReturnOptionObject]
```