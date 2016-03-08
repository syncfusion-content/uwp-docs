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

The steps to install the Syncfusion UWP NuGet Packages in Visual Studio are as follows,

1. Navigate the below location in browser. 

   [http://nuget.syncfusion.com/package/universalwindows](http://nuget.syncfusion.com/package/universalwindows)

   ![](Installation-and-Deployment_images\NuGetConfig_img1.jpeg)

2. Select `Download Links and Details` for the required Syncfusion version.

   ![](Installation-and-Deployment_images\NuGetConfig_img2.jpeg)

3. Click the `DOWNLOAD` button to get the Syncfusion UWP NuGet Packages from the listed package(s).

4. Extract the zip file once downloaded.

5. In Visual Studio, navigate to `Tools | NuGet Package Manager | Package Manager Settings`, the options dialog will appear on the screen as shows below,

   ![](Installation-and-Deployment_images\NuGetConfig_img3.jpeg)

6. Select `NuGet Package Manager | Package Sources` and click `Add` button to add the `Package Name` and locate the extracted directory location as `Package Source` of Syncfusion NuGet Packages.    

   **Name**: Name of the package source that listed in available package sources.
   
   **Source**: Syncfusion UWP NuGet package source location.
   
   ![](Installation-and-Deployment_images\NuGetConfig_img4.jpeg)

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

1. Download the latest Syncfusion NuGet Package from [here](http://nuget.syncfusion.com/package/universalwindows) and configure the latest Syncfusion NuGet Packages in Visual Studio. Please Refer the [NuGet Configuration](#nuget-configuration) topic for more information.

2. Right click on Project and Navigate to the `Manage NuGet Packages` and click on the `Updates tab` to check for updates.

3. Select `Updates -> <Syncfusion Package Source>` in `Package Source` combo box. Refer to the following screenshot for more information.

   ![](Installation-and-Deployment_images\NuGetConfig_img6.jpeg)

4. If there is a new version of NuGet you will see it in the list of available updates in Updates tab.

5. Select NuGet Package in the list and click `Update`. When the update is complete, close and re-open all open instances of Visual Studio.

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

Copying assemblies to local folder is supported by Syncfusion components. It can be achieved by setting the assembly’s Copy Local property to true, so that it can be copied to Bin\Release, Bin\Debug folders. The files .exe, dll, xml, .pri, rd.xml, .xaml  are copied to client machines.

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
