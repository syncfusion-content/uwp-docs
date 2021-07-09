---
layout: post
title: Working with annotations in UWP Pdf Viewer | Syncfusion
description: Learn here all about Working with annotations support in Syncfusion UWP Pdf Viewer (SfPdfViewer) control and more.
platform: uwp
control: PDF viewer
documentation: ug
---

# Working with annotations in UWP PDF Viewer

PDF Viewer allows user to include annotations in PDF files and provides options to modify or remove the existing annotations. The supported annotations are below. 

1. Text markup annotations
2. Shape annotations
3. Ink annotations
4. Popup annotations

The individual annotation types are discussed in detail under their own sections. 

### Annotation events. 

PDF viewer provides the following events. 

1. AnnotationAdded
2. AnnotationTapped
3. AnnotationSelected
4. AnnotationDeselected
5. AnnotationRemoved
6. AnnotationMovedOrResized

The properties of the annotation involved in the event can be obtained from the `AnnotationProperties` property of the event args parameter of each event except AnnotationMovedOrResized. Since the annotation properties are obtained from the same `AnnotationProperties` instance for all events except AnnotationMovedOrResized, only the AnnotationAdded event is illustrated below. 

The properties of the included annotation can be obtained by casting the `AnnotationAddedEventArgs` parameter's AnnotationProperties property to the property of corresponding annotation type.

{% highlight c# %}

SfPdfViewerControl pdfViewer = new SfPdfViewerControl();
pdfViewer.AnnotationAdded += PdfViewer_AnnotationAdded;

private void PdfViewer_AnnotationAdded(object sender, AnnotationAddedEventArgs e)
{	
	//Check whether the annotation is text markup
	if (e.AnnotationProperties is TextMarkupProperties)
	{
		TextMarkupProperties properties = e.AnnotationProperties as TextMarkupProperties;

		//Obtain the annotation type such as Highlight, Underline, Strikethrough
		AnnotationMode annotationMode = properties.AnnotationType;

		//Obtain color of the annotation
		Color color = properties.Color;

		//Obtain the opacity value of the annotation
		double opacity = properties.Opacity;

		//Obtain the page number in which the annotation is added
		int pageNumber = properties.PageNumber;
	}
}

{% endhighlight %}

The properties of the annotation involved in the `AnnotationMovedOrResized` event can be obtained from the `AnnotationMovedOrResizedEventArgs` parameter of the event handler. 

{% highlight c# %}

SfPdfViewerControl pdfViewer = new SfPdfViewerControl();
pdfViewer.AnnotationMovedOrResized += PdfViewer_AnnotationMovedOrResized;

private void PdfViewer_AnnotationAdded(object sender, AnnotationMovedOrResizedEventArgs e)
{	
	//Obtain the new position and size
	int newX = e.NewX;
	int newY = e.NewY;
	int newHeight = e.NewHeight;
	int newWidth = e.NewWidth;

	//Obtain the old position and size
	int oldX = e.OldX;
	int oldY = e.OldY;
	int oldHeight = e.OldHeight;
	int oldWidth = e.OldWidth;

	//Obtain the page number in which the annotation is added
	int pageNumber = e.PageNumber;
}

{% endhighlight %}

### Enable and disable selection of annotations

By default, PdfViewer allows the user to select the annotations by tapping on it, this action is followed by the appearance of the selector around the selected annotation. The selection of annotations can be disabled by setting `IsReadOnly` property of `AnnotationSettings` class to true. The default value of this API will be false.

{% highlight c# %}

//Disable the selection of annotations
pdfViewer.AnnotationSettings.IsReadOnly = true;

{% endhighlight %}

### Setting the author for the annotations.
The `Author` property of the [`IAnnotation`](https://help.syncfusion.com/cr/uwp/Syncfusion.Windows.PdfViewer.IAnnotation.html) is used to set the name of the author for all supported annotations.

Refer to the following code example.

{% highlight c# %}
//Initialize the SfPdfViewer
SfPdfViewerControl pdfViewer = new SfPdfViewerControl();

pdfViewer.AnnotationAdded += PdfViewer_AnnotationAdded;
private void PdfViewer_AnnotationAdded(object sender, Syncfusion.Windows.PdfViewer.AnnotationAddedEventArgs e)
		{
			if (e.Annotation is IAnnotation)
			{
				//sets the author name for the added annotation.  
				e.Annotation.Author = "Syncfusion";
			}
		}
{% endhighlight %}


