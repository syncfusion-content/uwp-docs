---
layout: post
title: Working with ink annotations in UWP Pdf Viewer | Syncfusion
description: Learn here all about Working with ink annotations support in Syncfusion<sup>®</sup> UWP Pdf Viewer (SfPdfViewer) control and more.
platform: uwp
control: PDF viewer
documentation: ug
---

# Working with ink annotations in UWP PDF Viewer (SfPdfViewer)

PDF Viewer allows you to include ink annotations in a PDF document and provides options to modify or remove the existing ink annotations.

## Adding ink annotations

### Enabling ink annotation mode

To enable an ink annotation, execute the `InkAnnotationCommand` with `true` as parameter.

{% tabs %}
{% highlight xaml %}

<syncfusion:SfPdfViewerControl x:Name="pdfViewer"/>
<Button x:Name="inkAnnotationButton" Click="inkAnnotationButton_Click"/>

{% endhighlight %}

{% highlight c# %}

private void inkAnnotationButton_Click(object sender, RoutedEventArgs e)
{
	pdfViewer.InkAnnotationCommand.Execute(true);
}

{% endhighlight %}
{% endtabs %}

### Disabling ink annotation mode

ink annotation can be disabled by executing the same command with `false` as parameter. 

{% tabs %}
{% highlight xaml %}

<syncfusion:SfPdfViewerControl x:Name="pdfViewer"/>
<Button x:Name="resetAnnotationButton" Click="resetAnnotationButton_Click" />

{% endhighlight %}
{% highlight c# %}

private void resetAnnotationButton_Click(object sender, RoutedEventArgs e)
{
	pdfViewer.InkAnnotationCommand.Execute(false);
}

{% endhighlight %}
{% endtabs %}

## Customizing the appearance of ink annotations

You can customize the default values of stroke color, opacity, and thickness of all ink annotations to be added. This will not affect the already added ink annotations.

### Setting the default stroke color

You can set the default stroke color of the ink annotations by using the `SfPdfViewerControl.InkAnnotationSettings.Color` property. Refer to the following code. 
 
{% highlight c# %}

SfPdfViewerControl pdfViewer = new SfPdfViewerControl();
pdfViewer.InkAnnotationSettings.Color = Color.FromArgb(255, 255, 0, 0);

{% endhighlight %}

### Setting the default opacity

You can set the default opacity of the ink annotations by using the `SfPdfViewerControl.InkAnnotationSettings.Opacity` property. Opacity value ranges from 0 to 1. Refer to the following code example.

{% highlight c# %}

SfPdfViewerControl pdfViewer = new SfPdfViewerControl();
pdfViewer.InkAnnotationSettings.Opacity = 0.5f; 

{% endhighlight %}

### Setting the default thickness

You can set the thickness of the ink annotations by using the `SfPdfViewerControl.InkAnnotationSettings.Thickness` property. Refer to the following code example. 

{% highlight c# %}

SfPdfViewerControl pdfViewer = new SfPdfViewerControl();
pdfViewer.InkAnnotationSettings.Thickness = 5;

{% endhighlight %}

### Changing the properties of a selected ink

You can change the properties of a selected ink annotation or remove it by right clicking it and choosing the desired property from the displayed options.

![Customtoolbarimage](images/image2.png)

## Detecting the change in appearance properties of ink annotations

The changes made in ink annotations' properties can be detected using the `SfPdfViewerControl.InkEdited` event. The property values before and after change can be obtained using the `InkEditedEventArgs` parameter of the event's handler. 

{% highlight c# %}

SfPdfViewerControl pdfViewer = new SfPdfViewerControl();
pdfViewer.InkEdited += PdfViewer_InkEdited;

private void PdfViewer_InkEdited(object sender, InkEditedEventArgs e)
{
	//Obtain the thickness after change
	double newThickness = e.NewThickness;
	
	//Obtain the thickness before change
	double oldThickness = e.OldThickness;
	
	//Obtain the opacity after change
	double newOpacity = e.NewOpacity;
	
	//Obtain the opacity before change
	double oldOpacity = e.OldOpacity;
	
	//Obtain the color after change
	Color newColor = e.NewColor;
	
	//Obtain the color before change
	Color oldColor = e.OldColor;
	
	//Obtain the page number in which the ink is added
	int pageNumber = e.PageNumber;
}

{% endhighlight %}

## Improving the smoothness of ink annotation

By default, SfPdfViewer uses the `Windows.UI.Xaml.Controls.Canvas` to draw ink strokes. The smoothness of ink annotations can be improved further by using the `UseWindowsInkCanvas` of `InkAnnotationSettings` of the PdfViewer. This API allows the control to use `WindowsUI.UI.Xaml.Controls.InkCanvas` for drawing ink strokes, which enables the smooth drawing of ink strokes. The code snippet for improving the smoothness of ink annotation is as follows.

{% highlight c# %}

//Enable the smooth drawing of ink strokes with the use of WindowsUI.UI.Xaml.Controls.InkCanvas.
pdfViewer.InkAnnotationSettings.UseWindowsInkCanvas = true;

{% endhighlight %}

N> When `UseWindowsInkCanvas` is set to true, other annotations (except ink) cannot be selected in ink mode and the cursor will be changed to hand tool when it is hovered on any existing ink strokes.
