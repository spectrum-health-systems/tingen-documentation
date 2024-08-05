<!--
  u240805_work-in-progress
-->

<div align="center">

  ![logo](../.github/Images/Logos/TingenDocumentation-232x308.png)

  <h1>
    Tingen development workflows
  </h1>

</div>

### TABLE OF CONTENTS
- [About Tingen development workflows](#about-tingen-development-workflows)
- [Development](#development)
  - [Daily](#daily)
    - [When daily development begins](#when-daily-development-begins)
    - [Throughout daily development](#throughout-daily-development)
  - [Monthly](#monthly)
    - [When monthly development begins](#when-monthly-development-begins)
- [Development components](#development-components)
  - [Update file headers](#update-file-headers)
  - [Update tnBuild value](#update-tnbuild-value)
  - [Update AssemblyInfo.cs files](#update-assemblyinfocs-files)
  - [Update Sandcastle help file versions](#update-sandcastle-help-file-versions)
  - [Update API documentation](#update-api-documentation)

# About Tingen development workflows

# Development

## Daily

### When daily development begins

1. [Update file headers](#update-file-headers)
2. [Update the tnBuild value](#update-the-tnbuild-value)

### Throughout daily development

- [Update the API documentation](#update-the-api-documentation)

## Monthly

### When monthly development begins

1. Update the AutoHotKey script
2. [Update file headers](#update-file-headers)
3. [Update the tnBuild value](#update-the-tnbuild-value)
4. [Update the AssemblyInfo.cs files](#update-the-assemblyinfocs-files)
5. [Update the Sandcastle help file versions](#update-the-sandcastle-help-file-versions)

<br>

***

<br>

# Development components

These are the development components that are referenced in this document.  

They are stored here for easy updating.

## Update file headers

Update the following file headers with the current build version:

- Tingen_development.asmx.cs
- WelcomeToOutpost31.cs

## Update tnBuild value

Update the `tnBuild` value in `Core.Session.TingenSession.BuildStaticVars()`

## Update AssemblyInfo.cs files

Update the following AssemblyInfo.cs files with the current version number:

- Tingen_development/Properties/AssemblyInfo.cs
- TOutpost31/Properties/AssemblyInfo.cs

## Update Sandcastle help file versions

Update the Sandcastle "Help file version" in the following Sandcastle profiles:

- Tingen
- Outpost31

## Update API documentation

1. Clean the Tingen solution

2. Rebuild the Tingen solution

3. Build the following Sandcastle projects:

   - Tingen
   - Outpost31

4. Commit changes for the following repositories:

   - Tingen
   - Outpost31
