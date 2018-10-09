---
layout: post
title: Range Band support for Sparkline
description: Range Band support for Sparkline
platform: uwp
control: SfSparkline
documentation: ug
---

# Range Band

Range band feature is used to highlight the particular mentioned range along Y axis.

* [`BandRangeStart`](http://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.SparklineBase~BandRangeStart.html) – Gets or sets the minimum range band value in Y axis.
* [`BandRangeEnd`](http://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.SparklineBase~BandRangeEnd.html) – Gets or sets the maximum range band value in Y axis.
* [`RangeBandBrush`](http://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.SparklineBase~RangeBandBrush.html) – Gets or sets the brush for range band.

{% tabs %}

{%highlight xaml%}

<Syncfusion:SfLineSparkline

BorderBrush="DarkGray" BorderThickness="1" 

ItemsSource="{Binding UsersList}" BandRangeStart="3500"   

Interior="#4a4a4a"  BandRangeEnd="8500" 

RangeBandBrush="DeepSkyBlue" Stroke="Red"

YBindingPath="NoOfUsers">

</Syncfusion:SfLineSparkline >

{%endhighlight%}

{% highlight c# %}

SfLineSparkline sparkline = new SfLineSparkline()
{

	ItemsSource = new SparkViewModel().UsersList,

	YBindingPath = "NoOfUsers",

	BandRangeStart = 2000,

	BandRangeEnd = -1000,

	RangeBandBrush = new SolidColorBrush(Colors.Green)

};

{% endhighlight %}

{% endtabs %}

![RangeBand](Range-Band_images/RangeBand_img1.jpeg)
