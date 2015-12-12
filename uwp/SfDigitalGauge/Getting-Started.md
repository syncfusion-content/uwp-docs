---
layout: post
title: Getting Started | SfDigitalGauge | uwp | Syncfusion
description: Getting Started 
platform: uwp
control: SfDigitalGauge
documentation: ug
---

# Getting Started 

This section explains you the steps required to configure the **SfDigitalGauge** and also explains the steps to add basic elements of **SfDigitalGauge** through various API’s available within it.

## Configuring SfDigitalGauge

SfDigitalGauge is existing in the following assembly and namespace.

**Assembly**: Syncfusion.SfGauge.UWP

**Namespace**: Syncfusion.UI.Xaml.Gauges

{% tabs %}
{% highlight xaml %}

    <syncfusion:SfDigitalGauge />

{% endhighlight %}

{% highlight c# %}

    SfDigitalGauge digitalgauge = new SfDigitalGauge();
    this.Grid.Children.Add(digitalgauge);
     
{% endhighlight %}
{% endtabs %}

![](Getting-Started_images/Getting-Started_img1.jpeg)


Run the above code and now the default **SfDigitalGauge** can be displayed as follows. UI component of the digital gauge can be customized by adding segments and passing Values which will be explained in the next section.

## Displaying Values 

You can add alphanumeric characters to SfDigitalGauge using **Value** property in SfDigitalGauge.

{% tabs %}
{% highlight xaml %}

    <syncfusion:SfDigitalGauge Value="GAUGE" />    

{% endhighlight %}

{% highlight c# %}

    SfDigitalGauge digitalgauge = new SfDigitalGauge();
    digitalgauge.Value = "GAUGE";
    this.Grid.Children.Add(digitalgauge);

{% endhighlight %}
{% endtabs %}

SfDigitalGauge Values are displayed as follows.

![](Getting-Started_images/Getting-Started_img2.jpeg)

## Changing segments

You can view the digital characters in SfDigitalGauge using different types of Segments available in **CharacterType** property.

{% tabs %}
{% highlight xaml %}

    <syncfusion:SfDigitalGauge Value="12345"  CharacterType="SegmentSeven" />

{% endhighlight %}

{% highlight c# %}

    SfDigitalGauge digitalgauge = new SfDigitalGauge();
    digitalgauge.Value = "12345";
    digitalgauge.CharacterType = CharacterType.SegmentSeven;
    this.Grid.Children.Add(digitalgauge);

{% endhighlight %}
{% endtabs %}

SfDigitalGauge Segments are displayed as follows.

![](Getting-Started_images/Getting-Started_img3.jpeg)
