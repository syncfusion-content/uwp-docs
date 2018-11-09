---
layout: post
title:  Bookmark Navigation
description: Bookmark Navigation
platform: UWP
control: SfPdfViewerControl
documentation: ug
---

# Working with Bookmark Navigation

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