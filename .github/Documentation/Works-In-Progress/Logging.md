# Logging

## Trace logs

If a trace log cannot be used, add this comment:

```csharp
/* Trace logs cannot be used here. For debugging purposes, use a Primeval log. */
```

If trace logs can be used, you'll need the following:

1. The Assembly header
2. The trace log call

### Assembly header

The following should be at the top of every class that generates logs:

```csharp
/// <summary>Assembly name for log files.</summary>
/// <remarks>
///   <para>
///    - Define the assembly name here so it can be used to write log files throughout the class.
///   </para>
/// </remarks>
public static string AssemblyName { get; set; } = Assembly.GetExecutingAssembly().GetName().Name;
```

### Trace log call

Two ways to call:

1. `LogEvent.Trace(1, AssemblyName, traceInfo);`

2. `LogEvent.Trace(1, AssemblyName, tnSession.TraceInfo);`

### Level 1

`LogEvent.Trace(1, AssemblyName, tnSession.TraceInfo);`

- First line of all methods


## Primeval