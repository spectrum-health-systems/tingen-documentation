<!--

- More information about <see href="github.com/spectrum-health-systems/Tingen-Documentation/blob/main/Glossary.md#avatar-optionobject">here</see>.

<paramref name="ReturnOptionObject"/>

<i>Module</i>

-->





# Tingen Glossary

This is a standing/living document that contains information about Tingen components.

## Avatar

### Avatar System Codes

Information about the Avatar System Code goes here.

### Avatar Script Parameter

Information about the Avatar Script Parameter goes here.

### Avatar OptionObject

Information about Avatar OptionObjects go here.

#### OptionObject error codes

Information about OptionObject error messages go here.

## Tingen

### Tingen Configuration

Information about configuring Tingen goes here.

### Tingen Modes
///   Setting the mode to <i>disabled</i> is the equivalent of disabling ScriptLink calls on every form that uses Tingen. This
///   is a good way to "turn off" the web service quickly, without having to modify every form that uses it.<br/><br/>
///   When disabled, the majority of the work is done in <b>Tingen.asmx.cs</b>, not in Outpost31, so it should have an
///   insignificant affect on Avatar's performance.<br/><br/>
///   You can also enable/disable individual Modules, Commands, and Actions via their associated configuration files.
///   This allows you to disable specific functionality without affecting the rest of Tingen.

#### Module Modes
///   <b>More information about the Open Incident Module mode setting:</b><br/>
///   Setting the mode to <i>disabled</i> is the equivalent of disabling any calls to the Open Incident Module.<br/><br/>
///   This is a good  way to "turn off" the the Open Indident Module functionality, without having disable the entire Tingen
///   web service.


### Logging

#### Trace logs

///   <b>More information about the trace log level:</b><br/>
///   Trace logs calls include a <i>log level</i> parameter.<br/><br/>
///   If the log level of the call is <i>less than or equal</i> to the TraceLogLevel, the log will be written. Otherwise,
///   the log will be skipped.<br/><br/>
///   This allows you to place log calls throughout the code, and then control the amount of logging that is done when Tingen
///   is executed.<br/><br/>

#### Primeval logs


## Outpost31

Information about Outpost31 goes here.

###