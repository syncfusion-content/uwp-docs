---
layout: post
title: Disable undo and redo in UWP PDF viewer | Syncfusion
description: Learn here about the support to enable and disable the undo and redo operations in UWP PDF viewer control.
platform: uwp
control: PDF viewer
documentation: ug
---

# Support to disable the undo and redo operations

When the PDF is modified by such as adding or editing annotations, these actions can be undone using the `UndoCommand` or the Ctrl + Z keyboard short cut. Likewise, the changes can be redone using the `RedoCommand` or the Ctrl + Y keyboard short cut. The undo operation using both command and keyboard short cut can be enabled or disabled using the IsUndoEnabled property. 

{% tabs %}
{% highlight c# %}

PdfViewer.IsUndoEnabled = false;

{% endhighlight %}
{% endtabs %}
     
N>Redo can be performed only if undo is enabled. So, enabling or disabling undo, effectively enables and disables redo as well.
