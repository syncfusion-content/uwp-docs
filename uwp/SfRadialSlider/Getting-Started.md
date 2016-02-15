---
layout: post
title: Getting Started with SfRadialSlider control for UWP
description: A quick tour to initial users on SfRadialSlider control for UWP
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
{% endtabs %}

