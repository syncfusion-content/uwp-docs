---
layout: post
title: Barcode Customization in UWP Barcode control | Syncfusion
description: Learn here all about Barcode Customization support in Syncfusion UWP Barcode (SfBarcode) control and more.
platform: uwp
control: SfBarcode
documentation: ug
---

# Barcode Customization in UWP Barcode (SfBarcode)

The color of the barcode can be customized by modifying the DarkBarBrush and LightBarBrush properties of the barcode control. 

{% tabs %}

{% highlight xaml %}

<sync:SfBarcode x:Name="barcode" Text="SYNCFUSION" LightBarBrush="Blue" DarkBarBrush="Red" Symbology="Code128A"/>

{% endhighlight  %}

{% endtabs %}

The DarkBarBrush represents the color of the dark bar (Black color usually) and the LightBarBrush represents the color of the gap between two adjacent black bars (White color usually).

![uwp-Barcode-Red-Color-Combination](Barcode-Customization_images/uwp-barcode-red-color-combination.png)

Barcode color combinations- Red
{:.caption}


![uwp-Barcode-Blue-Color-Combination](Barcode-Customization_images/uwp-barcode-blue-color-combination.png)

Barcode color combinations- Blue
{:.caption}

N> The DarkBarBrush and LightBarBrush customizations are applicable only for one dimensional barcodes. In order for a barcode symbol to be recognized by a scanner, there must be an adequate contrast between the dark bars and the light spaces and not all the barcode scanners have support for colored barcodes.
