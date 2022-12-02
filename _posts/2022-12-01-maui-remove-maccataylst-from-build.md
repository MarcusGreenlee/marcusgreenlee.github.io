<p>At this time maccatalyst can not be removed from the build process using the Visual Studio IDE.  <a href="https://github.com/dotnet/maui/issues/11584">Issue report</a></p>

<p>You can remove it from the build process by manually editing the .csproj file.</p>
<ol>
<li>In Visual Studio, double-click on your project name. This will open the project's .csproj file in your editor.  You should see text.</li>
<li>Search for "&ltTargetFrameworks&gtnet6.0-maccatalyst&lt/TargetFrameworks&gt, then comment the line out or delete it</li>
</ol>
