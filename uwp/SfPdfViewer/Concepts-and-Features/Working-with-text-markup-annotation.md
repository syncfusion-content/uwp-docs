---
layout: post
title: Working with text markup annotations in Syncfusion Essential UWP PDF viewer.
description: Working with text markup annotations in Syncfusion Essential UWP PDF viewer.
platform: uwp
control: PDF viewer
documentation: ug
---

## Working with text markup annotations

PDF Viewer allows users to include text markup annotations in a PDF document and provides options to modify or remove the existing text markup annotations. The supported text markup annotations are:

1. Highlight
2. Underline
3. Strikeout

In all the code snippets that follow, only Highlight annotation is used for brevity. Other text markup annotations can be used in the same way. 

## Adding text markup annotations

### Enabling text markup annotation mode

To enable a text markup annotation, execute the annotation's corresponding command with `true` as parameter.

{% tabs %}
{% highlight xaml %}

<syncfusion:SfPdfViewerControl x:Name="pdfViewer"/>
<Button x:Name="textMarkupAnnotationButton" Click="TextMarkupAnnotationButton_Click"/>

{% endhighlight %}

{% highlight c# %}

private void TextMarkupAnnotationButton_Click(object sender, RoutedEventArgs e)
{
	pdfViewer.HighlightAnnotationCommand.Execute(true);
}

{% endhighlight %}
{% endtabs %}

### Disabling text markup annotation mode

Text markup annotation can be disabled by executing the same command with `false` as parameter. 

{% tabs %}
{% highlight xaml %}

<syncfusion:SfPdfViewerControl x:Name="pdfViewer"/>
<Button x:Name="resetAnnotationButton" Click="resetAnnotationButton_Click" />

{% endhighlight %}
{% highlight c# %}

private void resetAnnotationButton_Click(object sender, RoutedEventArgs e)
{
	pdfViewer.HighlightAnnotationCommand.Execute(false);
}

{% endhighlight %}
{% endtabs %}

## Customizing the appearance of text markup annotations

You can customize the default values of color and opacity of all text markup annotations to be added. This will not affect the already added text markup annotations.

### Setting the default color

You can set the default color of a highlight annotation by using the `SfPdfViewerControl.HighlightAnnotationSettings.Color` property. Refer to the following code. 
 
{% highlight c# %}

SfPdfViewerControl pdfViewer = new SfPdfViewerControl();
pdfViewer.HighlightAnnotationSettings.Color = Color.FromArgb(255, 255, 0, 0);

{% endhighlight %}

### Setting the default opacity

You can set the default opacity of a highlight markup annotation by using the `SfPdfViewerControl.HighlightAnnotationSettings.Opacity` property. Opacity value ranges from 0 to 1. Refer to the following code example.

{% highlight c# %}

SfPdfViewerControl pdfViewer = new SfPdfViewerControl();
pdfViewer.HighlightAnnotationSettings.Opacity = 0.5f; 

{% endhighlight %}

### Changing the properties of a selected text markup

You can change the properties of a selected text markup annotation or remove it by right clicking it and choosing the desired property from the displayed options.

![customtoolbarimage](images/image3.png)

## Detecting the change in appearance properties of text markup annotations

The changes made in text markup annotations' properties can be detected using the `SfPdfViewerControl.TextmarkupEdited` event. The property values before and after change can be obtained using the `TextmarkupEditedEventArgs` parameter of the event's handler. 

{% highlight c# %}

SfPdfViewerControl pdfViewer = new SfPdfViewerControl();
pdfViewer.TextmarkupEdited += PdfViewer_TextmarkupEdited;

private void PdfViewer_TextmarkupEdited(object sender, TextmarkupEditedEventArgs e)
{
	//Obtain the opacity after change
	double newOpacity = e.NewOpacity;
	
	//Obtain the opacity before change
	double oldOpacity = e.OldOpacity;
	
	//Obtain the color after change
	Color newColor = e.NewColor;
	
	//Obtain the color before change
	Color oldColor = e.OldColor;
	
	//Obtain the page number in which the text markup is added
	int pageNumber = e.PageNumber;
}

{% endhighlight %}