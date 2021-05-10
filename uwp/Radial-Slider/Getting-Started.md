---
layout: post
title: Getting Started with UWP Radial Slider control | Syncfusion
description: Learn here all about getting started with Syncfusion UWP Radial Slider (SfRadialSlider) control and more.
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

