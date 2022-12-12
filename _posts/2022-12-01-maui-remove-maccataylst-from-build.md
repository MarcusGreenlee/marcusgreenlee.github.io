## Work Around: Removing maccatalyst from MAUI Build Process

At this time maccatalyst can not be removed from the build process using the Visual Studio IDE. [Issue report](https://github.com/dotnet/maui/issues/11584/)

You can remove it from the build process by manually editing the **.csproj** file.

Steps:
1. In Visual Studio 2022, double-click on your project name. This will open the project's **.csproj** file in your editor.  You should see text.
2. Search for **\<TargetFrameworks\>net6.0-maccatalyst\</TargetFrameworks\>**, then comment the line out or delete it.

