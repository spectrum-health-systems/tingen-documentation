# Code snippets

## `see href`

## Logging

```csharp
/* Trace Logs can't go here because the logging infrastructure hasn't been been initialized yet, so if you
 * need to create a logfile here, use a Primeval Log.
 */
```

```csharp
LogEvent.Primeval(Assembly.GetExecutingAssembly().GetName().Name);
```

## Development Notes

```csharp
/* [DN--] */
/* [DN01] */
```

```csharp
/*
=================
DEVELOPMENT NOTES
=================

-----------------
[DN--] 240817
-----------------
General note.

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
/*
=================
DEVELOPMENT NOTES
=================

None.

*/
```

## Assembly Name

```csharp
/// <summary>The executing assembly name.</summary>
/// <remarks>This is defined here so it can be used to write log files throughout the class.</remarks>
public static string ExeAsm { get; set; } = Assembly.GetExecutingAssembly().GetName().Name;
```

```html
<!-- u240820 -->
```

## XML documentation links to webpages

```csharp
<see href="github.com/spectrum-health-systems/Tingen-Documentation/blob/main/Glossary.md#tingen-configuration">here.</see>

<paramref name="name"/>

<see cref="ReturnOptionObject"/>

<see cref="Outpost31.Core.Avatar.ReturnObject.Finalize(Session.TingenSession, string, string)"/>

 More information about OptionObjects <see href="github.com/spectrum-health-systems/Tingen-Documentation/blob/main/Glossary.md#avatar-optionobject">here</see>
```

***


<seealso href="https://github.com/spectrum-health-systems/Tingen-Documentation/blob/main/Static/ScriptLink.md">Tingen Documentation: ScriptLink</seealso>



1-----------------------------------------------------------------------------80-----|-------------------------|-----120



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