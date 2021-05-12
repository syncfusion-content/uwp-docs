---
layout: post
title: Ticks in UWP Radial Gauge control | Syncfusion
description: Learn here all about Ticks support in Syncfusion UWP Radial Gauge (SfCircularGauge) control and more.
platform: uwp
control: SfCircularGauge
documentation: ug
---

# Ticks in UWP Radial Gauge (SfCircularGauge)

Ticks help you identify the gauge’s data value by marking the gauge scale in regular increments.

## Tick customization

The Interval property is used to calculate the tick count for a scale. Similar ticks, small ticks are calculated using the [`MinorTicksPerInterval`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Gauges.CircularScale.html#Syncfusion_UI_Xaml_Gauges_CircularScale_MinorTicksPerInterval) property.

The length, stroke, and stroke thickness of a tick are set using the [`TickLength`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Gauges.CircularScale.html#Syncfusion_UI_Xaml_Gauges_CircularScale_TickLength), [`TickStroke`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Gauges.CircularScale.html#Syncfusion_UI_Xaml_Gauges_CircularScale_TickStroke), and [`TickStrokeThickness`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Gauges.CircularScale.html#Syncfusion_UI_Xaml_Gauges_CircularScale_TickStrokeThickness) UI properties, respectively. Similar ticks, the length, stroke, and stroke thickness of a small tick are set using the [`SmallTickLength`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Gauges.CircularScale.html#Syncfusion_UI_Xaml_Gauges_CircularScale_SmallTickLength), [`SmallTickStroke`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Gauges.CircularScale.html#Syncfusion_UI_Xaml_Gauges_CircularScale_SmallTickStroke), and [`SmallTickStrokeThickness`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Gauges.CircularScale.html#Syncfusion_UI_Xaml_Gauges_CircularScale_SmallTickStrokeThickness) UI properties, respectively.

### Customize major ticks for scale

{% tabs %}

{% highlight xml %}

    <gauge:SfCircularGauge>

    <gauge:SfCircularGauge.Scales>

    <gauge:CircularScale Radius="150" RimStroke="#39B2C6" RimStrokeThickness="9" TickLength="20"

    TickStrokeThickness="2"  TickStroke="Brown" LabelStroke="#9E9E9E" SmallTickStroke="White">

    </gauge:CircularScale>

    </gauge:SfCircularGauge.Scales>

    </gauge:SfCircularGauge>

{% endhighlight %}

{% highlight c# %}

             SfCircularGauge sfCircularGauge = new SfCircularGauge();

            CircularScale circularScale = new CircularScale();

            circularScale.Radius = 150;

            circularScale.RimStroke = new SolidColorBrush(Color.FromArgb(0xff, 0x57, 0xb2, 0xc6));

            circularScale.TickLength = 20;

            circularScale.TickStrokeThickness = 2;

            circularScale.TickStroke = new SolidColorBrush(Colors.Brown);

            circularScale.SmallTickStroke = new SolidColorBrush(Colors.White);

            circularScale.RimStrokeThickness = 9;

            circularScale.LabelStroke = new SolidColorBrush(Color.FromArgb(0xff, 0x99, 0x99, 0x99));

            sfCircularGauge.Scales.Add(circularScale);

{% endhighlight %}

{% endtabs %}

![Ticks_img1](Ticks_images/Ticks_img1.png)

### Customize minor ticks for scale

{% tabs %}

{% highlight xml %}

    <gauge:SfCircularGauge>

    <gauge:SfCircularGauge.Scales>

    <gauge:CircularScale Radius="150" RimStroke="#39B2C6" RimStrokeThickness="9"

     MinorTicksPerInterval="3" SmallTickStrokeThickness="2"   SmallTickLength="10"

    TickStroke="#BEBEBE" LabelStroke="#9E9E9E" SmallTickStroke="Blue">

    </gauge:CircularScale>

    </gauge:SfCircularGauge.Scales>

    </gauge:SfCircularGauge>

{% endhighlight %}

{% highlight c# %}

            SfCircularGauge sfCircularGauge = new SfCircularGauge();

            CircularScale circularScale = new CircularScale();

            circularScale.Radius = 150;

            circularScale.RimStroke = new SolidColorBrush(Color.FromArgb(0xff, 0x57, 0xb2, 0xc6));

            circularScale.SmallTickLength = 10;

            circularScale.SmallTickStrokeThickness = 2;

            circularScale.TickStroke = new SolidColorBrush(Color.FromArgb(0xff, 0xc1, 0xc1, 0xc1));

            circularScale.SmallTickStroke = new SolidColorBrush(Colors.Blue);

            circularScale.RimStrokeThickness = 9;

            circularScale.MinorTicksPerInterval = 3;

            circularScale.LabelStroke = new SolidColorBrush(Color.FromArgb(0xff, 0x99, 0x99, 0x99));

            sfCircularGauge.Scales.Add(circularScale);

{% endhighlight %}

{% endtabs %}

![Ticks_img2](Ticks_images/Ticks_img2.png)

## Setting shape for tick

The [`TickShape`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Gauges.CircularScale.html#Syncfusion_UI_Xaml_Gauges_CircularScale_TickShape) is an enum property that provides an option to select shape of the circular mark ticks, which contains several shapes such as rectangle, ellipse, and triangle.

{% tabs %}

{% highlight xml %}

    <gauge:SfCircularGauge>

    <gauge:SfCircularGauge.Scales>

    <gauge:CircularScale Radius="150" RimStroke="#39B2C6" RimStrokeThickness="9"

    MinorTicksPerInterval="3" SmallTickStrokeThickness="2"

    SmallTickLength="10" TickShape="Triangle"

    TickStroke="Blue" LabelStroke="#9E9E9E" SmallTickStroke="Blue">

    </gauge:CircularScale>

    </gauge:SfCircularGauge.Scales>

    </gauge:SfCircularGauge>

{% endhighlight %}

{% highlight c# %}

           SfCircularGauge sfCircularGauge = new SfCircularGauge();

            CircularScale circularScale = new CircularScale();

            circularScale.Radius = 150;

            circularScale.RimStroke = new SolidColorBrush(Color.FromArgb(0xff, 0x57, 0xb2, 0xc6));

            circularScale.SmallTickLength = 10;

            circularScale.SmallTickStrokeThickness = 2;

            circularScale.TickStroke = new SolidColorBrush(Colors.Blue);

            circularScale.SmallTickStroke = new SolidColorBrush(Colors.Blue);

            circularScale.RimStrokeThickness = 9;

            circularScale.TickShape = TickShape.Triangle;

            circularScale.MinorTicksPerInterval = 3;

            circularScale.LabelStroke = new SolidColorBrush(Color.FromArgb(0xff, 0x99, 0x99, 0x99));

            sfCircularGauge.Scales.Add(circularScale);

{% endhighlight %}

{% endtabs %}

![Ticks_img3](Ticks_images/Ticks_img3.png)

## Setting position for tick

The major and minor ticks can be positioned far away from the rim using the following two ways:
 
    1. Using the `MajorTickOffset` and `MinorTickOffset` properties. First, set the `TickPosition` property to custom, and then set the offset of the tick.

{% tabs %}

{% highlight xml %}

    <gauge:SfCircularGauge>

    <gauge:SfCircularGauge.Scales>

    <gauge:CircularScale Radius="150" RimStroke="#39B2C6" RimStrokeThickness="9"

    MinorTicksPerInterval="3" TickPosition="Custom"

    MajorTickOffset="0.5" MinorTickOffset="0.5"

    TickStroke="#BEBEBE" LabelStroke="#9E9E9E" SmallTickStroke="#BEBEBE">

    </gauge:CircularScale>

    </gauge:SfCircularGauge.Scales>

    </gauge:SfCircularGauge>

{% endhighlight %}

{% highlight c# %}

            SfCircularGauge sfCircularGauge = new SfCircularGauge();

            CircularScale circularScale = new CircularScale();

            circularScale.Radius = 150;

            circularScale.RimStroke = new SolidColorBrush(Color.FromArgb(0xff, 0x57, 0xb2, 0xc6));

            circularScale.TickStroke = new SolidColorBrush(Color.FromArgb(0xff, 0xc1, 0xc1, 0xc1));

            circularScale.SmallTickStroke = new SolidColorBrush(Color.FromArgb(0xff, 0xc1, 0xc1, 0xc1));

            circularScale.RimStrokeThickness = 9;

            circularScale.MinorTicksPerInterval = 3;

            circularScale.TickPosition = TickPosition.Custom;

            circularScale.MajorTickOffset = 0.5;

            circularScale.MinorTickOffset = 0.5;

            circularScale.LabelStroke = new SolidColorBrush(Color.FromArgb(0xff, 0x99, 0x99, 0x99));

            sfCircularGauge.Scales.Add(circularScale);

{% endhighlight %}

{% endtabs %}

![Ticks_img4](Ticks_images/Ticks_img4.png)

    2. Placing the ticks inside the scale, outside the scale, or across the scale by selecting one of the options available in the `TickPosition` property. 
    
    They are:

1.	Inside (Default)

2.	Outside

3.	Cross

4.	Custom

{% tabs %}

{% highlight xml %}

    <gauge:SfCircularGauge>

    <gauge:SfCircularGauge.Scales>

    <gauge:CircularScale Radius="150" RimStroke="#39B2C6" RimStrokeThickness="9"

    MinorTicksPerInterval="3" TickPosition="Outside" TickStroke="#BEBEBE" LabelStroke="#9E9E9E" SmallTickStroke="#BEBEBE">

    </gauge:CircularScale>

    </gauge:SfCircularGauge.Scales>

    </gauge:SfCircularGauge>


{% endhighlight %}

{% highlight c# %}

           SfCircularGauge sfCircularGauge = new SfCircularGauge();

            CircularScale circularScale = new CircularScale();

            circularScale.Radius = 150;

            circularScale.RimStroke = new SolidColorBrush(Color.FromArgb(0xff, 0x57, 0xb2, 0xc6));

            circularScale.TickStroke = new SolidColorBrush(Color.FromArgb(0xff, 0xc1, 0xc1, 0xc1));

            circularScale.SmallTickStroke = new SolidColorBrush(Color.FromArgb(0xff, 0xc1, 0xc1, 0xc1));

            circularScale.RimStrokeThickness = 9;

            circularScale.MinorTicksPerInterval = 3;

            circularScale.TickPosition = TickPosition.Outside;

            circularScale.LabelStroke = new SolidColorBrush(Color.FromArgb(0xff, 0x99, 0x99, 0x99));

            sfCircularGauge.Scales.Add(circularScale);

{% endhighlight %}

{% endtabs %}

![Ticks_img5](Ticks_images/Ticks_img5.png)
