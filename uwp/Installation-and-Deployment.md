---
layout: post
title: Installation and Deployment process for Syncfusion Essential Studio UWP products
description: Learn how to install and deploy the Syncfusion UWP component
platform: uwp
control: Installation and Deployment
documentation: ug
---

# Installation and Deployment

## Manual Installation

The following procedure illustrates how to install Essential Studio.

* Double-click the Syncfusion Essential Studio UWP setup file. The Self-Extractor wizard opens and extracts the package automatically.
* Enter User Name, Organization and Unlock Key in the corresponding text boxes provided.
* Click Next
* After reading the terms and conditions, check the “I accept the terms and conditions” check box.
* Click Next. The Select the Installation and Samples Folder window opens.
* To install it in the displayed default location, click Install.
* Select the Run Dashboard check box to launch the Dashboard after installing.
* Click Finish. Essential Studio is installed in system and the Syncfusion Essential Studio [Dashboard](http://help.syncfusion.com/ug/common/documents/dashboard.htm#) is launched automatically.

## Configuring Syncfusion NuGet Packages in Visual Studio 

Syncfusion UWP NuGet packages are available [here](http://nuget.syncfusion.com/package/universalwindows)

### NuGet Configuration  

Syncfusion NuGet Package feed links are configured in Visual Studio in the following ways,

1. Syncfusion NuGet Package Manager
2. NuGet Package Manager settings

#### Syncfusion NuGet Package Manager

The following steps help you configure Syncfusion NuGet Packages with a URL.

1. **Syncfusion NuGet Manager** is allows you to **add** the Syncfusion NuGet sources (for available platforms) to NuGet Package Manager. Download the [Syncfusion NuGet Manager](http://www.syncfusion.com/downloads/support/directtrac/general/ze/SyncfusionNugetManager-1610952973.zip) utility.
2. Extract zip file and run the SyncfusionNuGetManager.exe
3. Syncfusion NuGet Manager Window will be opened.
4. Select the platform **UWP** from **“Select platforms to add”** (Left side of the window) column and click **Add>>** button. Then click **Configure** button.

   ![](Installation-and-Deployment_images\Syncfusion_NuGet_Manager_img1.jpg)

5. Once Syncfusion NuGet Manager added the Syncfusion NuGet sources, the changes will be reflected in package sources of your Visual Studio. 

   ![](Installation-and-Deployment_images\Syncfusion_NuGet_Manager_img2.jpg)

**Note:** Get the more details about Syncfusion NuGet Manager utility from [here](https://help.syncfusion.com/extension/syncfusion-nuget-packages/syncfusion-nuget-manager).

#### NuGet Package Manager settings

The steps to install the Syncfusion UWP NuGet Packages in Visual Studio are as follows,

1. In Visual Studio, navigate to `Tools | NuGet Package Manager | Package Manager Settings`, the options dialog will appear on the screen as shows below, 

   ![](Installation-and-Deployment_images\NuGetConfig_img3.jpeg)

2. Select `NuGet Package Manager | Package Sources` and click `Add` button to add the `Package Name` and `Package Source` of Syncfusion NuGet Packages.

   **Name**: Name of the package that listed in Available package sources  
   **Source**: Syncfusion UWP NuGet Package feed URL
   
   [http://nuget.syncfusion.com/nuget_universalwindows/nuget/getsyncfusionpackages/universalwindows](http://nuget.syncfusion.com/nuget_universalwindows/nuget/getsyncfusionpackages/universalwindows)
    
   ![](Installation-and-Deployment_images\NuGetConfig_img1.jpeg)
   
   N> The `Source` text box in the above image denotes the location of the NuGet packages and the `Name` section, allows you to provide a unique name for NuGet Packages Source.

I> Syncfusion other platforms NuGet packages feed links are available [here](http://nuget.syncfusion.com/)

### NuGet Installation

Syncfusion UWP NuGet can install once configured the package source. The NuGet installation steps as below,

1. Once configured the Package source with Syncfusion NuGet Packages, right click on project and choose `Manage NuGet Packages | Browse | <Package Source Name>` in `Package Sources` Combo box.

   ![](Installation-and-Deployment_images\NuGetConfig_img5.jpeg)

2. The NuGet Packages are listed which are available in package source location. Install the required packages to your application by clicking `Install` button.

   N> NuGet packages can be install directly through the command line (Package Manager Console). Further details click [here](http://help.syncfusion.com/extension/syncfusion-nuget-packages/nuget-install-and-configuration#install-from-package-manager-console)

### Updating a NuGet Package

Using `Manage NuGet packages` in Visual Studio, NuGet packages can be update.

1. Right click on Project and Navigate to the `Manage NuGet Packages` and click on the `Updates` tab to check for updates.

2. Select `Updates -> <Syncfusion Package Source>` in `Package Source` combo box. Refer to the following screenshot for more information.

   ![](Installation-and-Deployment_images\NuGetConfig_img6.jpeg)

3. If there is a new version of NuGet you will see it in the list of available updates in Updates tab.

4. Select NuGet Package in the list and click `Update`. When the update is complete, close and re-open all open instances of Visual Studio.

   N> By clicking `Update All` button, all NuGet packages are getting update. When the update is complete, close and re-open all open instances of Visual Studio.

## Command Line Installation

Follow the given steps to install through Command Line in Silent mode.

* Double-click the Syncfusion Essential Studio Setup file. The Self-Extractor wizard opens and extracts the package automatically.
* SyncfusionEssentialStudio_({{ site.releaseversion }}).exe file is extracted into the Temp folder.
* Open Run prompt and then execute the command %Temp% to open the Temp folder. SyncfusionEssentialStudio_({{ site.releaseversion }}).exe file is available in one of the folders.
* Copy the SyncfusionEssentialStudio_({{ site.releaseversion }}).exe file to local drive. Example: D:\temp
* Cancel the wizard.
* Open command prompt in administrator mode and pass the following arguments for corresponding version.


{% tabs %}

{% highlight Console %}  

“Setup file path\SyncfusionEssentialStudio_({{ site.releaseversion }}).exe” Install /PIDKEY:“(product unlock key)” [/log “{Log file path}”] [/InstallPath:{Location to install}]

{% endhighlight %} 

{% endtabs %}

N> In above section, Latest Essential Studio version details has been provided. User can refer installed Essential Studio version instead of mentioned version.

## Copy Local

Copying assemblies to local folder is supported by Syncfusion components. It can be achieved by setting the assembly’s Copy Local property to true, so that it can be copied to Bin\Release, Bin\Debug folders. The files .exe, .dll, .xml, .pri, rd.xml, .xaml  are copied to client machines.

![](Installation-and-Deployment_images/Installation-and-Deployment_img5.jpeg)


## Installed Location

The following table represents installed location of Assemblies and Samples.

<table>
<tr>
<td>
Assemblies/Samples</td><td>
Installed location</td></tr>
<tr>
<td>
SDK package</td><td>
C:\Program Files (x86)\Syncfusion\Essential Studio\{{ site.releaseversion }}\Universal Windows\10.0\SDK</td></tr>
<tr>
<td>
Assemblies</td><td>
C:\Program Files (x86)\Syncfusion\Essential Studio\{{ site.releaseversion }}\Assemblies for Universal Windows\10.0</td></tr>
<tr>
<td>
Samples</td><td>
[drive]:\Users\[username]\AppData\Local\Syncfusion\EssentialStudio\{{ site.releaseversion }}\UWP\SampleBrowser</td></tr>
</table>

N> In above table, Latest Essential Studio version details has been provided. User can refer installed Essential Studio version instead of mentioned version.
