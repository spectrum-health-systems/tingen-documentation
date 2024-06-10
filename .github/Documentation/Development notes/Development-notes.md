# Tingen Development Notes

- Encrypt data saved via `FieldOperation.SaveValue()`?

- Save an OO for testing?
- Service status message in data root
-  Verify "disabled" works (OO is returned correctly)
- trace logs

Notes in remarks when tracelogs can't be used


Commander/lieutenant/archive aren't specific to Tengen

Live/Primeval/public/remote/uat are

review which primeval logs can be trace logs

More places to create service status files

## Tingen_development.asmx.cs

### RunScript()

- Add a "development" case
- Maybe send out emails when the service is/is not enabled.



if (traceLevel != 0) and (traceLevel <= traceLogMode)
{
    Do work to workOptionObject
}

        ///   - Modules/Commands/Actions have their own modes, which can be set in the module's configuration file.<br/>

returnOptionObject = workOptionObject.Clone()

Session\YYMMDD\UserId\HHMM\trace\fffffff_calledClass-lineNumber.trace


        ///  <para>
        ///   - Tingen uses the following hardcoded variables, which are set in <see cref="TingenSession.BuildStaticVars()"/>"<br/>
        ///   <list type="table">
        ///    <item>
        ///     <term>tnVersion</term>
        ///     <description>The current version of Tingen, in <b>YY.MM.y.z</b> format.</description>
        ///    </item>
        ///    <item>
        ///     <term>tnDataRoot</term>
        ///     <description>The Tingen data root, set to <b>C:\TingenData\</b>.</description>
        ///    </item>
        ///    <item>
        ///     <term>avSystemCode</term>
        ///     <description>The Avatar System Code, which should match your Avatar environment.</description>
        ///    </item>
        ///    <item>
        ///     <term>tnConfigFileName</term>
        ///     <description>The name of the Tingen configuration file, <b>Tingen.config</b>.</description>
        ///    </item>
        ///   </list>
        ///  </para>