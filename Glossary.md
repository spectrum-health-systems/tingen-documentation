<!--
  u240805_work-in-progress
-->

<div align="center">

  <img src="TingenDocumentation_small.png"> 

  <br>

  <h1>
    GLOSSARY
  </h1>

</div>

- [Tingen](#tingen)
  - [Tingen Configuration](#tingen-configuration)
  - [Tingen Modes](#tingen-modes)
- [Outpost31](#outpost31)
- [Logging](#logging)
  - [Trace logs](#trace-logs)
  - [Primeval logs](#primeval-logs)
- [Modules](#modules)
  - [Module Modes](#module-modes)
  - [Open Indicent Module](#open-indicent-module)
- [Avatar](#avatar)
  - [Avatar System Codes](#avatar-system-codes)
  - [Avatar Script Parameter](#avatar-script-parameter)
  - [Avatar OptionObject](#avatar-optionobject)
    - [OptionObject error codes](#optionobject-error-codes)

# Tingen

**Tingen** is a custom web service for Avatar, and is called via a ScriptLink event on a form.  

Perhaps surprisingly, Tingen doesn’t actually do any work, it just accepts data sent from Avatar, and passes it along to [Outpost31](#outpost31).

## Tingen Configuration

Information about configuring Tingen goes here.

## Tingen Modes

Tingen operates in one of the following *modes*:

| Mode | Description |
| ---- | ----------- |
| `enabled` | Tingen functions normally. |
| `disabled` | Tingen is disabled, and doesn't do anything. |

# Outpost31

When Tigen is called via a ScriptLink event, a [Script Parameter](URL) is passed to Tingen. That Script Parameter is then passed to Outpost31, which does most of the work.

# Logging

## Trace logs

Trace logs calls include a *log level* parameter.

If the log level of the call is *less than or equal* to the TraceLogLevel, the log will be written. Otherwise, the log will be skipped.

This allows you to place log calls throughout the code, and then control the amount of logging that is done when Tingen is executed.

## Primeval logs

TBD

# Modules

## Module Modes

Tingen modules operate in one of the following *modes*:

| Mode | Description |
| ---- | ----------- |
| `enabled` | The module functions normally. |
| `disabled` | The module is disabled, and doesn't do anything. |

Disabling a module only affects that specific module, other modules/components of Tingen will function according to their specific mode.

## Open Indicent Module

# Avatar

## Avatar System Codes

Information about the Avatar System Code goes here.

## Avatar Script Parameter

Information about the Avatar Script Parameter goes here.

## Avatar OptionObject

Information about Avatar OptionObjects go here.

### OptionObject error codes

Information about OptionObject error messages go here.
