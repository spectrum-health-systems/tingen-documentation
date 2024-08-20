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

## Assembly Name

```csharp
/// <summary>Assembly name for logging purposes.</summary>
/// <include file='XmlDoc/Common_doc.xml' path='Common/Term[@name="Term"]/AssemblyName/*'/>
public static string AssemblyName { get; set; } = Assembly.GetExecutingAssembly().GetName().Name;
```

```html
<!--
    u240820_documentation [WORK-IN-PROGRESS]

    Namespace
        Outpost31.Core.Avatar

    Classes
        Outpost31.Core.Avatar.AvatarData.cs
        Outpost31.Core.Avatar.ReturnObject.cs
-->

<!--
    u240819_documentation [WORK-IN-PROGRESS]

    This document contains common XML Documentation that is used throughout the
    Outpost31 project.

    Properties
        AssemblyName        string
        Mode                string
        ReturnOptionObject  OptionObject
        SentOptionObject    OptionObject
        SentScriptParameter string
        SystemCode          string
        TraceDelay          int
        TraceLevel          int
        WorkOptionObject    OptionObject
-->
```

## XML documentation links to webpages

```csharp
<see href="github.com/spectrum-health-systems/Tingen-Documentation/blob/main/Glossary.md#tingen-configuration">here.</see>

<paramref name="name"/>

<see cref="ReturnOptionObject"/>

<see cref="Outpost31.Core.Avatar.ReturnObject.Finalize(Session.TingenSession, string, string)"/>

```

***


<seealso href="https://github.com/spectrum-health-systems/Tingen-Documentation/blob/main/Static/ScriptLink.md">Tingen Documentation: ScriptLink</seealso>



1-----------------------------------------------------------------------------80----|--------------------------|-----120



                <para>
                    Before returning the <see cref="ReturnOptionObject"/> to Avatar, it must
                    be formatted correctly, and any be finalized, which<br/>
                    is what this class does: it finalizes the OptionObject so it can be returned<br/>
                    to Avatar.
                </para>



                                    <list type="table">
                        <listheader>
                            <term>Error string</term>
                            <description>Description</description>
                        </listheader>
                        <item>
                            <term>"clone", "none", "success"</term>
                            <description><b>Success</b> - Returns the OptionObject without a message (error code <c>"0"</c>)</description>
                        </item>
                        <item>
                            <term>error</term>
                            <description><b>Error</b> - Stops the script from processing and displays an message with an "OK" button (error code <c>"1"</c>)</description>
                        </item>
                        <item>
                            <term>okcancel</term>
                            <description><b>OKCancel</b> - Displays a message with "OK" and "Cancel" buttons (error code <c>"2"</c>)</description>
                        </item>
                        <item>
                            <term>info</term>
                            <description><b>Info</b> - Displays an informational warning message with an "OK" button (error code <c>"3"</c>)</description>
                        </item>
                        <item>
                            <term>yesno</term>
                            <description><b>YesNo</b> - Displays a message with "Yes" and "No" buttons (error code <c>"4"</c>)</description>
                        </item>
                        <item>
                            <term>openurl</term>
                            <description><b>OpenURL</b> - Opens an URL in a browser (error code <c>"5"</c>)</description>
                        </item>
                        <item>
                            <term>openform</term>
                            <description><b>OpenForm</b> - Presents an OK/Cancel dialog to open a form (only be used on Form Load and Field events) (error code <c>"6"</c>)</description>
                        </item>
                    </list>    