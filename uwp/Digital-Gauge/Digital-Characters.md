---
layout: post
title: Digital Characters in UWP Digital Gauge control | Syncfusion
description: Learn here all about Digital Characters support in Syncfusion UWP Digital Gauge (SfDigitalGauge) control and more.
platform: uwp
control: SfDigitalGauge
documentation: ug
---

# Digital Characters in UWP Digital Gauge (SfDigitalGauge)

The digital characters in the digital gauge can be viewed in different types of segments. These digital characters are set to the digital gauge through the **Value** property of type string.

{% tabs %}
{% highlight xaml %}

    <syncfusion:SfDigitalGauge Value="GAUGE" />    

{% endhighlight %}

{% highlight c# %}

    SfDigitalGauge digital = new SfDigitalGauge();
    digital.Value = "GAUGE";
    this.Grid.Children.Add(digital);

{% endhighlight %}
{% endtabs %}

![Digital-Characters_img1](Digital-Characters_images/Digital-Characters_img1.jpeg)


## 7-Segments

The digital characters which are set as the value property of the digital gauge are displayed by default 7-segments. Rather than using the alphabets, these are mainly used to display numbers. The type of segments can be set by the **CharacterType** property.

{% tabs %}
{% highlight xaml %}

    <syncfusion:SfDigitalGauge Value="12345"  CharacterType="SegmentSeven" />

{% endhighlight %}

{% highlight c# %}

    SfDigitalGauge digital = new SfDigitalGauge();
    digital.Value = "12345";
    digital.CharacterType = CharacterType.SegmentSeven;
    this.Grid.Children.Add(digital);

{% endhighlight %}
{% endtabs %}

![Digital-Characters_img2](Digital-Characters_images/Digital-Characters_img2.jpeg)

## 14-Segments

The digital characters which are set as the value property of the digital gauge are displayed by 14 segments. These type of characters are used to display both alphabets and numbers. 

{% tabs %}
{% highlight xaml %}

    <syncfusion:SfDigitalGauge Value="SYNCFUSION" CharacterType="SegmentFourteen" />

{% endhighlight %}

{% highlight c# %}

    SfDigitalGauge digital = new SfDigitalGauge();
    digital.Value = "SYNCFUSION";
    digital.CharacterType = CharacterType.SegmentFourteen;
    this.Grid.Children.Add(digital);

{% endhighlight %}
{% endtabs %}

![Digital-Characters_img3](Digital-Characters_images/Digital-Characters_img3.jpeg)

## 16-Segments

The digital characters which are set as the value property of the digital gauge are displayed by 16 segments. These type of characters are also used to display both alphabets and numbers. 

{% tabs %}
{% highlight xaml %}

    <syncfusion:SfDigitalGauge Value="SYNCFUSION" CharacterType="SegmentSixteen" />

{% endhighlight %}

{% highlight c# %}

    SfDigitalGauge digital = new SfDigitalGauge();
    digital.Value = "SYNCFUSION";
    digital.CharacterType = CharacterType.SegmentSixteen;
    this.Grid.Children.Add(digital);

{% endhighlight %}
{% endtabs %}

![Digital-Characters_img4](Digital-Characters_images/Digital-Characters_img4.jpeg)

## 8*8 Dot Matrix Segments

The digital characters which are set as the value property of the digital gauge are displayed by eight cross eight dot matrix segments. These type of characters are used to display special characters along with the alphabets and numbers. 

{% tabs %}
{% highlight xaml %}

    <syncfusion:SfDigitalGauge Value="SYNCFUSION" CharacterType="EightCrossEightDotMatrix" />

{% endhighlight %}

{% highlight c# %}

    SfDigitalGauge digital = new SfDigitalGauge();
    digital.Value = "SYNCFUSION";
    digital.CharacterType = CharacterType.EightCrossEightDotMatrix;
    this.Grid.Children.Add(digital);

{% endhighlight %}
{% endtabs%}

![Digital-Characters_img5](Digital-Characters_images/Digital-Characters_img5.jpeg)

