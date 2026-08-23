---
layout: post
title: How to get thumb drag notifications in UWP Range Slider | Syncfusion®
description: Learn how to receive notifications when thumb dragging starts and completes in the Syncfusion® UWP Range Slider control using DragStarted and DragCompleted events.
platform: UWP
control: SfRange Slider
documentation: ug
---

# How to get thumb drag notifications in UWP Range Slider

The `DragStarted` event is raised when a thumb is dragged. After the thumb releases the pointer capture, the `DragCompleted` event is raised. The `Index` property of the `DragThumbEventArgs` returns a int value, which indicates the thumb used for performing drag operations.

<table>
<tr>
<th>Members</th>
<th>Description</th>
</tr>
<tr>
<td>Index</td>
<td>Indicates the thumb used for performing drag operations.
Value 0 for start thumb and 1 for end thumb.
</td>
</tr>
</table>

                                                
{% tabs %}

{% highlight c# %}

	rangeSlider.DragStarted+=(object sender, DragThumbEventArgs e) =>
	{
         //perform the operation
	};

	rangeSlider.DragCompleted+=(object sender, DragThumbEventArgs e) =>
	{
         //perform the operation
	};

{% endhighlight %}

{% endtabs %}
