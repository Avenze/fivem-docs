---
title: Scripting in C#
weight: 423
---

_This page is still a <b>work in progress</b> so this guide is not completed yet!_

# Setting up our environment
Before we can create our first C# resource, we need to install [Visual Studio 2017](https://visualstudio.microsoft.com/vs/) (the community/free version will work just fine).


## Creating your project
1. Open Visual Studio, and click `File > New > Project`. A window should pop up that looks something like the window below:
![screenshot-1](/csharp-tut-1.png)
<!--<img src="about:blank">--> <!-- TODO: replace this with a local image!!! -->
2. Make sure you select **Visual C#** in the panel on the left, then choose **Class Library (.NET Framework)**.
<br>It's very important that you select the correct project type otherwise your resource will **not** run.
3. After selecting the project type, make sure you set the Framework version to **.NET Framework 4.5.2** (somewhere at the bottom of the window, see the highlighted areas in the screenshot above). Yes, this is **not** the latest version, but this specific version is required for your resource to work correctly.
4. Once you've selected all these things and specified the correct framework version, it's time to enter a name for this project.
  - If this is going to be a client script, then name it something like `MyResourceNameClient`.
  - If it's going to be a server script, then name it something like `MyResourceNameServer`.
  - If it's going to be a script for both the server and the client side, then we'll consider this a Client script for now because we will create the Server project for this resource later.
<br><br>{{% alert theme="info" %}}You might want to change the "Solution name:" to something simpler. Instead of **MyResourceName[Server/Client]** you probably want to change it to just **MyResourceName**.<br>However, this is completely up to you.{{% /alert %}}
5. After choosing a proper name, then click "Browse..." to choose a folder where you want to save this project, or click "OK" if you want to save it at the default location.
### Additional project
**You can skip these steps if you only created a server or client side project, however continue reading if you need both a client and a server sided project.**
6. So, you've just created a client side project, but you also need a server side project. To add this to the solution, right-click on the "Solution '<solution name>' (1 project)" item in the Solution Explorer on the right side of your screen, and click "Add > New Project". All the settings should be the same as you used for the client project. This time, change the name to "MyResourceNameServer" and click "OK".
7. You should now have 2 projects inside your "Solution 'MyResourceName'" solution (again, you can view this in the Solution Explorer on the right).


## Configuring some project settings
To be able to build these projects and prepare them for FXServer, we'll need to change some settings in the project settings (change these settings in both projects if you're using a client & server project).

1. In the solution explorer on the right, right-click on your **project** (not the solution), and select "Properties".
2. Then go to the "Application" tab on the left, and in there add `.net` at the end of the "Assembly name". Now press CTRL + S to save this change. ![screenshot-2](/csharp-tut-2.png)
This is a very important step, if you do not add `.net` at the end of the Assembly name, then your resource will **NOT** run.

## Setting up the required dependencies
Once you've set that all up, it's time to get our dependencies for our resource.
<br>Depending on the type of resource you want to create, we'll either need the server CitizenFX.Core.dll dependency (for resources that need to run on the server side), or the client CitizenFX.Core.dll dependency (for resources that need to run on the client). If you want to be able to run your script both on the server, as well as on the client side then you'll need to get both of those dependencies, and we'll make 2 separate projects in our resource solution.

#### Client dependency
Getting the client dependency is very easy. Simply go to your local installation folder of FiveM, and follow the following path and copy the CitizenFX.Core.dll file. Then go to the folder where you saved your  Visual Studio project, and paste the dll file in that folder.
```ini
FiveM Application Data\citizen\clr2\lib\mono\4.5\CitizenFX.Core.dll
```
Now, go back into visual studio and go to your project in the Solution Explorer on the right. Right click on your (client) project, and click "Add > Reference".
The following window should appear: ![screenshot-3](/csharp-tut-3.png)
In that window, click on "Browse..." and go to your project folder. Find the CitizenFX.Core.dll file and select that (and press Add). You should now see that the dll has been added to the "Browse > Recent" list. Make sure that the checkmark in front of the reference **is checked**, and click "OK" in the bottom right.

Congratulations, you've now added the client dependency to the project. Only one more step before we can actually start coding. If you have a server sided project, then also checkout the next step. Otherwise skip the next step and go straight to the "Let's write some code" section.

<!--
FIXME: this isn't correct - the NuGet package is an (old) client version

#### Server dependency
The server project dependency is slightly different compared to the client dependency because we're not going to be taking the file and copying it inside our folder manually. We'll use **NuGet** for this. NuGet allows you to browse and install dependencies with just a few clicks, and it even notifies you whenever there's an update available.

To add this NuGet dependency, go to your server project in the Solution Explorer, and right click your project. Click "Manage NuGet packages..." and this window should appear: ![screenshot-4](/csharp-tut-4.png)
In the top left corner, click "Browse" and a search bar will appear below the "Browse" button. In there, type `CitizenFX` and press ENTER. Find the green iconic snail dependency in that list, and click the ⬇ icon on the right ![screenshot-5](/csharp-tut-5.png)

NuGet should take care of the rest for you. After the dependency has been added, you can close the NuGet window and return to your Class1.cs where we'll start coding in the next section of this guide.
-->

# Let's write some code
**It's finally time to actually start writing some code! 🎉**
```cpp
// Sorry, this guide is still a WIP. it will be finished soon!
```