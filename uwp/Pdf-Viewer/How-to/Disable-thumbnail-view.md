---
layout: post
title: Disable thumbnail view in Syncfusion Essential UWP PDF viewer.
description: Learn here about Disable thumbnail view support in UWP PDF viewer control and how to enable or disable thumbnail view, and more.
platform: uwp
control: PDF viewer
documentation: ug
---

# Disable thumbnail view in UWP PDF Viewer
The SfPdfViewer control allows you to enable and disable thumbnail view that is opened when the document is magnified below 100%. The following code illustrates the same.
{% tabs %}
{% highlight c# %}
pdfViewer.IsThumbnailViewEnabled = false;
{% endhighlight %}
{% highlight vbnet %}
pdfViewer.IsThumbnailViewEnabled = False
{% endhighlight %}
{% endtabs %}
