---
layout: post
title: Getting Started with UWP Bullet Graph | Syncfusion®
description: Learn how to get started with the Syncfusion® UWP Bullet Graph control. Explore setup, features, examples, and customization options.
platform: uwp
control: SfBulletGraph
documentation: ug
---

# Getting Started with UWP Bullet Graph

This section explains you the steps required to configure the [`SfBulletGraph`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.BulletGraph.SfBulletGraph.html) and also explains the steps to add basic elements of **UWP Bullet Graph** through various API’s available within it.

## Configuring UWP Bullet Graph

**UWP Bullet Graph** is available in the following assembly and namespace:

**Assembly**: Syncfusion.SfBulletGraph.UWP

**Namespace**: Syncfusion.UI.Xaml.BulletGraph

{% tabs %}
{% highlight xaml %}

<syncfusion:SfBulletGraph/>

{% endhighlight %}

{% highlight c# %}

SfBulletGraph bullet = new SfBulletGraph();
this.Grid.Children.Add(bullet);

{% endhighlight %}
{% endtabs %}

![Output image of UWP Bullet Graph getting started](Getting-Started_images/Getting-Started_img1.jpg)

As you can see now in the above image, the UWP Bullet Graph displays its default elements. To customize its element, you have to add respective elements to UWP Bullet Graph, following section contains the steps to add the basic elements to UWP Bullet Graph.

## Adding caption

You can assign a caption to **UWP Bullet Graph** by making use of “Caption” property and also you can position it either near or far using [`CaptionPosition`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.BulletGraph.SfBulletGraph.html#Syncfusion_UI_Xaml_BulletGraph_SfBulletGraph_CaptionPosition) property.

{% tabs %}
{% highlight xaml %}

<syncfusion:SfBulletGraph CaptionPosition="Far" Caption="Revenue YTD" />

{% endhighlight %}

{% highlight c# %}

SfBulletGraph bullet = new SfBulletGraph();
bullet.Caption = "Revenue YTD";
bullet.CaptionPosition  = BulletGraphCaptionPosition.Far;
this.Grid.Children.Add(bullet);

{% endhighlight %}
{% endtabs %}

![Output image of the UWP Bullet Graph with added caption](Getting-Started_images/Getting-Started_img2.jpg)

## Configuring ticks and labels 

You can configure Ticks and Labels of Quantitative Scale by making use of following API’s available in UWP Bullet Graph.

They are:

* Minimum
* Maximum
* Interval
* MinorTicksPerInterval
* MajorTickSize
* MinorTickSize
* MajorTickStroke
* LabelStroke
* MinorTickStroke

{% tabs %}
{% highlight xaml %}

<syncfusion:SfBulletGraph Minimum="0" Maximum="10" Interval="2"   
                          QualitativeRangesSize="30" QuantitativeScaleLength="300"    
                          MinorTicksPerInterval="3" MajorTickSize="15" MinorTickSize="10"
                          MajorTickStroke="Red" LabelStroke="Black" MinorTickStroke="Green" />

{% endhighlight %}

{% highlight c# %}

SfBulletGraph bullet = new SfBulletGraph();
bullet.FlowDirection = BulletGraphFlowDirection.Forward;
bullet.Orientation = Orientation.Horizontal;
bullet.QualitativeRangesSize = 30;
bullet.QuantitativeScaleLength = 300;
bullet.Minimum = 0;
bullet.Maximum = 10;
bullet.Interval = 2;
bullet.MinorTicksPerInterval = 3;
bullet.MajorTickSize = 15;
bullet.MinorTickSize = 10;
bullet.MajorTickStroke = new SolidColorBrush(Colors.Red);
bullet.LabelStroke = new SolidColorBrush(Colors.Black);
bullet.MinorTickStroke = new SolidColorBrush(Colors.Green);
this.Grid.Children.Add(bullet);

{% endhighlight %}
{% endtabs %}

![Output image of UWP Bullet Graph with configured labels and ticks](Getting-Started_images/Getting-Started_img3.jpg)

## Adding ranges 

You can add ranges to **UWP Bullet Graph** by creating ranges collection using [`QualitativeRanges`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.BulletGraph.SfBulletGraph.html#Syncfusion_UI_Xaml_BulletGraph_SfBulletGraph_QualitativeRanges).

{% tabs %}
{% highlight xaml %}

<syncfusion:SfBulletGraph Orientation="Horizontal" Minimum="0" Maximum="10" Interval="2"  FlowDirection="Forward"
                          QualitativeRangesSize="30" QuantitativeScaleLength="300">
    <syncfusion:SfBulletGraph.QualitativeRanges>
        <syncfusion:QualitativeRange RangeEnd="4.5" 
                                        RangeStroke="Red"
                                        RangeOpacity="1">
        </syncfusion:QualitativeRange>
        <syncfusion:QualitativeRange RangeEnd="7.5" 
                                        RangeStroke="Yellow"
                                        RangeOpacity="1">
        </syncfusion:QualitativeRange>
        <syncfusion:QualitativeRange RangeEnd="10" 
                                        RangeStroke="Green"
                                        RangeOpacity="1">
        </syncfusion:QualitativeRange>
    </syncfusion:SfBulletGraph.QualitativeRanges>
</syncfusion:SfBulletGraph>

{% endhighlight %}

{% highlight c# %}

SfBulletGraph bullet = new SfBulletGraph();
bullet.QualitativeRangesSize = 30;
bullet.QuantitativeScaleLength = 300;
bullet.FlowDirection = BulletGraphFlowDirection.Forward;
bullet.Orientation = Orientation.Horizontal;
bullet.Minimum = 0;
bullet.Maximum = 10;
bullet.Interval = 2;
bullet.QualitativeRanges.Add(new QualitativeRange()
{
    RangeEnd = 4.5,
    RangeOpacity = 1,
    RangeStroke = new SolidColorBrush(Colors.Red)
});
bullet.QualitativeRanges.Add(new QualitativeRange()
{
    RangeEnd = 7.5,
    RangeOpacity = 1,
    RangeStroke = new SolidColorBrush(Colors.Yellow)
});
bullet.QualitativeRanges.Add(new QualitativeRange()
{
    RangeEnd = 10,
    RangeOpacity = 1,
    RangeStroke = new SolidColorBrush(Colors.Green)
});
this.Grid.Children.Add(bullet);
            
{% endhighlight %}
{% endtabs %}

UWP Bullet Graph ranges are displayed as follows.

![Output image of bullet graph with ranges](Getting-Started_images/Getting-Started_img4.jpg)

## See also

[How to refresh bullet graph with dynamic data](https://www.syncfusion.com/kb/9996/how-to-refresh-bulletgraph-with-dynamic-data)
