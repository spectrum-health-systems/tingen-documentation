# Snippets

## XML comments

### Bullet list

``` csharp
///  <para>
///   Tingen configuration settings:
///   <list type="bullet">
///    <item>Specific to Tingen, not other components/modules/etc.</item>
///    <item>Do not change between Tingen sessions</item>
///    <item>Can be modified by the user to suit their environments</item>
///   </list>
///  </para>
```

### Table

``` csharp
///  <para>
///   The TingenMode can be:
///   <list type="table">
///    <item>
///     <term>Enabled (default)</term>
///     <description>Tingen is enabled, and will do work</description>
///    </item>
///    <item>
///     <term>Disabled</term>
///     <description>Tingen is disabled, and will not do any work</description>
///    </item>
///    <item>
///     <term>Development</term>
///     <description>Tingen is enabled, and development/debugging data is reset at execution</description>
///    </item>
///   </list>
///  </para>
```

## Assembly declaration

```csharp
/// <summary>Assembly name for log files.</summary>
/// <remarks>
///   <para>
///    - Define the assembly name here so it can be used to write log files throughout the class.
///   </para>
/// </remarks>
public static string AssemblyName { get; set; } = Assembly.GetExecutingAssembly().GetName().Name;
```



## Debugging

### Primeval

```csharp
LogEvent.Primeval(Assembly.GetExecutingAssembly().GetName().Name);
```

### Trace

When calling a Trace log event from a method that has the Tingen Session object:

```csharp
LogEvent.Trace(1, AssemblyName, tnSession.TraceInfo);
```

When calling a Trace log event from a method that has the `traceInfo` object:

```csharp
LogEvent.Trace(1, AssemblyName,  traceInfo);
```

You can also add content to a Trace log:

```csharp
LogEvent.Trace(1, AssemblyName, tnSession.TraceInfo, "Content goes here");
LogEvent.Trace(1, AssemblyName,  traceInfo, "Content goes here");
```

## Development notes footer

```csharp
/*

-----------------
Development notes
-----------------

*/
```
