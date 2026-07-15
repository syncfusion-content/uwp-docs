---
layout: post
title: Getting Started with UWP Barcode control | Syncfusion
description: Learn here about getting started with Syncfusion UWP Barcode (SfBarcode) control, its elements and more details.
platform: uwp
control: SfBarcode
documentation: ug
---

# Getting Started with UWP Barcode (SfBarcode)

## Add Barcode control to an Application 

The following assembly reference is required for deploying Barcode.

{% highlight c# %}

Namespace: Syncfusion.UI.Xaml.Controls.Barcode

Assembly: Syncfusion.SfBarcode.UWP

{% endhighlight  %}

To create the SfBarcode control in Visual Studio:

1. Create a new UWP project. 

2. Drag the SfBarcode control from the Toolbox window to the Design View. An instance of the SfBarcode control is created in the Design view.

   ![UWP Barcode Control](Getting-Started_images/uwp-barcode-control.png)

   SfBarcode Control after Dragging to Design View
   {:.caption}

The following code example shows how to create the Barcode control from XAML:

{% tabs %}

{% highlight xaml %}

<Page
    x:Class="GettingStarted.MainPage"
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
    xmlns:local="using:GettingStarted"
    xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
    xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
    mc:Ignorable="d"
    xmlns:sync="using:Syncfusion.UI.Xaml.Controls.Barcode">

    <Grid>
        <sync:SfBarcode x:Name="barcode" Text="http://www.syncfusion.com" Symbology="QRBarcode">
            <sync:SfBarcode.SymbologySettings>
                <sync:QRBarcodeSetting XDimension="8"/>
            </sync:SfBarcode.SymbologySettings>
        </sync:SfBarcode>
    </Grid>

</Page>

{% endhighlight %}

{% endtabs %}

## Text

The text to be encoded can be set using the Text property. By default, this original text will be displayed at the bottom of the bar code. The location of the text can be toggled between top and bottom using [`TextLocation`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Controls.Barcode.SfBarcode.html#Syncfusion_UI_Xaml_Controls_Barcode_SfBarcode_TextLocation) property. The horizontal alignment of the text can be set using [`TextAlignment`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Controls.Barcode.SfBarcode.html#Syncfusion_UI_Xaml_Controls_Barcode_SfBarcode_TextAlignment) The text brush and other various font customization can also be done using the built-in font properties. Optionally, the user can hide the barcode text by setting the [`DisplayText`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Controls.Barcode.SfBarcode.html#Syncfusion_UI_Xaml_Controls_Barcode_SfBarcode_DisplayText) property to false.

{% tabs %}

{% highlight xaml %}

<sync:SfBarcode x:Name="barcode" Text="http://www.syncfusion.com" DisplayText="False" Symbology="QRBarcode"/>

{% endhighlight %}

{% endtabs %}

## Rotation

Barcode control can be rotated to save space by using the Rotation property. The barcode can be rotated to 90, 180 and 270 degrees.