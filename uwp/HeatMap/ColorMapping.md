---
layout: post
title: ColorMapping in UWP HeatMap (SfHeatMap) control | Syncfusion®
description: How to configure colors codes for Syncfusion® Essential Studio® uwp HeatMap (SfHeatMap) control, its elements and more.
platform: uwp
control: SfHeatMap
documentation: ug
---

# Color Mapping in UWP HeatMap (SfHeatMap) control
Color mapping is used to indicate values as colors instead of numerical values. For example, if a HeatMap represents a data from 0 to 100. [ColorMapping](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.HeatMap.ColorMapping.html) is used to specify a color for lower value and higher value. For any value between two values, a medium color will be automatically be chosen. 

In color mapping, when white color is set to value 0 and red color is set for value 30, as shown below.
{% highlight xaml %}
<syncfusion:ColorMappingCollection x:Key="colorMapping">
	<syncfusion:ColorMapping Value="0" Color="White"/>
	<syncfusion:ColorMapping Value="30" Color="Red"/>
</syncfusion:ColorMappingCollection>
{% endhighlight %}

Resultant HeatMap will be as shown below.

![ColorMapping_Image](Images/ColorMapping.png)
