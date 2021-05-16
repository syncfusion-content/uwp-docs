---
layout: post
title: Ranges in UWP Bullet Graph control | Syncfusion
description: Learn here all about Ranges support in Syncfusion UWP Bullet Graph (SfBulletGraph) control and more.
platform: uwp
control: SfBulletGraph
documentation: ug
---

# Ranges in UWP Bullet Graph (SfBulletGraph)

Ranges for a bullet graph are a collection of qualitative ranges. A qualitative range is a visual element which ends at a specified **RangeEnd** at the start of the previous range’s RangeEnd. The qualitative ranges are arranged according to each RangeEnd value.

## Customizing Range

The width of the ranges can be customized by setting the **QualitativeRangesSize** property. By changing **RangeStroke** of the qualitative range, the stroke of the range can be personalized. By setting the **RangeOpacity** of the qualitative range the opacity of the range is modified.

{% tabs %}
{% highlight xaml %}

        <syncfusion:SfBulletGraph QualitativeRangesSize="30" >
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

![Output image of customized range](Ranges_images/Ranges_img1.jpeg)

## Binding RangeStroke to Ticks and Labels

By setting **BindWithRangeStrokeToLabels**, the stroke of the labels is set related to the stroke of the specified ranges. Similarly, by setting **BindWithRangeStrokeToTicks**, the stroke of the ticks is set related to the stroke of the specified ranges.

{% tabs %}
{% highlight xaml %}

    <syncfusion:SfBulletGraph BindRangeStrokeToLabels="True"
    BindRangeStrokeToTicks="True">
    </syncfusion:SfBulletGraph>

{% endhighlight %}

{% highlight c# %}

    SfBulletGraph bullet = new SfBulletGraph();
    bullet.BindRangeStrokeToLabels = true;
    bullet.BindRangeStrokeToTicks = true;
    this.Grid.Children.Add(bullet);

{% endhighlight %}
{% endtabs %}

![Output image of range stroke](Ranges_images/Ranges_img2.jpg)

## See also

[How to refresh bullet graph with dynamic data](https://www.syncfusion.com/kb/9996/how-to-refresh-bulletgraph-with-dynamic-data)
