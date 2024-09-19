<!-- u240919 -->

<div align="center">

  ![BranchWarning](https://img.shields.io/badge/WORK%20IN%20PROGRESS-yellow?style=for-the-badge)

  ![logo](../../.github/Images/Logos/TingenDocumentation-232x308.png)

  <h1>
    Tingen monthly development workflow
  </h1>

</div>

# 1. Update the AutoHotKey script

# 2. Update file headers

Update the following file headers with the current build version:

- Tingen_development.asmx.cs
- WelcomeToOutpost31.cs

# 3. Update the tnBuild value

Update the `tnBuild` value in `Core.Session.TingenSession.BuildStaticVars()`

# 4. Update the AssemblyInfo.cs files

Update the following AssemblyInfo.cs files with the current version number:

- Tingen_development/Properties/AssemblyInfo.cs
- TOutpost31/Properties/AssemblyInfo.cs

# 5. Update the Sandcastle help file versions

Update the Sandcastle "Help file version" in the following Sandcastle profiles:

- Tingen
- Outpost31
