# Setting the AvtrSys

1. Go to the host location of the Tingen Web Service

2. Open the Web.config file in a text editor

3. Locate the <appSettings> section

4. Find the key named "AvtrSys"

5. Change the "value" to the desired Avatar system

## UAT example:

%HostName\Tingen_www\WebService\UAT\Web.config

```text
<applicationSettings>
    <TingenWebService.Properties.Settings>
        <setting name="AvtrSys" serializeAs="String">
            <value>UAT</value>
        </setting>
    </TingenWebService.Properties.Settings>
</applicationSettings>
```

## LIVE example:

%HostName\Tingen_www\WebService\LIVE\Web.config

```text
<applicationSettings>
    <TingenWebService.Properties.Settings>
        <setting name="AvtrSys" serializeAs="String">
            <value>LIVE</value>
        </setting>
    </TingenWebService.Properties.Settings>
</applicationSettings>
```
