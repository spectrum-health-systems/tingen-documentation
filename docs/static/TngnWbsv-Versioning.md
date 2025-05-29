<!-- u250501 -->

<div align="center">

  ![logo](/.github/image/logo/TingenDevelopmentDocumentation_logo_320x420.png)

  ![TINGEN_VERSION](https://img.shields.io/badge/TINGEN%2025.5-white?style=for-the-badge)
  
  <h1>Tingen Web Service versioning</h1>

</div>

<br>

The Tingen Web Service is closer to Semantic versioning than the Microsoft versioning scheme, and consists of up to three components:

* The release year
* The release month
* An optional patch number

Or:

```
YY.MM.Patch
```

Put those together and you get a version number that looks like this:  

```
25.02.1
```

This isn't 'Nam, there are rules:

* The **YY** is two digits (e.g., 2025 would be `25`)
* The **MM** component is two digits (e.g., July would be `07`)
* The **Patch** component is a single digit, and is `0` if there are no patches
* The `Revision` component in the <i>AssemblyInfo.cs</i> file) is always `0`

For each release of Tingen the following lines:

```csharp
[assembly: AssemblyVersion("Major.Minor.Build.Revision")]
[assembly: AssemblyFileVersion("Major.Minor.Build.Revision")]
```

Need to be modified as so:

```csharp
[assembly: AssemblyVersion("YY.MM.Patch.0")]
[assembly: AssemblyFileVersion("YY.MM.Patch.0")]
```

So, for example the December 2024 release, without a patch, would look like this:

```csharp
[assembly: AssemblyVersion("24.12.0.0")]
[assembly: AssemblyFileVersion("24.12.0.0")]
```