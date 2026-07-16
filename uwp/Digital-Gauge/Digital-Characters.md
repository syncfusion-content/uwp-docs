---
layout: post
title: Digital Characters in UWP Digital Gauge control | Syncfusion
description: Learn here all about Digital Characters support in Syncfusion UWP Digital Gauge (SfDigitalGauge) control and more.
platform: uwp
control: SfDigitalGauge
documentation: ug
---

# Digital Characters in UWP Digital Gauge (SfDigitalGauge)

The digital characters in the digital gauge can be viewed in different types of segments. These digital characters are displayed in the digital gauge by setting the [Value](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Gauges.SfDigitalGauge.html#Syncfusion_UI_Xaml_Gauges_SfDigitalGauge_Value) property of type string. For initial setup of the control, see [Getting Started](./Getting-Started.md).

By default, the [CharacterType](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Gauges.SfDigitalGauge.html#Syncfusion_UI_Xaml_Gauges_SfDigitalGauge_CharacterType) property is set to `SegmentSeven`. The following sample uses the default segment type to render the value "GAUGE".

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

![UWP Digital Gauge Digital Characters](Digital-Characters_images/Digital-Characters_img1.jpeg)

The segment type can be changed using the [CharacterType](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Gauges.SfDigitalGauge.html#Syncfusion_UI_Xaml_Gauges_SfDigitalGauge_CharacterType) property. The `CharacterType` enum (defined in the `Syncfusion.UI.Xaml.Gauges` namespace) supports the following values: `SegmentSeven`, `SegmentFourteen`, `SegmentSixteen`, and `EightCrossEightDotMatrix`. Unsupported characters are rendered as blank segments. The [Value](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Gauges.SfDigitalGauge.html#Syncfusion_UI_Xaml_Gauges_SfDigitalGauge_Value) property accepts alphanumeric and special characters and is case-sensitive.


## 7-Segments

When [CharacterType](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Gauges.SfDigitalGauge.html#Syncfusion_UI_Xaml_Gauges_SfDigitalGauge_CharacterType) is set to `SegmentSeven` (the default), the value is displayed in 7-segment format. This type is mainly used to display numbers (0–9), though a limited set of letters is also supported.

{% tabs %}
{% highlight xaml %}

<syncfusion:SfDigitalGauge Value="12345" CharacterType="SegmentSeven" />

{% endhighlight %}

{% highlight c# %}

SfDigitalGauge digital = new SfDigitalGauge();
digital.Value = "12345";
digital.CharacterType = CharacterType.SegmentSeven;
this.Grid.Children.Add(digital);

{% endhighlight %}
{% endtabs %}

![UWP Digital Gauge 7-Segments](Digital-Characters_images/Digital-Characters_img2.jpeg)

## 14-Segments

When [CharacterType](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Gauges.SfDigitalGauge.html#Syncfusion_UI_Xaml_Gauges_SfDigitalGauge_CharacterType) is set to `SegmentFourteen`, the value is displayed in 14-segment format. This type is used to display both letters and numbers.

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

![UWP Digital Gauge 14-Segments](Digital-Characters_images/Digital-Characters_img3.jpeg)

## 16-Segments

When [CharacterType](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Gauges.SfDigitalGauge.html#Syncfusion_UI_Xaml_Gauges_SfDigitalGauge_CharacterType) is set to `SegmentSixteen`, the value is displayed in 16-segment format. This type is also used to display both letters and numbers. Compared to 14-segment, the 16-segment type splits the horizontal bars, producing a cleaner, more evenly lit character suitable when a split-style appearance is preferred.

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

![UWP Digital Gauge 16-Segments](Digital-Characters_images/Digital-Characters_img4.jpeg)

## 8*8 Dot Matrix Segments

When [CharacterType](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Gauges.SfDigitalGauge.html#Syncfusion_UI_Xaml_Gauges_SfDigitalGauge_CharacterType) is set to `EightCrossEightDotMatrix`, the value is displayed in an 8 × 8 dot matrix. This type is used to display special characters along with letters and numbers.

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
{% endtabs %}

![UWP Digital Gauge 8 x 8 Dot Matrix Segments](Digital-Characters_images/Digital-Characters_img5.jpeg)

