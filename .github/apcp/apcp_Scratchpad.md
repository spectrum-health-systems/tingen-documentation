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