<!-- u251008 -->

<div align="center">

  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://github.com/spectrum-health-systems/tingen-projects/blob/main/logos/tngndocs-dark-400x63.png">
    <source media="(prefers-color-scheme: light)" srcset="https://github.com/spectrum-health-systems/tingen-projects/blob/main/logos/tngndocs-light-400x63.png">
    <img alt="Fallback image description" src="https://github.com/spectrum-health-systems/tingen-projects/blob/main/logos/tngndocs-light-400x63.png">
  </picture>
  <h4>Tingen Web Service</h4>
  <h1>The Script Parameter</h1>

</div>

### Contents

[About](#about)  
[Valid commands](#valid-commands)  

# About

The Script Parameter is the **request** that Avatar sends, along with the OptionObject, to the Tingen Web Service.

> [!TIP]
> Tingen projects use the terms *Script Parameter* and *request* interchangeably

The maximum length of a script parameter is 48 characters.





# Valid requests

As of R25.9, the following are valid Script Parameters:

* 




# The Script Parameter

## CONTENTS
[Overview](#overview)
[Components](components)
[Syntax](#syntax)

# Overview
The Script Parameter sent from Avatar contains all of the information Abatab needs to do what it needs to do, including:

* The requested `Module`  
* The requested `Command`
* The requested `Action`
* The requested `Option`




<br>

# Script Parameters

## Syntax





Script Parameters have the following syntax:

    `Module-Command-Action-Option`

For example:

    `ProgNote-VfyLoc-IndiCounselingNote`

The maximum length of a script parameter is 48 characters.

* The `MODULE` component is 8 characters, or less
* The `COMMAND` component is 12 characters, or less (see below)
* The `ACTION` component is 16 characters, or less
* The `OPTION` component is 2 characters, or less

```
12345678-123456789012-1234567890123456-12
MODULE__-COMMAND_____-ACTION__________-OP
```


The `COMMAND` can consist of a *command prefix*, which is 3 characters, leaving 9 characters for the rest of the command.

```
123
   123456789
PreCommand__
```

## Scr

`Testing-DataDump-SessionInformation`  
`Testing-ErrorCode-ErrorCode1`  

### PROGRESSNOTE
`MODULE__-COMMAND_____-ACTION__________-OP`
`ProgNote-VfyLoc-GroupIndiNote`
`ProgNote-VfyLoc-IndiCounselingNote`  

### QUICKMEDICATIONORDER
`QMedOrdr-vfyAmount-Dose`


## Abbreviations

### Module

Module abbreviations are 8 characters.

* ProgNote = Progress Note
* Proto    = Prototype
* QMedOrdr = Quick Medication Order
* Testing  = Testing

### Keywords

Keyword abbreviations are 4 characters.

* Vfy  = Verify  

### Other abbreviations

* Loc  = Location
* Indi = Individual/Individualized
* Inde = Independent

<br>

***

<div align="center">

  This document is part of the [Abatab Documentation Project](../Abatab%20Documentation%20Project.md).

  <h5>
    Last updated: 230329.1117
  </h5>

</div>
