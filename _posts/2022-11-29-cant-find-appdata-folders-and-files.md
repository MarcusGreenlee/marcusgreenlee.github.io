## .NET MAUI and AppData Directory

<p>I'm playing around with .NET Maui w/Blazor and adding a folder and file to AppData but nether the folder or file were visible in File Explorer.  They weren't 
visible, yet they were created successfully by my executing code and verified by following calles to Exists(). </p>

<p>I was expecting: </p>

<p>C:\Users\{USER}\AppData\Local\{APPNAME}\logs </p>

<p>At this time, I don't know why this works the way it does. I used the following code to create that path and verified via the Debugger that the path was 
what I expected.</p>

 ```C#
string pathSt = Environment.GetFolderPath(System.Environment.SpecialFolder.LocalApplicationData);
string appName = System.Reflection.Assembly.GetExecutingAssembly().GetName().Name;
string logFileName = System.IO.Path.Combine(pathStr, appName, "logs", "{APPNAME}-.log");
 ```
<p>After discovering this page https://learn.microsoft.com/en-us/dotnet/maui/platform-integration/storage/file-system-helpers?view=net-maui-7.0&tabs=windows 
I changed my code thus:</p>

 ```C#
string pathSt = FileSystem.Current.AppDataDirectory;
string appName = System.Reflection.Assembly.GetExecutingAssembly().GetName().Name;
string logFileName = System.IO.Path.Combine(pathStr, appName, "logs", "{APPNAME}-.log");
 ```

<p>While this still didn't get my folder and files written directly to AppData, stepping through with the Debugger did show me where my folder and file
were being housed.</p>

<p>C:\Users\{USER}\Local\Packages\35FED738-E840-4140-85DD-93F97F478798_9zz4h110yvjzm\LocalCache\Local\{APPNAME}\logs</p>
