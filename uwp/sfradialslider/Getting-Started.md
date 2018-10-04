---
layout: post
title: Getting Started of SfRadialSlider control | UWP | Syncfusion
description: Getting started section provide details about how to use the SfRadialSlider control in the UWP application
platform: uwp
control: SfRadial Slider 
documentation: ug
---

# Getting Started 

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

