---
layout: post
title: Steps to add Syncfusion Essential UWP controls
description: Learn here all about the different ways to add Syncfusion Essential UWP controls to the Visual Studio projects.
platform: uwp
control: Add Syncfusion Controls
documentation: ug
---

# Add Syncfusion UWP Controls

The Syncfusion UWP controls can be added in a Visual Studio projects by using either of the following ways,

* Through Designer
* Through Code-Behind
* Through Project Templates
* Through NuGet Packages

## Through Designer


Syncfusion UI for UWP are added automatically to the Visual Studio Toolbox during installation. The following steps helps to add required Essential UWP control through drag and drop from Toolbox. For example: SfTextBoxExt 

1. Create a Universal Windows Platform project in Visual Studio.

2. Find `SfTextBoxExt` by typing the text “SfTextBoxExt” in search box.

![Search SfTextBoxExt in UWP](add-syncfusion-controls_images/search-textbox-in-uwp-controls-list.jpeg)


3.Drag `SfTextBoxExt` and drop it in the designer.

![Drag SfTextBoxExt in to Designer in UWP](add-syncfusion-controls_images/add-uwp-textbox-control-through-designer.jpeg)


## Through XAML

The following steps helps to add a required Essential UWP control through XAML Code, for example: SfTextBoxExt.

1.Create a Universal Windows Platform project in Visual Studio and refer the following assemblies.

 * Syncfusion.SfInput.UWP.dll
 * Syncfusion.SfShared.UWP.dll

2.Include XML namespace for the above assemblies in MainPage.xaml.

{% tabs %}
	
{% highlight XAML  %}

<Page xmlns="(http://schemas.microsoft.com/winfx/2006/xaml/presentation"

xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"

xmlns:input="using:Syncfusion.UI.Xaml.Controls.Input">


{% endhighlight %}

{% endtabs %}

3.Now, Add the `SfTextBoxExt` control with a required optimal name, using the included namespace.

{% tabs %}

{% highlight XAML %}

<input:SfTextBoxExt x:Name="sftextboxExt">



{% endhighlight %}

{% endtabs %}


## Through Code-Behind

Syncfusion UI for UWP can added at runtime using C# / VB. The following steps helps to add required Essential UWP control through code. For example: SfTextBoxExt.

1.Create a Universal Windows Platform project in Visual Studio and refer to the following assemblies.

 * Syncfusion.SfInput.UWP.dll
 * Syncfusion.SfShared.UWP.dll

2.Create an instance of `SfTextBoxExt` using its namespace and set the required properties.

{% tabs %}

{% highlight C# %}


Syncfusion.UI.Xaml.Controls.Input.SfTextBoxExt textBoxExt1 = new Syncfusion.UI.Xaml.Controls.Input.SfTextBoxExt();

textBoxExt1.Height = 20;

textBoxExt1.Width = 120;

textBoxExt1.Margin = new Thickness(10, 10, 10, 10);

textBoxExt1.VerticalAlignment = VerticalAlignment.Center;

textBoxExt1.HorizontalAlignment = HorizontalAlignment.Center;

{% endhighlight %}

{% highlight VB %}
 
Dim textBoxExt1 As New Syncfusion.UI.Xaml.Controls.Input.SfTextBoxExt()

textBoxExt1.Height = 20

textBoxExt1.Width = 120

textBoxExt1.Margin = New Thickness(10, 10, 10, 10)

textBoxExt1.VerticalAlignment = VerticalAlignment.Center

textBoxExt1.HorizontalAlignment = HorizontalAlignment.Center


{% endhighlight %}

{% endtabs %}

3.Add the created instance to MainPage.

{% tabs%}

{% highlight C# %}


this.Content = textBoxExt1;


{% endhighlight %}


{% highlight VB %}

Me.Content = textBoxExt1


{% endhighlight %}

{% endtabs %}

N> Syncfusion controls for UWP package can be added (available under Universal Windows Platform => Extensions tab in Add reference dialog) in the cases of using most of the controls from Syncfusion toolkit.

## Through Project Templates

Syncfusion provides the **Visual** **Studio** **Project** **Templates** for the Syncfusion UWP platform to create Syncfusion UWP Applications.  

I> The Syncfusion UWP project templates are available from Essential Studio v15.3.0.26.  

### Create Syncfusion UWP Application

The following steps direct you to create the **Syncfusion** **UWP** **Application** through the **Visual** **Studio** **Project** **Template**.

1. To create a Syncfusion UWP project, choose **New** **Project****->** **Syncfusion****->****Universal** **Windows****->****Syncfusion** **Universal** **Windows** **Application** from **Visual** **Studio**.

   ![Create Syncfusion UWP project](add-syncfusion-controls_images/project-templates-in-uwp-controls.jpeg)

2. Name the **Project** and choose the destination location if required, then click **OK**. 

3. Then Project Configuration Wizard appears. Choose the options to configure the Syncfusion UWP Application by using the following Project Configuration dialog.

   #### Project configurations:

   **Language:** Select the language, either Visual C# or Visual Basic.

   **Reference Type:** Select the reference type of UWP Project, either Assemblies or SDK.

   **Target Version:** Choose the Target Version of the UWP platform that your project is targeting. This sets the **TargetPlatformVersion** setting in your project file.

   **Minimum Version:** Choose the Minimum Version of the UWP platform that your project can work with. This sets the **TargetPlatformMinVersion** setting in your project file.

   **Template Type:** Select the template type of UWP Project, either Blank or Hamburger Menu or Hamburger Menu (MVVM).

   **Components:** Choose the required Syncfusion components to configure.
   
   ![Configure Syncfusion UWP project](add-syncfusion-controls_images/configure-project-in-uwp-controls.jpeg)
   
   N> If SDK is chosen as the reference type, then all the Syncfusion UWP controls will be added. So, you no need to select any components.
   
4. Once you click Create button, the Syncfusion UWP Application is created.

5. Once the Project Configuration Wizard is done, the Syncfusion UWP Application is created with required SDK/references and pages.

   ![UWP Application Created with required SDK and References](add-syncfusion-controls_images/create-application-in-uwp-controls.jpeg)

6. Then, Syncfusion licensing registration required message box will be shown as follow, if you are installed the trial setup or NuGet packages since Syncfusion introduced the licensing system from 2018 Volume 2 (v16.2.0.41) Essential Studio release. Please navigate to the [help topic](https://help.syncfusion.com/common/essential-studio/licensing/overview#how-to-generate-syncfusion-license-key) which is shown in the licensing message box to generate and register the Syncfusion license key to your project. Refer to this [blog](https://www.syncfusion.com/blogs/post/whats-new-in-2018-volume-2.aspx) post for understanding the licensing changes introduced in Essential Studio.

   ![Syncfusion Licensing Message Box](add-syncfusion-controls_images/create-licensing-in-uwp-controls.jpeg)

## Through NuGet Packages

Syncfusion UI for UWP are added automatically to the specific Visual Studio UWP application Toolbox during Syncfusion NuGet package installation. Please refer below topic to configure and install the Syncfusion UWP NuGet packages in UWP application from Visual Studio.

[Configuring Syncfusion NuGet packages in Visual Studio](https://help.syncfusion.com/uwp/visual-studio-integration/nuget-packages)

After Installed required Syncfusion UWP NuGet packages in your application, we can utilize the Syncfusion UWP controls by following ways. 

* Through Designer
* Through XMAL
* Through Code-Behind

1.Syncfusion UI for UWP are added automatically to the specific Visual Studio UWP application Toolbox during Syncfusion NuGet package installation. We can add required Syncfusion UWP control through drag and drop from ToolBox. Toolbox configured from Syncfusion UWP NuGet package, controls will be listed under “Syncfusion controls for UWP” category. For example: SfColorPicker

   ![Add Colorpicker from ToolBox in UWP](add-ayncfusion-controls_images/add-colorpicker-in-uwp-controls.png)
    
   ![UWP Colorpicker Control](add-syncfusion-controls_images/colorpicker-control-in-uwp.png)

   N> Toolbox configuration by installing UWP NuGet packages support available from v15.4.0.17.


2.The following steps helps to add a required Essential UWP control through XAML code, for example: SfColorPicker

a. Include the namespace for Syncfusion.SfColorPickers.UWP assembly from Syncfusion.SfColorPickers.UWP NuGet package in MainPage.xaml.

        {% tabs %}

        {% highlight XAML %}

        <Page xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"

        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"

        xmlns:media="using:Syncfusion.UI.Xaml.Controls.Media">

        {% endhighlight %}

        {% endtabs %}

b. Now add the `SfColorPicker` control with a required optimal name using the included namespace

        {% tabs %}

        {% highlight XAML %}

        <media:SfColorPicker x:Name="colorPicker">

        {% endhighlight %}

        {% endtabs %}


3.The following steps helps to add a required Essential UWP control through code, for example: SfColorPicker
        
a. Include the namespace for Syncfusion. SfColorPickers.UWP assembly in MainPage.xaml.cs

        {% tabs %}

        {% highlight C# %}

        using Syncfusion.UI.Xaml.Controls.Media;

        {% endhighlight %}

        {% highlight VB %}

        Imports Syncfusion.UI.Xaml.Controls.Media

        {% endhighlight %}

        {% endtabs %}

b. Now add the SfColorPicker control with a required optimal name 

        {% tabs %}

        {% highlight C# %}

        SfColorPicker colorPicker = new SfColorPicker();

        {% endhighlight %}

        {% highlight VB %}

        Dim colorPicker As New SfColorPicker()

        {% endhighlight %}

        {% endtabs %}






