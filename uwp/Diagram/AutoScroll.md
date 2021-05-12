---
layout: post
title: AutoScroll in UWP Diagram control | Syncfusion
description: Learn here all about AutoScroll support in Syncfusion UWP Diagram (SfDiagram) control and more.
platform: uwp
control: SfDiagram
documentation: ug
---

# AutoScroll in UWP Diagram (SfDiagram)

Autoscroll feature automatically scrolls the Diagram whenever the Node or Connector is moved beyond the boundary of the diagram. So that, it is always visible during dragging, resizing, and multiple selection operations. Autoscroll is automatically triggered when any one of the following is done towards the edges of the Diagram.

* Node dragging, resizing
* Connection editing
* Rubber band selection
* Label dragging

## Autoscroll border

The Autoscroll border is used to specify the maximum distance between the object and Diagram edge to trigger Autoscroll. The default value is set as 20 for all sides (left, right, top, and bottom) and it can be changed by using the `AutoScrollBorder` property of ScrollSettings. The following code example illustrates how to set Autoscroll border.

{% highlight C# %}

//Specifies AutoScroll Border
diagram.ScrollSettings.AutoScrollBorder = new Thickness(150, 15, 15, 15);

{% endhighlight %}

## Scroll limit

The scroll limit allows you to define the scrollable region of the Diagram. It includes the following options.

* Allows to scroll in all directions without any restriction.
* Allows to scroll within the Diagram content.
* Allows to scroll within the specified scrollable area.

`ScrollLimit` property of ScrollSettings helps to limit the scrolling.

The following code example illustrates how to specify the scroll limit.

{% highlight C# %}

//Sets the ScrollLimit
diagram.ScrollSettings.ScrollLimit = ScrollLimit.Infinity;

{% endhighlight %}

## Scrollable Area

You can restrict scrolling beyond any particular rectangle area by using the `ScrollableArea` property of ScrollSettings. To restrict scrolling beyond any custom region, you have to set the `ScrollLimit` as “limited”. The following code example illustrated how to customize scrollable area.

{% highlight C# %}

//Sets ScrollLimit as limited
diagram.ScrollSettings.ScrollLimit = ScrollLimit.Limited;

//Sets the limited ScrollableArea
diagram.ScrollSettings.ScrollableArea = new Rect(0, 0, 500, 500);

{% endhighlight %}
