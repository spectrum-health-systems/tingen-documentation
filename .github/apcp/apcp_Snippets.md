<!-- u250306 -->

# DEVELOPMENT GUIDELINES

Guidelines for the following can be found [here](https://github.com/APrettyCoolProgram/APrettyCoolProgram):

* Classes/methods
* Syntax
* Formatting
* Versioning
* Comments
* XML documentation
* File headers
* Mermaid


### HTML files

```html
<!-- u240820 -->
```

# COMMENTS

# Class links to documentation

```csharp
/// <seealso href="https://github.com/spectrum-health-systems/tingen-documentation-project">Tingen Documentation Project</seealso>
/// <seealso href="https://spectrum-health-systems.github.io/tingen-documentation-project/api">Tingen API Documentation</seealso>
```

# CODE

## Executing Assembly name

```csharp
/// <summary>The executing assembly name.</summary>
/// <remarks>A required log component, defined here so it can be used throughout the class.</remarks>
public static string ExeAsm { get; set; } = Assembly.GetExecutingAssembly()
                                                    .GetName().Name;
```

## Creating a Primeval Log

```csharp
LogEvent.Primeval(Assembly.GetExecutingAssembly().GetName().Name);
```

# Log warnings

## No Trace Logs

```csharp
/* Trace Logs can't go here because the logging infrastructure hasn't been initialized yet.
 */
```

or

```csharp
/* Trace Logs won't work here. */
```

## No Trace Logs or Primeival Logs

```csharp
/* Trace Logs can't go here because the logging infrastructure hasn't been initialized yet.
 *
 * Primeval Log can't go since that may result in an infinite loop/stack overflow when the
 * Primeval log directory is being refreshed.
 */
```

or

```csharp
/* Trace/Primeval Logs won't work here. */
```

# Development note comments

```csharp
/*
[DN01] 240817
Make the following changes:
  - Change #1
  - Change #2
*/
```


# Source code comment types

```
// -DEPRECIATED- %optional-note%
// %code%

or 

/* -DEPRECIATED- %optional-note%
%code%
*/
```

```
// #DEVNOTE#
// %note%

or

/* #DEVNOTE#
%note%
*/
```

```
// !IMPORTANT!
// %note%

or 

/* !IMPORTANT!
%note%
*/
```

```
// {REFACTOR}
// %note%

or 

/* {REFACTOR}
%note%
*/
```

```
// @TODO@
// %note%

or

/* @TODO@
%note%
*/
```

# Abbreviations

Avtr          = Avatar
Env           = Environment
OptObj        = OptionObject
Rntm          = Runtime
Slnk          = Scriptlink
SysCode       = System Code
Tngn          = Tingen
TngnWbSv      = Tingen Web Service

## OptionObject

The OptionObject contains all of the content of and metadata describing the calling myAvatar form

## Method notes

<note title="Important information about this method">
    <list type="bullet">
        <item>This method is required by Avatar and <i>should not be modified</i>.</item>
        <item>
            Trace Logs can't go here because the logging infrastructure<br/>
            hasn't been initialized yet.
        </item>
    </list>
</note>


## pull request

```
**This is a development release**

**DO NOT USE IN PRODUCTION ENVIRONMENTS**

You are probably looking for this:

[Tingen Web Service Community Release](https://github.com/spectrum-health-systems/tingen-community-release)
```

```
/// <seealso href="https://github.com/spectrum-health-systems/tingen-documentation-project">Tingen Documentation Project</seealso>
```