## .NET MAUI and AppData Directory

<p>I'm playing around with .NET Maui w/Blazor and trying to setup logging using <a href="https://serilog.net/">Serilog</a>. Serilog will create directories and the log file for me.  I was sending the location of my AppData folder but nether the folder or file were visible via File Explorer.  Trying different things suchs as are they hidden? is there an access issue? etc... didn't give me any clue as to what was going on.  My exectuting code returned that both the directory and file were created successfully by my executing code and verified by following calls to Exists(). </p>

<p>I was expecting: </p>

<p>C:\Users\{USER}\AppData\Local\{APPNAME}\logs </p>

<p>At this time, I don't know why this works the way it does. I used the following code to create that path and verified via the Debugger that the path was 
what I expected:</p>

 ```C#
string pathSt = Environment.GetFolderPath(System.Environment.SpecialFolder.LocalApplicationData);
string appName = System.Reflection.Assembly.GetExecutingAssembly().GetName().Name;
string logFileName = System.IO.Path.Combine(pathStr, appName, "logs", "{APPNAME}-.log");
 ```
<p>After discovering this page <a href="https://learn.microsoft.com/en-us/dotnet/maui/platform-integration/storage/file-system-helpers?view=net-maui-7.0&tabs=windows">Microsoft article</a> 
I changed my code thus:</p>

 ```C#
string pathSt = FileSystem.Current.AppDataDirectory;
string appName = System.Reflection.Assembly.GetExecutingAssembly().GetName().Name;
string logFileName = System.IO.Path.Combine(pathStr, appName, "logs", "{APPNAME}-.log");
 ```

<p>While this still didn't get my folder and files written directly to AppData, stepping through with the Debugger did show me where my folder and file
were being housed.</p>

<p>C:\Users\{USER}\Local\Packages\35FED738-E840-4140-85DD-93F97F478798_9zz4h110yvjzm\LocalCache\Local\{APPNAME}\logs</p>
