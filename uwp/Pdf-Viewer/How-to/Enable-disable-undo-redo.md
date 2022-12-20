---
layout: post
title: Disable undo and redo in UWP PDF viewer | Syncfusion
description: Learn here about the support to enable and disable the undo and redo operations in UWP PDF viewer control.
platform: uwp
control: PDF viewer
documentation: ug
---

# Support to disable the undo and redo operations

The undo operation using both the `UndoCommand` and keyboard shortcut Ctrl+Z can be enabled or disabled using the `IsUndoEnabled` property. The default value of this property is true.
{% tabs %}
{% highlight c# %}

PdfViewer.IsUndoEnabled = false;

{% endhighlight %}
{% endtabs %}
     
N>Redo can be performed only if undo is enabled. So, enabling or disabling undo, effectively enables and disables redo as well.
