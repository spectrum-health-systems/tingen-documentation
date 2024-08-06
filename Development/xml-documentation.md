<!--
  u240805_work-in-progress
-->

<div align="center">

  ![logo](../.github/Images/Logos/TingenDocumentation-232x308.png)

  <h1>
    XML documentation
  </h1>

</div>

### CONTENTS
- [About Tingen XML documentation](#about-tingen-xml-documentation)
- [Source code XML documentation](#source-code-xml-documentation)
- [External XML documentation](#external-xml-documentation)
- [The Tingen Glossary](#the-tingen-glossary)
- [XML tag examples](#xml-tag-examples)
  - [See](#see)
  - [SeeAlso](#seealso)

<br>

# About Tingen XML documentation

Tingen projects use both *source code* and *external* XML documentation.

**Source code XML documentation** should provide all *required* information about a component.

**External XML documentation** should provide *non-essential but helpful* detailed information, examples, and other resources for a component.

## What should be documented <!-- omit in toc -->

The following source code components should be commented:

- Classes
- Properties
- Methods

# Source code XML documentation

The following XML documentation tags are used directly in the *source code*, since they are helpful when viewing the source code.

- `<summary>`
- `<param>`
- `<returns>`

## Source code documentation structure <!-- omit in toc -->

Source code XML documentation should follow these guidelines:

- Comments (including tags) should fit on a single line
- Comments (not including tags) should not exceed 120 characters

## Example of source code XML documentation <!-- omit in toc -->

```csharp
/// <summary>Builds the remote paths object.</summary>
/// <param name="tnDataRoot">The Tingen data root.</param>
/// <remarks>These paths are important to the functionality of things.</remarks>
/// <returns>A collection of remote paths.</returns>
```

# External XML documentation

The following XML documentation tags are stored in external files, in order to keep the source code cleaner/more readable:

- `<code>`
- `<example>`
- `<exception>`
- `<see>`
- [`<seealso>`](#seealso)
- `<value>`

If a `<remarks>` entry is longer than a single line, it should contained in an external file, not the source code.

## External files <!-- omit in toc -->

Each *namespace* has it's own external XML documentation file containing the external XML documentation for all *classes* in the namespace. The file is located in the project's `XMLDoc\` folder with the syntax of `%namespace%_doc.xml`

For example, XML documentation for the `Outpost31.Logger` namespace is located in the `Outpost31\XMLDoc\Logger_doc.xml` file, and contains all of the external XML documentation for all of the classes in the `Outpost31.Logger` namespace.

## Source code documentation structure <!-- omit in toc -->

Source code XML documentation should follow these guidelines:

- An HTML comment at the top of the file indicating the last changed date
- XML documentation tags should be properly indented
- Comments (not including tags) should not exceed 120 characters

## Example of source code XML documentation <!-- omit in toc -->

```xml
<!--
    u240805.0855_documentation
-->

<Doc>
    <Sec name="ClassName">
        <MethodName>
            <remarks>
                <para>
                    This is a list
                    <list type="bullet">
                        <item>
                            Bullet 1
                        </item>
                        <item>
                            Bullet 2
                        </item>
                    </list>
                    <br/>
                    More comments.
                    <br/>
                    More comments.
                </para>
            </remarks>
        </MethodName>
        <PropertyName>
            <remarks>
                <para>
                    Remarks about the property.
                </para>
            </remarks>
        </PropertyName>
    </Sec>
</Doc>
```

## Referencing external XML documentation in the source code <!-- omit in toc -->

To reference external XML documentation in the source code, add the following line at the end of the source code XML documentation:

```csharp
/// <include file='XMLDoc/FileName_doc.xml' path='Doc/Sec[@name="ClassName"]/MethodName/*'/>
```

For example:

```csharp
/// <summary>Starts the Tingen web service.</summary>
/// <param name="sentOptionObject">The OptionObject sent from Avatar.</param>
/// <param name="sentScriptParameter">The ScriptParameter sent from Avatar.</param>
/// <returns>The finalized OptionObject to myAvatar.</returns>
/// <include file='XMLDoc/Tingen_doc.xml' path='Doc/Sec[@name="tingen"]/RunScript/*'/>
```

# The Tingen Glossary

The [Tingen Glossary](../Glossary.md) is a permanent, living document that contains important keywords and terminology related to Tingen projects.

The idea is that you can always reference the glossary, and use it to reference topics that may change over time. For that reason, glossary terminology is kept as simpld and static as possible, in order to maintain compatibility with XML documentation, no matter when it was written.

And the glossary is ***always*** located here: http://github.com/spectrum-health-systems/Tingen-Documentation/blob/main/Glossary.md

## Glossary format <!-- omit in toc -->

The glossary format looks like this:

```md
# Topic header

A short description of the `topic header` goes here. 

The `topic header` is rarely referenced in XML documentation.

## Topic sub-header 1

The `topic sub-header 1` is generally what the XML documentation will reference, and should therefore have a detailed description of what it is/what it does.

You can also reference other topics here.
```

For example:

```md
# Tingen

**Tingen** is a custom web service for Avatar, and is called via a ScriptLink event on a form.  

Perhaps surprisingly, Tingen doesn’t actually do any work, it just accepts data sent from Avatar, and passes it along to [Outpost31](#outpost31).

## Tingen Modes

Tingen operates in one of the following *modes*:

| Mode | Description |
| ---- | ----------- |
| `enabled` | Tingen functions normally. |
| `disabled` | Tingen is disabled, and doesn't do anything. |
```

## Referencing the glossary in XML documentation <!-- omit in toc -->

You can reference the glossary in XML comments - either in the source code, or external file - by using the following syntax:

```csharp
/// <a href="http://github.com/spectrum-health-systems/Tingen-Documentation/blob/main/Glossary.md#%TerminologyAnchor%">%Terminology%</a>
```

For example:

```csharp
/// <a href="http://github.com/spectrum-health-systems/Tingen-Documentation/blob/main/Glossary.md#tingen-configuration">Configuring Tingen</a>
```

# XML tag examples

## Lists <!-- omit in toc -->

### Bullet list <!-- omit in toc -->

Bulleted lists should follow these guidelines:

- All items (including tags) should fit on a single line
- Item text should not exceed 120 characters
- Items should not end, or contain, periods
- Proper indenting should be used

```xml
<para>
    An introduction:
    <list type="bullet">
      <item>Bullet 1</item>
      <item>Bullet 1</item>
      <item>Bullet 1</item>
    </list>
</para>
```

### Numbered list <!-- omit in toc -->

TBA

## Tables <!-- omit in toc -->

Tables should follow these guidelines:

- An optional `listheader` may be used
- All items (including tags) should fit on a single line
- Item text should not exceed 120 characters
- Items should not end, or contain, periods
- Proper indenting should be used

```xml
<para>
    An introduction:
    <list type="table">
        <listheader>
            <term>Term header</term>
            <description>Description header</description>
        </listheader>
        <item>
            <term>Term 1</term>
            <description>Description 1</description>
        </item>
        <item>
            <term>Term 2</term>
            <description>Description 3</description>
        </item>
    </list>
</para>
```

## See

```csharp
Please see the <see href="github.com/spectrum-health-systems/Tingen-Documentation/blob/main/Glossary.md#avatar-optionobject">Tingen documentation</see> for more information.
```

## SeeAlso

```csharp
<seealso href="https://github.com/spectrum-health-systems/Tingen-Documentation/blob/main/Glossary.md#avatar-system-codes">System Codes</seealso>
```

<!-- 

<paramref name="ReturnOptionObject"/>

See <see cref="GetVersion()"/> to add doubles.

<seealso cref="GetVersion()"/>

<i>Module</i>

<see cref="member"/>
<see cref="member">Link text</see>
<see href="link">Link Text</see>
<see langword="keyword"/>

<seealso cref="member"/>

<seealso href="link">Link Text</seealso>
 -->
