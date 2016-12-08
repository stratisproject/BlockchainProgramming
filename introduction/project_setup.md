## Project Setup {#project-setup}

Before we begin with the instruction, we should describe how we expect your projects to be set up.

1.  Create a new Project in Visual Studio (.NET 4.5 or higher)
2.  Right click on “References” in Solution Explorer and select “Manage NuGet Packages…”
3.  Search for “**NStratis”** and install it. (Or NStratis.Mono on MAC and Linux.)
![](../assets/nuget.png)  

> **Tip:** If you are on MAC or Linux and reference NStratis instead of NBitcoin.Mono you will be missing some classes.  

NStratis is the .NET Stratis library, it is open-source, maintained by Nicolas Dorier, the main author of this book. 
This library should always be included if you do anything Stratis related in C#.  
NStratis supports cross-platform applications.  

### ## # How to debug into NBitcoin source code (optional)  

NStratis lets you debug into its code, to make your life easier. For this feature to work make sure you have source server support enabled in Visual Studio (Tools/Options).   
![](../assets/visualstudio_enablesourceserversupport.png)  

Now, if you step into NStratis code, the source code will be automatically fetched on github, and appear in visual studio debugger.  
