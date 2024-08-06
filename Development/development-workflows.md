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
  - [Monthly](#monthly)
- [Development workflow components](#development-workflow-components)

# About Tingen development workflows

This document details the development workflows for Tingen projects.

# Development

## Daily

**Daily development** is the development that takes place during a single day.

### When daily development begins <!-- omit in toc -->

1. [Update file headers](#update-file-headers)
2. [Update the tnBuild value](#update-the-tnbuild-value)

### Throughout daily development <!-- omit in toc -->

- [Update the API documentation](#update-the-api-documentation)
- [Commit changes to the repository](#committing-changes-to-the-repository)

## Monthly

**Monthly development** takes place at the beginning of the month.

### When monthly development begins <!-- omit in toc -->

1. Update the AutoHotKey script
2. [Update file headers](#update-file-headers)
3. [Update the tnBuild value](#update-the-tnbuild-value)
4. [Update the AssemblyInfo.cs files](#update-the-assemblyinfocs-files)
5. [Update the Sandcastle help file versions](#update-the-sandcastle-help-file-versions)

<br>

***

<br>

# Development workflow components

These are the development components that are referenced in this document.  

They are stored here for easy updating.

## Update file headers <!-- omit in toc -->

Update the following file headers with the current build version:

- Tingen_development.asmx.cs
- WelcomeToOutpost31.cs

## Update tnBuild value <!-- omit in toc -->

Update the `tnBuild` value in `Core.Session.TingenSession.BuildStaticVars()`

## Update AssemblyInfo.cs files <!-- omit in toc -->

Update the following AssemblyInfo.cs files with the current version number:

- Tingen_development/Properties/AssemblyInfo.cs
- TOutpost31/Properties/AssemblyInfo.cs

## Update Sandcastle help file versions <!-- omit in toc -->

Update the Sandcastle "Help file version" in the following Sandcastle profiles:

- Tingen
- Outpost31

## Update API documentation <!-- omit in toc -->

1. Clean the Tingen solution

2. Rebuild the Tingen solution

3. Build the following Sandcastle projects:

   - Tingen
   - Outpost31

## Commit changes to the repository <!-- omit in toc -->

Commit changes for the following repositories:

- Tingen
- Outpost31
