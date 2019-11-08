---
layout: post
title: Map Selection in SfMaps control
description: How to select map shapes?
platform: UWP
control: SfMaps
documentation: ug
---

# Map Selection

Each shape in the map can be selected and unselected when interacted with shapes. There are two ways to select the map shapes:

* `SingleSelection` 
* `MultiSelection`

The selected map shapes is differentiate by its fill. `SelectedShapeColor` of ShapeSetting is the API that is used to get or set the selected shape color.

All selected shapes available in the `SelectedMapShapes` of ShapeFileLayer.

## Single Selection

Single selection allows only one map shape to be selected at a time. You can select the shape by tapping on the shape. Single selection is enabled by the `EnableSelection` property of ShapeFileLayer. When EnableSelection is set to true, then the map can be selected. When it is set to false, the shapes cannot be selected. When any other shape or the map area is selected, then the shape that is already selected is unselected.

{% highlight html %}

        <syncfusion:SfMap >
                <syncfusion:SfMap.Layers>
                    <syncfusion:ShapeFileLayer x:Name="shapeLayer" EnableSelection ="True"                                               
                                                Uri="MapApp.world1.shp"  >
                        <syncfusion:ShapeFileLayer.ShapeSettings>
                            <syncfusion:ShapeSetting ShapeFill="#E5E5E5" SelectedShapeColor="#1196CD" ShapeStroke="#C1C1C1" ShapeStrokeThickness="1" />
                        </syncfusion:ShapeFileLayer.ShapeSettings>
                    </syncfusion:ShapeFileLayer>
                </syncfusion:SfMap.Layers>
            </syncfusion:SfMap >

{% endhighlight %}

![](Features_images/Features_img17.png)

## Multi Selection

Multiple shapes in the map can be selected when `EnableMultiSelection` of ShapeFileLayer is set to true. When EnableMultiSelection is set to true, a cross-hair cursor appears on the map to guide the selection. When you drag on the map, a rectangle appears. The shapes bound that intersect with the rectangle is selected. When EnableMultiSelection is set to `True`, the panning does not work through interactions.

{% highlight html %}

        <syncfusion:SfMap >
                <syncfusion:SfMap.Layers>
                    <syncfusion:ShapeFileLayer x:Name="shapeLayer" CrossCursorStroke="#686868" CrossCursorStrokeThickness="0.5"  
                                               EnableMultiSelection="True"                                               
                                                Uri="MapApp.world1.shp"  >
                        <syncfusion:ShapeFileLayer.ShapeSettings>
                            <syncfusion:ShapeSetting ShapeFill="#E5E5E5" SelectedShapeColor="#1196CD" ShapeStroke="#C1C1C1" ShapeStrokeThickness="1" />
                        </syncfusion:ShapeFileLayer.ShapeSettings>
                    </syncfusion:ShapeFileLayer>
                </syncfusion:SfMap.Layers>
            </syncfusion:SfMap >

{% endhighlight %}


![](Features_images/Features_img16.png)
