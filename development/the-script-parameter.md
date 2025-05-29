<!-- 250430 -->

<div align="center">

  ![logo](/.github/image/logo/TingenDevelopmentDocumentation_logo_320x420.png)

  ![TINGEN_VERSION](https://img.shields.io/badge/TINGEN%2025.5-white?style=for-the-badge)
  
  <h1>The Script Parameter</h1>

</div>

<br>

## CONTENTS
[Overview](#overview)
[Components](components)
[Syntax](#syntax)

# Overview
The Script Parameter sent from Avatar contains all of the information that the Tingen Web Service needs to do what it needs to do.

The maximum length of a script parameter is 50 characters, and includes:

* The requested `Module` (the *namespace*)
* The requested `Command` (the *class*)
* The requested `Request` (the *method*)
* The requested `Option`

Components are seperated by a "`.`"

For example:

`Admin.Status.Current`

# Valid standard requests

```
12345678901234-1234567890-12345678901234567890-123
Module........-Command...-Action..............-Opt
```

* `Admin.Status.Current`
* `FormAccess.Deny.SysCodeDoc`
* `FormAccess.Deny.SysCodeDocHoc`
* `FormAccess.Deny.SysCodeList01`

## Prototypes

```
12345678901234-1234567890-12345678901234567890-123
Module........-Command...-Action..............-Opt
```

* `_pFormAccess.Deny.DocSysCode`




# Valid Script Parameters




## Prototypes

* _pDocSysCodeDenyAccessToForm

* Prototype.DocSysCode.DenyAccessToForm
* Admin.Status.Current
QuickMedicationOrder.Verify.Dose