---
layout: post
title: Enable and disable text selection in Syncfusion Essential UWP PDF viewer.
description: Enable and disable text selection in Syncfusion Essential UWP PDF viewer.
platform: uwp
control: PDF viewer
documentation: ug
---

## Enable and disable text selection
The text selection feature of the PDF viewer can be disabled as shown in the following code.
{% tabs %}
{% highlight c# %}
PdfLoadedDocument ldoc = new PdfLoadedDocument(buffer);
pdfViewer.LoadDocument(ldoc);
// Disables text selection.
pdfViewer.IsTextSelectionEnabled = false;
{% endhighlight %}
{% highlight vbnet %}
Dim ldoc As New PdfLoadedDocument(Buffer)
pdfViewer.LoadDocument(ldoc)
'Disables text selection.
pdfViewer.IsTextSelectionEnabled = False
{% endhighlight %}
{% endtabs %}