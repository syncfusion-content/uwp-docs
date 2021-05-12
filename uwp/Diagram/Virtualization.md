---
layout: post
title: Virtualization in UWP Diagram control | Syncfusion
description: Learn here all about Virtualization support in Syncfusion UWP Diagram (SfDiagram) control and more.
platform: uwp
control: SfDiagram
documentation: ug
---

# Virtualization in UWP Diagram (SfDiagram)

Virtualization is the process of loading the diagramming objects available in the visible area of the Diagram control, that is, only the diagramming objects that lie within the ViewPort of the ScrollViewer are loaded (remaining objects are loaded only when they come into view).

This feature gives optimized performance while loading and dragging items to the SfDiagram that consists of many Nodes and Line Connectors.

The following code example illustrates how to enable Virtualization in SfDiagram

{% highlight C# %}

sfdiagram.Constraints = sfdiagram.Constraints | GraphConstraints.Virtualize;

{% endhighlight %}
