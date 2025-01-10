---
layout: post
title: Bookmark navigation in UWP PDF Viewer control | Syncfusion
description: Learn here all about Bookmark navigation support in Syncfusion<sup>®</sup> UWP PDF Viewer (SfPdfViewer) control and more.
platform: uwp
control: SfPdfViewerControl
documentation: ug
---

# Bookmark navigation in UWP PDF Viewer (SfPdfViewer)

PDF Viewer allows users to navigate to the bookmarks present in the loaded PDF document. 

## Programmatically navigate to a bookmark destination

You can navigate to a desired bookmark destination using the `GotoBookmark(PdfBookmark)` method. The target/destination bookmark should be provided as the parameter to this method. Refer to the following code sample.

{% tabs %}
{% highlight c# %}

//Create an object for PdfLoadedDocument
PdfLoadedDocument loadedDocument = new PdfLoadedDocument(documentStream);

//Retrieves the bookmark collection from the loaded PDF document
PdfBookmarkBase bookmark = loadedDocument.Bookmarks;

//Navigate to the specified bookmark destination offset
pdfViewerControl.GoToBookmark(bookmark[0]);

{% endhighlight %}
{% endtabs %}
