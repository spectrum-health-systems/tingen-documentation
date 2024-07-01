

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
<!-- or -->
<see cref="member">Link text</see>
<!-- or -->
<see href="link">Link Text</see>
<!-- or -->
<see langword="keyword"/>


<seealso cref="member"/>
<!-- or -->
<seealso href="link">Link Text</seealso>


-->

<div align="center">

  ![logo](./.github/images/logos/TingenDocumentation_README.png)

  <h1>
  TINGEN / OUTPOST31 GLOSSARY
  </h1>

</div>


Tingen Glossary

This is a standing/living document that contains information about Tingen components.

# Avatar

## Avatar System Codes

Information about the Avatar System Code goes here.

## Avatar Script Parameter

Information about the Avatar Script Parameter goes here.

## Avatar OptionObject

Information about Avatar OptionObjects go here.

### OptionObject error codes

Information about OptionObject error messages go here.

# Tingen

## Tingen Configuration

Information about configuring Tingen goes here.

## Tingen Modes
///   Setting the mode to <i>disabled</i> is the equivalent of disabling ScriptLink calls on every form that uses Tingen. This
///   is a good way to "turn off" the web service quickly, without having to modify every form that uses it.<br/><br/>
///   When disabled, the majority of the work is done in <b>Tingen.asmx.cs</b>, not in Outpost31, so it should have an
///   insignificant affect on Avatar's performance.<br/><br/>
///   You can also enable/disable individual Modules, Commands, and Actions via their associated configuration files.
///   This allows you to disable specific functionality without affecting the rest of Tingen.

### Module Modes
///   <b>More information about the Open Incident Module mode setting:</b><br/>
///   Setting the mode to <i>disabled</i> is the equivalent of disabling any calls to the Open Incident Module.<br/><br/>
///   This is a good  way to "turn off" the the Open Indident Module functionality, without having disable the entire Tingen
///   web service.


# Logging

## Trace logs

///   <b>More information about the trace log level:</b><br/>
///   Trace logs calls include a <i>log level</i> parameter.<br/><br/>
///   If the log level of the call is <i>less than or equal</i> to the TraceLogLevel, the log will be written. Otherwise,
///   the log will be skipped.<br/><br/>
///   This allows you to place log calls throughout the code, and then control the amount of logging that is done when Tingen
///   is executed.<br/><br/>

## Primeval logs


# Outpost31

Information about Outpost31 goes here.