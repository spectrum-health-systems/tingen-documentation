<!--
  u240805_work-in-progress
-->

<div align="center">

  ![logo](../.github/Images/Logos/TingenDocumentation-232x308.png)

  <h1>
    XML documentation
  </h1>

</div>

- [About Tingen XML documentation](#about-tingen-xml-documentation)
- [Source code XML documentation](#source-code-xml-documentation)
- [External XML documentation](#external-xml-documentation)
- [XML tag examples](#xml-tag-examples)

# About Tingen XML documentation

Tingen projects use both *source code* and *external XML* documentation.

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
/// <returns>A collection of remote paths.</returns>
```

# External XML documentation

The following XML documentation tags are stored in external files, in order to keep the source code cleaner/more readable:

- `<code>`
- `<example>`
- `<exception>`
- `<remarks>`
- `<see>`
- `<seealso>`
- `<value>`

## External files <!-- omit in toc -->

Each *namespace* has it's own external XML documentation file containing the external XML documentation for all *classes* in the namespace. The file is located in the project's `XMLDoc\` folder with the syntax of `%namespace%_doc.xml`

For example, XML documentation for the `Outpost31.Logger` namespace is located in the `Outpost31\XMLDoc\Logger_doc.xml` file, and contains all of the external XML documentation for all of the classes in the `Outpost31.Logger` namespace.

## Source code documentation structure <!-- omit in toc -->

Source code XML documentation should follow these guidelines:

- An HTML comment at the top of the file indicating the last changed date
- XML documentation tags should be propery indented
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
