# XML comments

## External XML documentation files

Naming convention: `%namespace%_doc.xml`

Header:

```html
<!--
    u240709.0842_documentation
-->
```

Include statement:

` /// <include file='XMLDoc/Tingen_doc.xml' path='Doc/Sec[@name="tingen"]/Tingen/*'/>`



## Bullet list

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

## Table

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


## Class description

* Overview of class.
* <paramref>, not <href>

## Method description

* Overview of method
* <paramref> and <href>

# External XML documentation

External XML file tags
  * `<remarks>` - Additional information about the member.
  * `<example>` - An example of how to use the member.
  * `<code>` - A code element.
  * `<see>` - A reference to another member.
  * `<seealso>` - A reference to another member
  * `<exception>` - A description of an exception that can be thrown by a method.