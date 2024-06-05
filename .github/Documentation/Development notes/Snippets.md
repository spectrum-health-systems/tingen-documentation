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

```csharp
/* Can't do any logging here. Sorry! */
```

```csharp
/* Trace logs cannot be used here. For debugging purposes, use a Primeval log. */
```

```csharp
/* Trace log info for this method. */
Dictionary<string, string> traceInfo = LogInfo.TraceLog(Asm, tnSession.Config, tnSession.Framework);
```

```csharp
LogEvent.Primeval(Assembly.GetExecutingAssembly().GetName().Name);
```



```csharp
LogEvent.Trace(2, Asm, traceInfo);
```

```csharp
LogEvent.Trace(2, Asm, tnSession.TraceInfo);
```

## Development notes footer

```csharp
/*

Development notes
-----------------

*/
```
