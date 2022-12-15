---
layout: post
title: Get the selected text in UWP PDF viewer | Syncfusion
description: Learn here about the support to get the selected text in UWP PDF viewer control.
platform: uwp
control: PDF viewer
documentation: ug
---

# How to get the selected text

When text selection action is completed, the TextSelectionCompleted event will be raised. The event arguments will contain the selected text.

{% tabs %}
{% highlight c# %}

PdfViewer.TextSelectionCompleted += PdfViewer_TextSelectionCompleted;

private void PdfViewer_TextSelectionCompleted(object sender, TextSelectionCompletedEventArgs e)
{
    //Get the selected text
    string selectedText = e.SelectedText;
}

{% endhighlight %}
{% endtabs %}