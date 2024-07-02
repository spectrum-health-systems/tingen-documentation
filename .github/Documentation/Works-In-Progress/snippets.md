# Development snippets

<see href="github.com/spectrum-health-systems/Tingen-Documentation/blob/main/Glossary.md#avatar-system-code">AvatarSystemCode</see>

<see href="github.com/spectrum-health-systems/Tingen-Documentation/blob/main/Glossary.md#avatar-script-parameter">SentScriptParameter</see>

 More information about OptionObjects <see href="github.com/spectrum-health-systems/Tingen-Documentation/blob/main/Glossary.md#avatar-optionobject">here</see>


/* Trace logs cannot be used here. For debugging purposes, use a Primeval log. */

/*[1]*/


/*
=================
DEVELOPMENT NOTES
=================

_Documentation updated ------
*/



// u240624.0843_code
// u240624.0843_documentation

At the end of each header, add an empty anchor with a chosen name — e.g. <a name="foo"></a>.
At the start of the document, list the headers with a link to their anchors — e.g. [Foo](#foo).


///             <listheader>
///                 <term>Setting</term>
///                 <description>Description</description>
///             </listheader>

/// <summary>Avatar-specific data and logic.</summary>
/// <remarks>
///     <para>
///         <b>About this class</b><br/>
///         This class should only contain the following Avatar-specific data:<br/>
///         <list type="bullet">
///             <item>The <paramref name="AvatarSystemCode"/></item>
///             <item>The <paramref name="SentScriptParameter"/></item>
///             <item>The <paramref name="SentOptionObject"/></item>
///             <item>The <paramref name="WorkOptionObject"/></item>
///             <item>The <paramref name="ReturnOptionObject"/></item>
///         </list>
///     </para>
///     <para>
///         <b>More information</b><br/>
///         <a href="https://github.com/spectrum-health-systems/Tingen-Documentation/blob/main/Glossary.md#avatar-optionobject">OptionObjects</a><br/>
///         <a href="https://github.com/spectrum-health-systems/Tingen-Documentation/blob/main/Glossary.md#avatar-script-paramater">Script Parameter</a><br/>
///         <a href="https://github.com/spectrum-health-systems/Tingen-Documentation/blob/main/Glossary.md#avatar-system-codes">System Codes</a>
///     </para>
///     <para>
///         <b>Also...</b><br/>
///         Please see the <a href="https://github.com/spectrum-health-systems/Tingen-Documentation">Tingen documentation</a> for more information.
///     </para>
/// </remarks>

/// <summary>The <a href="https://github.com/spectrum-health-systems/Tingen-Documentation/blob/main/Glossary.md#avatar-script-parameter">Script Parameter</a> sent from AvatarNX.</summary>

/// <summary>Builds a new AvatarData object.</summary>
/// <param name="sentOptionObject">The OptionObject sent from AvatarNX.</param>
/// <param name="sentScriptParameter">The ScriptParameter sent from AvatarNX.</param>
/// <remarks>
///     <para>
///         <b>About this method</b><br/>
///         - The <paramref name="sentScriptParameter"/> is converted to lowercase so it is easier to compare against.<br/>
///         - The <paramref name="workOptionObject"/> is cloned from the  <paramref name="sentOptionObject"/> so it can be modified without affecting the original data.<br/>
///         - The <paramref name="returnOptionObject"/> is initally set to "null", and will be formatted/finalized prior to returning to AvatarNX.
///     </para>
///     <para>
///         <b>More information</b><br/>
///         <a href="https://github.com/spectrum-health-systems/Tingen-Documentation/blob/main/Glossary.md#avatar-optionobject">OptionObjects</a><br/>
///         <a href="https://github.com/spectrum-health-systems/Tingen-Documentation/blob/main/Glossary.md#avatar-script-paramater">Script Parameter</a><br/>
///         <a href="https://github.com/spectrum-health-systems/Tingen-Documentation/blob/main/Glossary.md#avatar-system-codes">System Codes</a>
///     </para>
/// </remarks>
/// <returns>The necessary AvatarNX data.</returns>