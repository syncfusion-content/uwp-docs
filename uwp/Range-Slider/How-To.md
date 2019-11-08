---
layout: post
title: Events in Syncfusion SfRangeSlider control for UWP
description: Learn how to populate events in SfRangeSlider control
platform: UWP
control: SfRange Slider
documentation: ug
---

## How to get notifications when a thumb drag is started and completed?

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
