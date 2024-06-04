# Tingen Development Notes

- Encrypt data saved via `FieldOperation.SaveValue()`?

- Save an OO for testing?
- Service status message in data root
-  Verify "disabled" works (OO is returned correctly)
- trace logs

if can't trace or other log, primeval

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

returnOptionObject = workOptionObject.Clone()

Session\YYMMDD\UserId\HHMM\trace\fffffff_calledClass-lineNumber.trace






/* <!-- For debugging: LogEvent.Primeval(asm); --> */ // To be removed.

/*

Development notes

- Remove the Primeval calls, potentially replace with Tracelogs.
- If logs aren't written, remove the Asm property.

*/




        ///  <para>
        ///   The only difference between the development and production versions of this class is the value of <c>configFilePath</c>:
        ///   <list type="table">
        ///    <item>
        ///     <term>Development</term>
        ///     <description>C:\Tingen\UAT\Configs\Tingen.config</description>
        ///    </item>
        ///    <item>
        ///     <term>Production</term>
        ///     <description>C:\Tingen\LIVE\Configs\Tingen.config</description>
        ///    </item>
        ///   </list>
        ///  </para>
        ///  <para>
        ///   Tingen has the following modes:
        ///   <list type="table">
        ///    <item>
        ///     <term>Enabled</term>
        ///     <description>Work is done, and a modified sentOptionObject is returned to Avatar</description>
        ///    </item>
        ///    <item>
        ///     <term>Disabled</term>
        ///     <description><i>No work</i> is done, and the <i>unmodified</i> sentOptionObject is returned to Avatar</description>
        ///    </item>
        ///   </list>
        ///  </para>