---
layout: post
title: Legend in UWP HeatMap (SfHeatMap) control | Syncfusion®
description: How to create and configure legend for Syncfusion® Essential Studio® UWP HeatMap (SfHeatMap) control, its elements and more.
platform: uwp
control: SfHeatMap
documentation: ug
---

# Legend in UWP HeatMap (SfHeatMap) control
Legend is a control used to summarize the color ranges in a HeatMap, providing a visual guide for mapping values to their corresponding colors.

## Create Legend
Legend can be created with color mapping as shown below.

{% tabs %}
{% highlight xaml %}

<syncfusion:ColorMappingCollection x:Key="colorMapping">
    <syncfusion:ColorMapping Value="0" Color="#fe0002" Label="Poor"/>
    <syncfusion:ColorMapping Value="3" Color="#ffff01" Label="Average"/>
    <syncfusion:ColorMapping Value="6" Color="#13ab11" Label="Good"/>
    <syncfusion:ColorMapping Value="10" Color="#005ba2 " Label="Excellent"/>
</syncfusion:ColorMappingCollection>

<syncfusion:SfHeatMapLegend ColorMappingCollection="{StaticResource colorMapping}"/>

{% endhighlight %}
{% endtabs %}

The resulting legend will appear as shown in the following image.

![Legend_Image](Images/Legend.png)

## Legend Mode
There are two modes available for the legend:

* Gradient
* List

### Gradient

{% tabs %}
{% highlight xaml %}
<syncfusion:SfHeatMapLegend 
	LegendMode="Gradient" 
	ColorMappingCollection="{StaticResource colorMapping}"/>
{% endhighlight %}
{% endtabs %}

![Legend_Image](Images/Legend_Gradient.png)

### List

{% tabs %}
{% highlight xaml %}
<syncfusion:SfHeatMapLegend
	LegendMode="List" 
	ColorMappingCollection="{StaticResource colorMapping}"/>
{% endhighlight %}
{% endtabs %}

![Legend_Image](Images/Legend_List.png)

## Orientation
There are two types of orientation available for both Gradient and List modes:
* Horizontal
* Vertical

### Horizontal

{% tabs %}
{% highlight xaml %}
<syncfusion:SfHeatMapLegend 
	LegendMode="List" 
	Orientation="Horizontal" 
	ColorMappingCollection="{StaticResource colorMapping}"/>
{% endhighlight %}
{% endtabs %}

![Legend_Image](Images/Legend_Horizontal.png)

### Vertical

{% tabs %}
{% highlight xaml %}
<syncfusion:SfHeatMapLegend 
	LegendMode="List" 
	Orientation="Vertical" 
	ColorMappingCollection="{StaticResource colorMapping}"/>
{% endhighlight %}
{% endtabs %}

![Legend_Image](Images/Legend_Vertical.png)
