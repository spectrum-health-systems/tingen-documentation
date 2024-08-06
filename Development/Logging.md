<!--
  u240805_work-in-progress
-->

<div align="center">
    <h1>
        LOGGING
    </h1>
</div>

<br>
<br>

# Trace logs

If trace logs can be used, you'll need the following:

1. The Assembly header
2. The trace log call
3. (optional) Message

## Assembly header

The following should be at the top of every class that generates logs:

```csharp
/// <summary>Assembly name for logging purposes.</summary>
/// <include file='XMLDoc/Tingen_doc.xml' path='Doc/Sec[@name="tingen"]/AssemblyName/*'/>
public static string AssemblyName { get; set; } = Assembly.GetExecutingAssembly().GetName().Name;
```

## Trace log call

- `LogEvent.Trace(1, AssemblyName, traceInfo);`
- `LogEvent.Trace(1, AssemblyName, tnSession.TraceInfo);`
- `LogEvent.Trace(1, AssemblyName, traceInfo, message);`
- `LogEvent.Trace(1, AssemblyName, tnSession.TraceInfo, message);`

## Trace log levels

- `0` Temporary trace logs, can be removed.
- `1` First line of all methods
- `2`
- `3`
- `4`
- `5`
- `6`
- `7`
- `8`
- `9`
- 
# Primeval logs

Simple logs that need little information to create, and are located in "TingenData\Primeval\

- `LogEvent.Primeval(Assembly.GetExecutingAssembly().GetName().Name);`
- `LogEvent.Primeval(Assembly.GetExecutingAssembly().GetName().Name, message);`

- `LogEvent.Primeval(AssemblyName);`
- `LogEvent.Primeval(AssemblyName, message);`
