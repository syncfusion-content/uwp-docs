---
layout: post
title: Localization in UWP Pivot Chart control | Syncfusion
description: Learn here all about Localization support in Syncfusion UWP Pivot Chart (SfPivotChart) control and more.
platform: UWP
control: SfPivotChart
documentation: ug
---

# Localization in UWP Pivot Chart (SfPivotChart)

Localization is the key feature to provide software solutions targeted at global users. The SfPivotChart allows users to localize the control to a specific locale and supports “resx” based localization.

You should perform the following steps to localize the control:

* Translation.
* Resource file and file name conventions.
* Culture specification.

## Translation

The first step in localization is translating the strings that can be localized to the destination locale.

N> Localization key field should be same for all locales. Do not translate the key fields.

## Resource file and file name conventions

After translating the strings, perform the following steps in the application:

1. Right-click the project file to create a new folder in the project by selecting Add > New Folder and rename the folder as “Resources”.

2. Then, right-click the **Resources** folder to create a new resource file by selecting Add > New Item.

![newResxFile_step1](Localization_images/newResxFile_step1.png)

![newResxFile_step2](Localization_images/newResxFile_step2.png)

N> The resource file name should be in the format “&lt;Culture Code&gt;.resx”.

3. Copy and paste the translated locale to the resource file which is created in the previous step.

## Culture specification

You should specify the CurrentUICulture in Application_Startup method of the App.xaml.cs file or constructor of the MainPage.xaml.cs file.

N> If you are specifying the current culture in the constructor of MainPage, then ensure that the culture is specified before calling the InitializeComponent() method.

{% tabs %}

{% highlight c# %}

public sealed partial class MainPage : Page
{
    public MainPage()
    {
        ApplicationLanguages.PrimaryLanguageOverride = "ar-AE";
        this.InitializeComponent();
    }
}

{% endhighlight %}

{% highlight vb %}

Public NotInheritable Partial Class MainPage
	Inherits Page
	Public Sub New()
		ApplicationLanguages.PrimaryLanguageOverride = "ar-AE"
		Me.InitializeComponent()
	End Sub
End Class

{% endhighlight %}

{% endtabs %}

## RTL

The SfPivotChart provides RTL support to display the content from right to left direction by setting the `FlowDirection` property to **RightToLeft**.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfPivotChart x:Name="PivotChart1" FlowDirection="RightToLeft"
                         ItemSource="{Binding ProductSalesData}" PivotAxis="{Binding PivotAxis}"
                         PivotLegend="{Binding PivotLegend}" PivotCalculations="{Binding PivotCalculations}"/>

{% endhighlight %}

{% highlight C# %}

PivotChart1.FlowDirection = FlowDirection.RightToLeft;

{% endhighlight %}

{% highlight vb %}

PivotChart1.FlowDirection = FlowDirection.RightToLeft

{% endhighlight %}

{% endtabs %}

![relationalRTL](Localization_images/relationalRTL.png)

A demo sample is available in the following location.

{system drive}:\Users\&lt;User Name&gt;\AppData\Local\Syncfusion\EssentialStudio\&lt;Version Number&gt;\Samples\UWP\SampleBrowser\PivotChart\PivotChart\View\Localization.xaml
