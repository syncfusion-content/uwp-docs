---
layout: post
title: Getting Started with UWP Radial Slider control | Syncfusion
description: Learn here about getting started with Syncfusion UWP Radial Slider (SfRadialSlider) control, its elements and more.
platform: uwp
control: SfRadial Slider 
documentation: ug
---

# Getting Started with UWP Radial Slider (SfRadialSlider)

Namespace : Syncfusion.UI.Xaml.Controls.Navigation 

Assembly : Syncfusion.SfRadialMenu.UWP 

Dependent assembly: Syncfusion.SfShared.UWP



The following code sample shows how to create the SfRadialSlider from code-behind and XAML, 
{% tabs %}
 {% highlight xaml %}

<syncfusion:SfRadialSlider

            Minimum="0" 

            Maximum="100"  

            />

{% endhighlight %}

{% highlight c# %}

SfRadialSlider sfRadialSlider = new SfRadialSlider() {Minimum = 0, Maximum = 100};

{% endhighlight %}

{% highlight VB %}

Dim sfRadialSlider As New SfRadialSlider() With {
	.Minimum = 0,
	.Maximum = 100
}

{% endhighlight %}

{% endtabs %}

N> You can refer to our [UWP Radial Slider feature tour](https://www.syncfusion.com/uwp-ui-controls/radial-slider) page to know about its other groundbreaking feature representations. You can also explore our [UWP Radial Slider example](https://apps.microsoft.com/store/detail/syncfusion-essential-studio-for-uwp/9NBLGGH5WNGV) to understand how to present and manipulate data.