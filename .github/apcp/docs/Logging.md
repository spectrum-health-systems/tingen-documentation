# Logging

## Trace logs

<list type="table">
    <listheader>
        <term>Level</term>
        <description>Type of log written</description>
    </listheader>
    <item>
        <term>0</term>
        <description>Trace logs are disabled.</description>
    </item>
    <item>
        <term>1</term>
        <description>Method trace logs are created.</description>
    </item>
    <item>
        <term>2...9</term>
        <description>Statement/loop trace logs are written.</description>
    </item>
</list>




/// <summary>The trace logging level.</summary>
/// <remarks>
///  <para>
///   - Trace logs with a level less than or equal to the <paramref name="TraceLevel"/> will be written.<br/>
///   - Trace logs are written to <i>"%TingenDataRoot%\%AvatarSystemCode%\YYMM\%OptionUserId%\HHMMSS\"</i>.<br/>
///   - More information about trace logs can be found <see href="github.com/spectrum-health-systems/Tingen-Documentation/blob/main/Glossary.md#logging">here</see>.
///  </para>
/// </remarks>
///   <example>
///    If the TraceLogLevel is set to "<c>2</c>", the following log calls will be executed:<br/>
///    <c>LogEvent.Trace(1, tnSession.TraceLogs, Asm);</c><br/>
///    <c>LogEvent.Trace(2, tnSession.TraceLogs, Asm);</c><br/><br/>
///    If the TraceLogLevel is set to "<c>2</c>", the following log calls will <i>not</i> be executed:<br/>
///    <c>LogEvent.Trace(4, tnSession.TraceLogs, Asm);</c><br/>
///    <c>LogEvent.Trace(5, tnSession.TraceLogs, Asm);</c>
///   </example>
/// <value>
///  0 (default)
/// </value>
///
