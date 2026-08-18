---
layout: post
title: Getting Started with UWP Radial Slider | Syncfusion®
description: Learn how to get started with the Syncfusion® UWP Radial Slider (SfRadialSlider) control. Explore setup, features, examples, and customization options.
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

N> You can refer to our [UWP Radial Slider](https://www.syncfusion.com/uwp-ui-controls/radial-slider) page to know about its other groundbreaking feature representations. You can also explore our [UWP Radial Slider example](https://apps.microsoft.com/detail/9nblggh5wngv?hl=en-US&gl=IN) that shows you how to render and configure the Radial Slider in UWP.