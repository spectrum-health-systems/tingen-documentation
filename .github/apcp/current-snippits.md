
```csharp
/// <summary>The executing assembly name.</summary>
/// <remarks>
///   This is a required component of most log files, and is defined at the start of each class, so it can be<br/>
///   used at any time that a log needs to be created.
/// </remarks>
public static string ExeAsmName { get; set; } = Assembly.GetExecutingAssembly().GetName().Name;
```