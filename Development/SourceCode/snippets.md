<!-- u250114 -->

<div align="center">

![logo](../.github/image/logos/TingenDevelopmentDocumentation_logo_320x420.png)

 <h1>Code snippets</h1>

</div>

### CONTENTS

[Trace logs](#trace-logs)  
[Primeval logs](primeval-logs)  
[Development notes](#development-notes)  
[Assembly name variable](#assembly-name-variable)  
[HTML headers](#html-headers)  
[XML documentation](#xml-documentation)

# Trace logs

## Trace log can't go here

```csharp
/* Trace Logs can't go here because the logging infrastructure hasn't been initialized yet, so if you
 * need to create a log file here, use a Primeval Log.
 */
```

## Trace logs and Primeival logs can't go here

```csharp
/* Trace Logs can't go here because the logging infrastructure hasn't been initialized yet.
 *
 * You can't put a Primeval Log here either, since that may result in an infinite loop/stack overflow
 * when Primeval log directory is being refreshed.
 */
```

## Trace log can't go here, use a Primeval at your own risk

```csharp
/* Trace Logs can't go here because the logging infrastructure hasn't been initialized yet.
 * 
 * Use a Primeval Log here at your own risk!
 */
```

## Trace log can't go here, Primeval not recommended

```csharp
/* Trace Logs can't go here because the logging infrastructure hasn't been initialized yet.
 *
 * Creating a Primeval log here is not recommended. If you need to debug this method, you'll need to
 * insert some of the logic above to avoid infinite loops/stack overflows.
 */
```

# Primeval logs

## Code syntax

```csharp
LogEvent.Primeval(Assembly.GetExecutingAssembly().GetName().Name);
```

# Development notes

## Comment syntax

```csharp
/*
[DN01] YYMMDD
Development notes

[DN02] YYMMDD
Development notes
 */
```

## Example

```csharp
/*
[DN01] 240817
General note.

As of v24.8, the TingenMode must be either "enabled" or "disabled".

If the TingenMode is "enable" or "disable" (which I've done when testing, so it's not an edge case), the Tingen will enter an "unknown"
state.

For now, users should verify that the TingenMode is "enabled" or "disabled", but it may make sense to catch other valuessuch as
"enable" or "disable".
*/
```

# Assembly name variable

This code block belongs at the top of most classes:

```csharp
/// <summary>The executing Assembly name.</summary>
/// <remarks>A required component for writing log files, defined here so it can be used throughout the class.</remarks>
public static string ExeAsm { get; set; } = Assembly.GetExecutingAssembly().GetName().Name;
```

# HTML headers

```html
<!-- u240820 -->
```

# XML documentation

## SeeAlso

```csharp
<seealso href="https://github.com/spectrum-health-systems/Tingen-Documentation">Tingen documentation</seealso>
```

## Link to URL

```csharp
<see href="github.com/spectrum-health-systems/Tingen-Documentation/blob/main/Glossary.md#tingen-configuration">here.</see>

<paramref name="name"/>

<see cref="ReturnOptionObject"/>

<see cref="Outpost31.Core.Avatar.ReturnObject.Finalize(Session.TingenSession, string, string)"/>

 More information about OptionObjects <see href="github.com/spectrum-health-systems/Tingen-Documentation/blob/main/Glossary.md#avatar-optionobject">here</see>
```

***
