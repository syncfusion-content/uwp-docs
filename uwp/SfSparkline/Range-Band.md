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

* [`BandRangeStart`](http://help.syncfusion.com/cr/cref_files/uwp/sfchart/frlrfSyncfusionUIXamlChartsSparklineBaseClassBandRangeStartTopic.html) – Gets or sets the minimum range band value in Y axis.
* [`BandRangeEnd`](http://help.syncfusion.com/cr/cref_files/uwp/sfchart/frlrfSyncfusionUIXamlChartsSparklineBaseClassBandRangeEndTopic.html) – Gets or sets the maximum range band value in Y axis.
* [`RangeBandBrush`](http://help.syncfusion.com/cr/cref_files/uwp/sfchart/frlrfSyncfusionUIXamlChartsSparklineBaseClassRangeBandBrushTopic.html) – Gets or sets the brush for range band.

{%highlight xaml%}

<Syncfusion:SfLineSparkline

BorderBrush="DarkGray" BorderThickness="1" 

ItemsSource="{Binding UsersList}" BandRangeStart="3500"   

Interior="#4a4a4a"  BandRangeEnd="8500" 

RangeBandBrush="DeepSkyBlue" Stroke="Red"

YBindingPath="NoOfUsers">

</Syncfusion:SfLineSparkline >

{%endhighlight%}

![RangeBand](Range-Band_images/RangeBand_img1.jpeg)
