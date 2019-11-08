---
layout: post
title: Zooming and Panning in SfMaps control
description: Learn how to perform zooming and panning in Maps
platform: UWP
control: SfMaps
documentation: ug
---

# Zooming and Panning

The Zooming and Panning feature of the Map control allows users to zoom in and out and navigate the map.

## Zooming

The zooming feature enables users to zoom in and out of the map to show in-depth information. It is controlled by the `ZoomLevel` property of the map. When the zoom level of the Map control is increased, the map is zoomed in. If the zoom level is decreased then the map is zoomed out.

## Properties Related to Zooming

The following properties are related to the zooming feature of the Maps control:

* ZoomLevel
* EnableZoom
* MinZoom
* MaxZoom

## ZoomLevel

`ZoomLevel` is the primary property of the zooming feature. It controls the map’s scale size while zooming. Initially, the zoom level is 1. ZoomLevel cannot be less than 1.

## EnableZoom

The `EnableZoom` property enables or disables the zooming feature. A `True` value of this property enables the zooming feature and `False` disables the zooming feature.

## MinZoom

The `MinZoom` property is used to set the minimum zoom level of the map. 

## MaxZoom

The `MaxZoom` property is used to set the maximum zoom level of the Map control.

{% highlight html %}

        <syncfusion:SfMap ZoomLevel="3" MinZoom="1" MaxZoom="20" EnableZoom="True">                
        </syncfusion:SfMap >

{% endhighlight %}

## Methods to Zoom the Map:

Maps can be zoomed using the following methods:

* By changing the ZoomLevel.
* Through the Zoom method.
* By pinching the map.
* Through the mouse scroll.
* By double-tapping on the map.



## Changing the ZoomLevel

A map can be zoomed by changing the zoom level of the Map control. Incrementing the ZoomLevel will zoom in on the map and decrementing the ZoomLevel will zoom out of the map.

## Through the Zoom method

Maps can be zoomed through the Zoom method. The Zoom method has the parameter zoom value. The map can be zoomed or scaled with the zoom value parameter.

{% highlight c# %}

        SfMap syncMap = new SfMap();
        ShapeFileLayer shapeLayer = new ShapeFileLayer();
        shapeLayer.Uri = "MapApp.ShapeFiles.world.shp";
        syncMap.Layers.Add(shapeLayer);
        syncMap.Zoom(5);

{% endhighlight  %}

## By pinching the map

Since UWP fully supports touch interactions, the Maps control also supports touch interactions.  Maps can be zoomed through pinching events. Scale value is determined by using the delta value of the pinch event.

## Through a mouse wheel event

In addition to the pinching event, the map can be zoomed with mouse events.  When the mouse is scrolled up, the map is zoomed in. When the mouse is scrolled down, the map is zoomed out.

## Through a double-tapping event

When the map is double-tapped, the zooming operation is performed. 


![](Features_images/Features_img6.png)

## Panning the map

The panning feature enables navigation through the map.

Properties related to Panning are:

* EnablePan

## Enable and disable pan

The `EnablePan` property enables or disables the panning feature of the map. A `True` value enables the panning feature. A `False` value disables the panning feature of the map.

{% highlight html %}

        <syncfusion:SfMap ShowCoords="True" LatitudeLongitudeType="Decimal" EnablePan="True">         
            <syncfusion:SfMap.Layers>
                <syncfusion:ShapeFileLayer   Uri="MapApp.world1.shp">                    
                </syncfusion:ShapeFileLayer>
            </syncfusion:SfMap.Layers>
        </syncfusion:SfMap >

{% endhighlight %}

## Ways to pan the map

There are two methods for panning the map. They are:

* Through the Pan method.
* By dragging the map.

## Through the Pan method

The map can be panned with the Pan method in the Maps control. The Pan method has two parameters: x and y.  The map is translated with respect to the x and y parameters.

{% highlight c# %}
   
           SfMap syncMap = new SfMap();
           syncMap.EnablePan = true;
           ShapeFileLayer layer = new ShapeFileLayer();
           layer.Uri = "App2.world1.shp";
           syncMap.Layers.Add(layer);
           syncMap.Pan(200, 200);

{% endhighlight  %}

## Dragging the map

The map can be panned by dragging the map through mouse interactions. This works automatically for touch events.

N>  The map can be panned only when some parts of the map are outside the view of the control.

![](Features_images/Features_img8.png)
