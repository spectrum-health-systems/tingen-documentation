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

* The requested `Module`  
* The requested `Command`
* The requested `Request`
* The requested `Option`

## The `Module` component

- The (abreviated) name of the module.
- 14 characters, or less

### Module abbreviations

| Module name | Abbreviation |
| ----------- | ------------ |
| Admin       | Admin |
| Form Access | `FrmAccess` |
| Open Incident | `OpenIncident` |
| Prototype code | `_p` |
| Quick Medication Order | `QuickMedOrder` |

## The `Command` component

- What you want the Tingen Web Service to do, broadly
- 10 characters, or less

### Command abbreviations

| Command     | Abbreviation | Description |
| ----------- | ------------ | ----------- |
| Deny        | `Deny`       | Deny something |
| Verify      | `Vfy`        | Verify something |

## The `Request` component

- What you want the Tingen Web Service to do, specifically
- 20 characters, or less

### Request component abbreviations

| Command     | Abbreviation |
| ----------- | ------------ |
| Department of Corrections | `DeptOfCx` |
| Individual/Individualized | `Indv` |
| Independent | `Indep` |
| Location | `Loc` |
| Verify      | `Vfy`        |

## The `Option` component

- Options

## Examples

```
12345678901234-1234567890-12345678901234567890-123
Module........-Command...-Action..............-Opt
```

`ProgressNote-VerifyLocation-GroupIndividualNote`

# Valid Script Parameters

## Prototypes

* _pDocSysCodeDenyAccessToForm

* Prototype.DocSysCode.DenyAccessToForm
* Admin.Status.Current
QuickMedicationOrder.Verify.Dose