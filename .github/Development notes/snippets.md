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

## Assemnly Name

```csharp
/// <summary>Assembly name for logging purposes.</summary>
/// <include file='XmlDoc/Common_doc.xml' path='Common/Term[@name="Term"]/AssemblyName/*'/>
public static string AssemblyName { get; set; } = Assembly.GetExecutingAssembly().GetName().Name;
```

```html
<!--
    u240818.0906_documentation

    Namespace
        Outpost31.Core.Avatar

    Classes
        AvatarData.cs
        ReturnObject.cs
-->
```

## XML documentation links to webpages

```csharp
<see href="github.com/spectrum-health-systems/Tingen-Documentation/blob/main/Glossary.md#tingen-configuration">here.</see>
```