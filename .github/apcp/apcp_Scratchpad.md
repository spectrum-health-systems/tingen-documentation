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