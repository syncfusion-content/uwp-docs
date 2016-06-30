---
layout: post
title: Highlight Segment for Sparkline
description: Highlight Segment for Sparkline
platform: uwp
control: SfSparkline
documentation: ug
---
# Highlight Segment

This feature enable to highlight the column segments on mouse move and this is applicable for column and win-loss sparkline.

{%highlight xaml%}

<Syncfusion:SfWinLossSparkline Interior="Gray" BorderBrush="DarkGray" 

BorderThickness="1" 

HighlightSegment="True" x:Name="sparkline"  

ItemsSource="{Binding Match}" YBindingPath="Result" >

</Syncfusion:SfWinLossSparkline>

{%endhighlight%}

Following is the snapshot for highlight segment,

![Highlighted SfWinLossSparkline segment](Highlight-Segment_images/HighlightSegment_img1.jpeg)
