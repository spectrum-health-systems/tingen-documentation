# Development snippets

```csharp
 More information about OptionObjects <see href="github.com/spectrum-health-systems/Tingen-Documentation/blob/main/Glossary.md#avatar-optionobject">here</see>
```

```csharp
/* Trace logs cannot be used here. For debugging purposes, use a Primeval log.
*/
```

```csharp
/* [DN01] */
```

```csharp
/*
=================
DEVELOPMENT NOTES
=================

-----------------
[DN01] 240817
-----------------
As of v24.8, the TingenMode must be either "enabled" or "disabled".

If the TingenMode is "enable" or "disable" (which I've done when testing, so it's not an edge case), the Tingen will enter an "unknown"
state.

For now, users should verify that the TingenMode is "enabled" or "disabled", but it may make sense to catch other valuessuch as
"enable" or "disable".

*/
```



```csharp
/// <summary>Assembly name for logging purposes.</summary>
/// <remarks> The assembly name is defined here so it can be used to write log files throughout the class.</remarks>
public static string AssemblyName { get; set; } = Assembly.GetExecutingAssembly().GetName().Name;
```

```html
<!--
    u240817.1021_documentation
-->
```

## XML documentation links to webpages

```csharp
<see href="github.com/spectrum-health-systems/Tingen-Documentation/blob/main/Glossary.md#tingen-configuration">here.</see>
```