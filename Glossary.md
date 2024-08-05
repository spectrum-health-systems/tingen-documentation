<!--

This is a standing document that is referenced in the source code for Tingen, Tingen_development, and Outpost31.

Entries in this document should follow this format:

# Main header - generally not referenced in source code

%Description%

## Sub-entry level 1 - always referenced in source code

### Sub-entry level 2 - not referenced in source code

#### Sub-entry level 3 - not referenced in source code

Only the `#` entry is referenced in the source code, and should remain static (so name it correctly the first time!).

The %Description% should give a good overview, and explain why the user should be looking at sub entries.

---

Source code should contain the following XML comments:

- More information about <see href="github.com/spectrum-health-systems/Tingen-Documentation/blob/main/Glossary.md#avatar-optionobject">here</see>.

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

<div align="center">

  <img src="TingenDocumentation_small.png"> 

  <br>

  <h1>
    GLOSSARY
  </h1>

</div>

- [Tingen](#tingen)
- [Outpost31](#outpost31)
- [Logging](#logging)
- [Modules](#modules)
- [Avatar](#avatar)

# Tingen

**Tingen** is a custom web service for Avatar, and is called via a ScriptLink event on a form.  

Perhaps surprisingly, Tingen doesn’t actually do any work, it just accepts data sent from Avatar, and passes it along to [Outpost31](#outpost31).

## Tingen Configuration <!-- omit from toc -->

Information about configuring Tingen goes here.

## Tingen Modes <!-- omit from toc -->

Tingen operates in one of the following *modes*:

| Mode | Description |
| ---- | ----------- |
| `enabled` | Tingen functions normally. |
| `disabled` | Tingen is disabled, and doesn't do anything. |

# Outpost31

When Tigen is called via a ScriptLink event, a [Script Parameter](URL) is passed to Tingen. That Script Parameter is then passed to Outpost31, which does most of the work.

# Logging

## Trace logs <!-- omit from toc -->

Trace logs calls include a *log level* parameter.

If the log level of the call is *less than or equal* to the TraceLogLevel, the log will be written. Otherwise, the log will be skipped.

This allows you to place log calls throughout the code, and then control the amount of logging that is done when Tingen is executed.

## Primeval logs <!-- omit from toc -->

TBD

# Modules

## Module Modes <!-- omit from toc -->

Tingen modules operate in one of the following *modes*:

| Mode | Description |
| ---- | ----------- |
| `enabled` | The module functions normally. |
| `disabled` | The module is disabled, and doesn't do anything. |

Disabling a module only affects that specific module, other modules/components of Tingen will function according to their specific mode.

## Open Indicent Module <!-- omit from toc -->

# Avatar

## Avatar System Codes <!-- omit from toc -->

Information about the Avatar System Code goes here.

## Avatar Script Parameter <!-- omit from toc -->

Information about the Avatar Script Parameter goes here.

## Avatar OptionObject <!-- omit from toc -->

Information about Avatar OptionObjects go here.

### OptionObject error codes <!-- omit from toc -->

Information about OptionObject error messages go here.
