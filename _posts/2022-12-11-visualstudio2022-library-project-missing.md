## Work Around: Visual Studio 2022 .NET Class Library Project Template Not Found

I was following these [instructions](https://learn.microsoft.com/en-us/dotnet/core/tutorials/library-with-visual-studio?pivots=dotnet-7-0) to create a .NET 7 Class Library project, but was unable to find the template in my instance of Visual Studio 2022.  I did spend sometime trying to figure out where the project template was but then realized that I was wasting time debugging something that, for my needs, wasn't a high priority.

Because I was just trying to add another .NET Class Library project to a solution that already had several of them in it, I was confident that I had everything I needed to build one.  My workaround was to reinstall [Visual Studio 2019](https://learn.microsoft.com/en-us/visualstudio/releases/2019/release-notes), create my Class Library project there, then port it into my Visual Studio 2022 project.

I will update when / if I discover why the Class Library project tempate isn't visible, but this workaround kept me going.
