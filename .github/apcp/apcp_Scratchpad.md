            //#DEVNOTE# Testing/debugging purposes.
            //File.WriteAllText(@"C:\Tingen_Data\test.txt", sentOptionObject.OptionId.ToString());
            //Outpost31.Core.Logger.LogEvent.Primeval(@"C:\Tingen_Data", ExeAsm, sentOptionObject.OptionId.ToString());


            ////// START PROTO

            ////OptionObject2015 workObj = sentOptionObject.Clone();

            ////if (workObj.SystemCode == "UAT" && workObj.OptionId == "USER_Report118")
            ////{
            ////    return sentOptionObject.ToReturnOptionObject(1, "NO!");


            ////}
            ////else
            ////{
            ////    return sentOptionObject.ToReturnOptionObject(3, "OK!");
            ////}

            ////// END PROTO




A. foo
B. foo.src
C. src
D. .src
E. C:\Users\OddThinking\Documents\My Source\ (absolute path of the root)
F. Widget\foo.src (relative path of the file to absolute path of the root)
G. Widget\
H. C:\Users\OddThinking\Documents\My Source\Widget\
I. C:\Users\OddThinking\Documents\My Source\Widget\foo.src

C:\                             - Root path

C:\Folder1\Folder2\file.txt     - Full path / Absolute path

Folder2\file.txt                - Relative path

Folder1\                        - Folder

file.txt                        - file name

file                            - stem

.txt                            - file extension

A. file root

B. File name

C. File extension

D. File extension

E. base directory

F. relative path

G. Directory/folder

H. Directory name

I. full path/absolute path
'

file name, folder name, volume name

filename, pathname, volume name



## Abrv

avtr = Avatar
avtrEnvironment = Avatar Environment (LIVE, UAT, etc.)
tngnwsvc = Tingen Web Service


<seealso href="https://github.com/spectrum-health-systems/tingen-documentation-project">Tingen Documentation Project</seealso>

<seealso href="https://github.com/spectrum-health-systems/tingen-documentation-project/blob/main/static/avatar/environment.md">Avatar Environents</seealso>

<see href="https://github.com/spectrum-health-systems/tingen-documentation-project/blob/main/static/avatar/environment.md#system-code">Avatar System Code</see>



```csharp
        /// <summary>Creates a new instance of the RuntimeSettings class.</summary>
        /// <returns>An object containing the runtime settings for the Tingen Web Service.</returns>
        /// <include file='AppData/XmlDoc/Core.Runtime.xml' path='Core.Runtime/Class[@name="TngnWbsvRuntimeSettings"]/New/*'/>
        public static WsvcRuntime New(string tngnWbsvVersion, string tngnWbsvEnvironment)
        {
            /* #DEVNOTE#
             * Please read the XML Documentation for this method for important information.
             */

            LogEvent.Debuggler(tngnWbsvEnvironment, $"[CREATE DATA PATH]");

            string tngnWbsvDataPath    = $@"C:\Tingen_Data\WebService\{tngnWbsvEnvironment}";

            LogEvent.Debuggler(tngnWbsvEnvironment, $"[GET MODE]");

            string tngnWbsvMode        = GetTngnWbsvMode($@"{tngnWbsvDataPath}\Runtime\TngnWbsv.Mode", ValidTngnWbsvModes());

            LogEvent.Debuggler(tngnWbsvEnvironment, $"[CREATING RUNTIME SETTINGS]");


            var thing = new WsvcRuntime()
            {
                TngnWsvcVer     = tngnWbsvVersion,
                TngnWsvcBuild       = "250512",
                TngnWsvcAvtrSys = tngnWbsvEnvironment,
                TngnWsvcMode        = tngnWbsvMode,
                TngnWsvcDataPath    = tngnWbsvDataPath,
                TngnWsvcHostName    = Environment.MachineName,
                CurrentDate         = DateTime.Now.ToString("YYMMDD"),
                CurrentTime         = DateTime.Now.ToString("HHMMSS"),
            };

            LogEvent.Debuggler(tngnWbsvEnvironment, $"[RUNTIME SETTINGS CREATED]");

            return thing;

            //return new TngnWbsvRuntimeSettings()
            //{
            //    TngnWbsvVersion     = tngnWbsvVersion,
            //    TngnWbsvBuild       = "250512",
            //    TngnWbsvEnvironment = tngnWbsvEnvironment,
            //    TngnWbsvMode        = tngnWbsvMode,
            //    TngnWbsvDataPath    = tngnWbsvDataPath,
            //    TngnWbsvHostName    = Environment.MachineName,
            //    CurrentDate         = DateTime.Now.ToString("YYMMDD"),
            //    CurrentTime         = DateTime.Now.ToString("HHMMSS"),
            //};
        }

        /// <summary>Get the contents of a file, and validate it.</summary>
        /// <param name="filePath">The file path.</param>
        /// <param name="validateAgainst">A list of values to validate against.</param>
        /// <returns>The valid contents of the file (or we exit the application).</returns>
        /// <include file='AppData/XmlDoc/Core.Runtime.xml' path='Core.Runtime/Class[@name="TngnWbsvRuntimeSettings"]/TngnWbsvRuntimeSettings.New/*'/>
        private static string GetTngnWbsvMode(string filePath, List<string> validateAgainst)
        {
            /* Trace Logs won't work here. */

            string tngnWbsvMode = DuFile.ReadAndVerifyLocal(filePath, validateAgainst);

            if (tngnWbsvMode.Contains("The contents of are not valid.")) // test
            {
                // Log this.
                Service.Spin.DownImmediately();
            }

            //#DEVNOTE# Test to make sure this works if the contents are not valid.
            return tngnWbsvMode;
        }

        /// <summary>Valid Tingen Web Service modes.</summary>
        /// <returns>A list of valid Tingen Web Service modes.</returns>
        private static List<string> ValidTngnWbsvModes()
        {
            return new List<string>()
            {
                "enabled",
                "disabled",
                "passthrough"
            };
        }
```



  %% Styles
  classDef R0_ stroke:#f9ebea,stroke-width:3px,fill:#f9ebea,color:#641e16
  classDef R1_ stroke:#f9ebea,stroke-width:3px,fill:#E6B0AA,color:#641e16
  classDef R2_ stroke:#f9ebea,stroke-width:3px,fill:#CD6155,color:#f9ebea
  classDef R3_ stroke:#f9ebea,stroke-width:3px,fill:#A93226,color:#f9ebea
  classDef R4_ stroke:#f9ebea,stroke-width:3px,fill:#641e16,color:#f9ebea
  classDef R5_ stroke:#641e16,stroke-width:3px,fill:#f9ebea,color:#641e16
  classDef R6_ stroke:#641e16,stroke-width:3px,fill:#E6B0AA,color:#641e16
  classDef R7_ stroke:#641e16,stroke-width:3px,fill:#CD6155,color:#f9ebea
  classDef R8_ stroke:#641e16,stroke-width:3px,fill:#A93226,color:#f9ebea
  classDef R9_ stroke:#641e16,stroke-width:3px,fill:#641e16,color:#f9ebea
  classDef P0_ stroke:#f5eef8,stroke-width:3px,fill:#f5eef8,color:#512e5f
  classDef P1_ stroke:#f5eef8,stroke-width:3px,fill:#d7bde2,color:#512e5f
  classDef P2_ stroke:#f5eef8,stroke-width:3px,fill:#af7ac5,color:#f5eef8
  classDef P3_ stroke:#f5eef8,stroke-width:3px,fill:#884ea0,color:#f5eef8
  classDef P4_ stroke:#f5eef8,stroke-width:3px,fill:#512e5f,color:#f5eef8
  classDef P5_ stroke:#512e5f,stroke-width:3px,fill:#f5eef8,color:#512e5f
  classDef P6_ stroke:#512e5f,stroke-width:3px,fill:#d7bde2,color:#512e5f
  classDef P7_ stroke:#512e5f,stroke-width:3px,fill:#af7ac5,color:#f5eef8
  classDef P8_ stroke:#512e5f,stroke-width:3px,fill:#884ea0,color:#f5eef8
  classDef P9_ stroke:#512e5f,stroke-width:3px,fill:#512e5f,color:#f5eef8
  classDef U0_ stroke:#eaf2f8,stroke-width:3px,fill:#eaf2f8,color:#154360
  classDef U1_ stroke:#eaf2f8,stroke-width:3px,fill:#a9cce3,color:#154360
  classDef U2_ stroke:#eaf2f8,stroke-width:3px,fill:#5499c7,color:#eaf2f8
  classDef U3_ stroke:#eaf2f8,stroke-width:3px,fill:#2471a3,color:#eaf2f8
  classDef U4_ stroke:#eaf2f8,stroke-width:3px,fill:#154360,color:#eaf2f8
  classDef U5_ stroke:#154360,stroke-width:3px,fill:#eaf2f8,color:#154360
  classDef U6_ stroke:#154360,stroke-width:3px,fill:#a9cce3,color:#154360
  classDef U7_ stroke:#154360,stroke-width:3px,fill:#5499c7,color:#eaf2f8
  classDef U8_ stroke:#154360,stroke-width:3px,fill:#2471a3,color:#eaf2f8
  classDef U9_ stroke:#154360,stroke-width:3px,fill:#154360,color:#eaf2f8
  classDef G0_ stroke:#e9f7ef,stroke-width:3px,fill:#eaf2f8,color:#154360
  classDef G1_ stroke:#e9f7ef,stroke-width:3px,fill:#a9dfbf,color:#145a32
  classDef G2_ stroke:#e9f7ef,stroke-width:3px,fill:#52be80,color:#e9f7ef
  classDef G3_ stroke:#e9f7ef,stroke-width:3px,fill:#1d8348,color:#e9f7ef
  classDef G4_ stroke:#e9f7ef,stroke-width:3px,fill:#145a32,color:#e9f7ef
  classDef G5_ stroke:#145a32,stroke-width:3px,fill:#eaf2f8,color:#154360
  classDef G6_ stroke:#145a32,stroke-width:3px,fill:#a9dfbf,color:#145a32
  classDef G7_ stroke:#145a32,stroke-width:3px,fill:#52be80,color:#e9f7ef
  classDef G8_ stroke:#145a32,stroke-width:3px,fill:#1d8348,color:#e9f7ef
  classDef G9_ stroke:#145a32,stroke-width:3px,fill:#145a32,color:#e9f7ef
  classDef Y0_ stroke:#fef9e7,stroke-width:3px,fill:#fef9e7,color:#7d6608
  classDef Y1_ stroke:#fef9e7,stroke-width:3px,fill:#f9e79f,color:#7d6608
  classDef Y2_ stroke:#fef9e7,stroke-width:3px,fill:#f4d03f,color:#7d6608
  classDef Y3_ stroke:#fef9e7,stroke-width:3px,fill:#d4ac0d,color:#fef9e7
  classDef Y4_ stroke:#fef9e7,stroke-width:3px,fill:#7d6608,color:#fef9e7
  classDef Y5_ stroke:#7d6608,stroke-width:3px,fill:#fef9e7,color:#7d6608
  classDef Y6_ stroke:#7d6608,stroke-width:3px,fill:#f9e79f,color:#7d6608
  classDef Y7_ stroke:#7d6608,stroke-width:3px,fill:#f4d03f,color:#7d6608
  classDef Y8_ stroke:#7d6608,stroke-width:3px,fill:#d4ac0d,color:#fef9e7
  classDef Y9_ stroke:#7d6608,stroke-width:3px,fill:#7d6608,color:#fef9e7
  classDef E0_ stroke:#fdf2e9,stroke-width:3px,fill:#fdf2e9,color:#784212
  classDef E1_ stroke:#fdf2e9,stroke-width:3px,fill:#f8c471,color:#784212  
  classDef E2_ stroke:#fdf2e9,stroke-width:3px,fill:#f5b041,color:#fdf2e9
  classDef E3_ stroke:#fdf2e9,stroke-width:3px,fill:#ca6f1e,color:#fdf2e9
  classDef E4_ stroke:#fdf2e9,stroke-width:3px,fill:#784212,color:#fdf2e9
  classDef E5_ stroke:#784212,stroke-width:3px,fill:#fdf2e9,color:#784212
  classDef E6_ stroke:#784212,stroke-width:3px,fill:#f8c471,color:#784212  
  classDef E7_ stroke:#784212,stroke-width:3px,fill:#f5b041,color:#fdf2e9
  classDef E8_ stroke:#784212,stroke-width:3px,fill:#ca6f1e,color:#fdf2e9
  classDef E9_ stroke:#784212,stroke-width:3px,fill:#784212,color:#fdf2e9
  classDef W0_ stroke:#FFFFFF,stroke-width:3px,fill:#FFFFFF,color:#000000
  classDef W1_ stroke:#641e16,stroke-width:3px,fill:#FFFFFF,color:#641e16
  classDef W2_ stroke:#af7ac5,stroke-width:3px,fill:#FFFFFF,color:#af7ac5
  classDef W3_ stroke:#5499c7,stroke-width:3px,fill:#FFFFFF,color:#5499c7
  classDef W4_ stroke:#52be80,stroke-width:3px,fill:#FFFFFF,color:#52be80
  classDef W5_ stroke:#d4ac0d,stroke-width:3px,fill:#FFFFFF,color:#d4ac0d
  classDef W6_ stroke:#ca6f1e,stroke-width:3px,fill:#FFFFFF,color:#ca6f1e 
  classDef W7_ stroke:#7b7d7d,stroke-width:3px,fill:#FFFFFF,color:#7b7d7d
  classDef W8_ stroke:#424949,stroke-width:3px,fill:#FFFFFF,color:#424949
  classDef W9_ stroke:#000000,stroke-width:3px,fill:#FFFFFF,color:#000000
  classDef B0_ stroke:#FFFFFF,stroke-width:3px,fill:#000000,color:#FFFFFF
  classDef B1_ stroke:#CD6155,stroke-width:3px,fill:#000000,color:#CD6155
  classDef B2_ stroke:#af7ac5,stroke-width:3px,fill:#000000,color:#af7ac5
  classDef B3_ stroke:#5499c7,stroke-width:3px,fill:#000000,color:#5499c7
  classDef B4_ stroke:#52be80,stroke-width:3px,fill:#000000,color:#52be80
  classDef B5_ stroke:#d4ac0d,stroke-width:3px,fill:#000000,color:#d4ac0d
  classDef B6_ stroke:#ca6f1e,stroke-width:3px,fill:#000000,color:#ca6f1e 
  classDef B7_ stroke:#7b7d7d,stroke-width:3px,fill:#000000,color:#7b7d7d
  classDef B8_ stroke:#626567,stroke-width:3px,fill:#000000,color:#626567 
  classDef B9_ stroke:#000000,stroke-width:3px,fill:#000000,color:#FFFFFF