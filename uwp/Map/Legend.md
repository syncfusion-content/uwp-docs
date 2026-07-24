---
layout: post
title: Legend in UWP Map control | Syncfusion
description: Learn how to configure, position, and customize legends for shape and bubble layers in the Syncfusion UWP Map control using SfMaps properties.
platform: uwp
control: SfMaps
documentation: ug
---

# Legend in UWP Map (SfMaps)

A legend is a key to the symbolism used on a map, usually containing swatches of symbols with descriptions. It provides valuable information for interpreting what the map is displaying, and can be represented in various colors and shapes based on the data.

## Visibility of Legend

Legends are visible only by setting the [`LegendVisibility`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Maps.ShapeFileLayer.html#Syncfusion_UI_Xaml_Maps_ShapeFileLayer_LegendVisibility) property of the `Visibility` type as `Visible` in the [`ShapeFileLayer`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Maps.ShapeFileLayer.html).

## Positioning of Legend

Map legends can be positioned by setting the [`LegendPosition`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Maps.ShapeFileLayer.html#Syncfusion_UI_Xaml_Maps_ShapeFileLayer_LegendPosition) property in the `ShapeFileLayer`. Also, the legend can be positioned based on the margin values for the x-axis and the y-axis with the help of the [`LegendPositionX`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Maps.ShapeFileLayer.html#Syncfusion_UI_Xaml_Maps_ShapeFileLayer_LegendPositionX) and [`LegendPositionY`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Maps.ShapeFileLayer.html#Syncfusion_UI_Xaml_Maps_ShapeFileLayer_LegendPositionY) properties available in the `ShapeFileLayer`. For positioning the legend based on the margins corresponding to a map, `LegendPosition` must be set to `Default`.

<table>
<tr>
<th>
Property</th><th>
Type</th><th>
Description</th></tr>
<tr>
<td>
[LegendPosition](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Maps.ShapeFileLayer.html#Syncfusion_UI_Xaml_Maps_ShapeFileLayer_LegendPosition)</td><td>
[LegendPosition](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Maps.LegendPosition.html) (enum)</td><td>
Gets or sets the standard position for the legend.</td></tr>
<tr>
<td>
[LegendPositionX](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Maps.ShapeFileLayer.html#Syncfusion_UI_Xaml_Maps_ShapeFileLayer_LegendPositionX)</td><td>
Double</td><td>
Gets or sets the margin value for the x-axis.</td></tr>
<tr>
<td>
[LegendPositionY](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Maps.ShapeFileLayer.html#Syncfusion_UI_Xaml_Maps_ShapeFileLayer_LegendPositionY)</td><td>
Double</td><td>
Gets or sets the margin value for the y-axis.</td></tr>
</table>


## Header for Legends

A header for the legend can be added by setting the [`LegendHeader`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Maps.ShapeFileLayer.html#Syncfusion_UI_Xaml_Maps_ShapeFileLayer_LegendHeader) property of the string type.

## Categories of Legend

Legends are categorized into two types:

* Legends for shape layers.
* Legends for bubbles.

These can be set using the [`LegendType`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Maps.ShapeFileLayer.html#Syncfusion_UI_Xaml_Maps_ShapeFileLayer_LegendType) property of the [`LegendType`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Maps.LegendType.html) type.

## Legends for Shapes

Layer shape type legends can have different shapes for the legend. The shapes can be set using the [`LegendIcon`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Maps.ShapeFileLayer.html#Syncfusion_UI_Xaml_Maps_ShapeFileLayer_LegendIcon) property of the [`LegendIcons`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Maps.LegendIcons.html) type.

{% highlight html %}

<syncfusion:SfMap>
    <syncfusion:SfMap.Layers>
        <syncfusion:ShapeFileLayer LegendType="Layers" LegendHeader="LegendHeader"
            LegendColumnSplit="2" LegendPositionX="10"
            LegendPositionY="200" LegendVisibility="Visible"
            LegendIcon="Rectangle" ItemsSource="{Binding Countries1}" ShapeIDPath="NAME"
            ShapeIDTableField="NAME" Uri="LegendSample.ShapeFile.world1.shp">
            <syncfusion:ShapeFileLayer.ShapeSettings>
                <syncfusion:ShapeSetting ShapeFill="#E5E5E5" ShapeStroke="#C1C1C1" ShapeStrokeThickness="0.5" ShapeValuePath="Population">
                    <syncfusion:ShapeSetting.FillSetting>
                        <syncfusion:ShapeFillSetting AutoFillColors="False">
                            <syncfusion:ShapeFillSetting.ColorMappings>
                                <syncfusion:RangeColorMapping Color="#7F20BCEE" From="100000000" To="1000000000"/>
                                <syncfusion:RangeColorMapping Color="#7FA7CE38" From="10000000" To="100000000"/>
                                <syncfusion:RangeColorMapping Color="#7FF1B21A" From="1000000" To="10000000"/>
                                <syncfusion:RangeColorMapping Color="#7F1DA249" From="10000" To="100000"/>
                                <syncfusion:RangeColorMapping Color="#7FEB737C" From="1000" To="10000"/>
                                <syncfusion:RangeColorMapping Color="#7FED2D95" From="0" To="1000"/>
                            </syncfusion:ShapeFillSetting.ColorMappings>
                        </syncfusion:ShapeFillSetting>
                    </syncfusion:ShapeSetting.FillSetting>
                </syncfusion:ShapeSetting>
            </syncfusion:ShapeFileLayer.ShapeSettings>
        </syncfusion:ShapeFileLayer>
    </syncfusion:SfMap.Layers>
</syncfusion:SfMap>

{% endhighlight %}

![UWP Map Control Legend for Shapes](Legend_images/Legend_img1.png)


## Legends for Bubbles

`Bubble` type legends are always bubbles with varying sizes. The size of the bubbles is obtained from the [`SizeRatio`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Maps.BubbleMarkerSetting.html#Syncfusion_UI_Xaml_Maps_BubbleMarkerSetting_SizeRatio) property of the [`BubbleMarkerSetting`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Maps.BubbleMarkerSetting.html).

{% highlight html %}

<syncfusion:SfMap>
    <syncfusion:SfMap.Layers>
        <syncfusion:ShapeFileLayer LegendType="Bubble" LegendHeader="LegendHeader" LegendColumnSplit="2" LegendPositionX="10" LegendPositionY="200" LegendVisibility="Visible" LegendIcon="Rectangle" ItemsSource="{Binding Countries1}" ShapeIDPath="NAME" ShapeIDTableField="NAME" Uri="LegendSample.ShapeFile.world1.shp">
            <syncfusion:ShapeFileLayer.BubbleMarkerSetting>
                <syncfusion:BubbleMarkerSetting AutoFillColor="False" MaxSize="50" MinSize="20" StrokeThickness="0" ValuePath="Population">
                    <syncfusion:BubbleMarkerSetting.ColorMappings>
                        <syncfusion:RangeColorMapping Color="#7F20BCEE" From="100000000" To="1000000000"/>
                        <syncfusion:RangeColorMapping Color="#7FA7CE38" From="10000000" To="100000000"/>
                        <syncfusion:RangeColorMapping Color="#7FF1B21A" From="1000000" To="10000000"/>
                        <syncfusion:RangeColorMapping Color="#7F1DA249" From="10000" To="100000"/>
                        <syncfusion:RangeColorMapping Color="#7FEB737C" From="1000" To="10000"/>
                        <syncfusion:RangeColorMapping Color="#7FED2D95" From="0" To="1000"/>
                    </syncfusion:BubbleMarkerSetting.ColorMappings>
                </syncfusion:BubbleMarkerSetting>
            </syncfusion:ShapeFileLayer.BubbleMarkerSetting>
        </syncfusion:ShapeFileLayer>
    </syncfusion:SfMap.Layers>
</syncfusion:SfMap>

{% endhighlight %}


![UWP Map Control Legend for Bubbles](Legend_images/Legend_img2.png)

## Arranging the Legends

Legends are arranged in a matrix format. The number of columns in the arranging matrix can be set by setting the [`LegendColumnSplit`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Maps.ShapeFileLayer.html#Syncfusion_UI_Xaml_Maps_ShapeFileLayer_LegendColumnSplit) property of the `int` type. 




