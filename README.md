# Create-and-publish-a-nuget-package

Often times, we use NuGet packages in our projects and we are familiar with the procedure of adding a NuGet package to a project.

In this documentation, we'll discuss in detail how to create and publish NuGet Packages.

### What is NuGet?

Nuget is a mechanism through which developers can create, share, and consume useful code. Often such code is bundled into "packages" that contain compiled code (as DLLs) along with other content needed in the projects that consume these packages.

It is an essential tool for any modern development platform.

### What is a NuGet-package?

Very simple, it’s a container with components inside, designed for re-usability and sharing. It can contain class libraries or even an entire project including the `.cs` files. It’s then encapsulated into a redistributable package for anyone to use.

> Technically speaking, a NuGet package is just a ZIP file that’s been renamed with the .nupkg extension and whose contents match certain conventions. To easily examine any package’s contents, change the extension to .zip and expand its contents as usual. Just be sure to change the extension back to .nupkg before attempting to upload it to a host – Microsoft Docs

![The flow of packages between creators, hosts, and consumers](/images/nuget-roles-img.png)

<center>The flow of packages between creators, hosts, and consumers (Source – Microsoft Docs) </center>

## Getting Started 

Here, we describe how to create NuGet package and publish it using nuget.exe.

### Setting up project

* Launch Visual Studio
* Create a new solution
* Next, add a project of type “Class Library” and name it as “MyFirstNugetPackage”.
* Right click on project and select "Properties".

![The flow of packages between creators, hosts, and consumers](/images/properties.png)
<center>Properties</center>

Set the following basic values on the property values

* Check Generate NuGet package on build
* Package id - Unique identifier
* Package version
* Authors
* Company

### Creating a package

Checking "Generate NuGet package on build" property automatically creates package on build. This means the package will be created on every build. Consequently, the time to build increases the build time for your project.

**Note:** Package creation can also be done through the command using `dotnet pack` command and from the solution explorer by right-clicking the specific project and then click "Pack".

### Publish NuGet package

After successfully creating a NuGet package, the next step is to make it available to the developers. [nuget.org](http://nuget.org) helps you achieve this. You can make it publicly available to everyone or share it with a limited audience through a file share or other options like the private NuGet server.

A Microsoft account is needed to be able to publish your package on nuget.org.
You can freely create one [here](https://account.microsoft.com/).

![Upload new package](/images/upload.png)
<center>Upload new package</center>

### Consuming the package from NuGet Manager

In the NuGet package manager, simply search for the NuGet package name. Click install.