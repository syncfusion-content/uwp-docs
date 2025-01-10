---
layout: post
title: Free text calllout annotation in UWP PDF Viewer control | Syncfusion
description: Learn about free text callout annotation support in Syncfusion<sup>®</sup> UWP PDF Viewer (SfPdfViewer) control and more.
platform: uwp
control: SfPdfViewerControl
documentation: ug
---

# Working with free text callout annotations in UWP PDF Viewer (SfPdfViewer)

The PDF Viewer allows you to include free text callout annotations in a PDF document and provides options to modify or remove the existing free text callout annotations.

## Adding free text callout annotations

### Enabling free text callout annotation mode

To enable a free text callout annotation, execute the `FreeTextCalloutAnnotationCommand` with true as a parameter.

{% tabs %}
{% highlight xaml %}

<syncfusion:SfPdfViewerControl x:Name="pdfViewer"/>
<Button x:Name="FreeTextCalloutAnnotationButton" Click="FreeTextCalloutAnnotationButton_Click"/>

{% endhighlight %}
{% highlight c# %}

private void FreeTextCalloutAnnotationButton_Click(object sender, RoutedEventArgs e)
{
	pdfViewer.FreeTextCalloutAnnotationCommand.Execute(true);
}

{% endhighlight %}
{% endtabs %}

### Disabling free text callout annotation mode

The free text callout annotation can be disabled by executing the same command with false as a parameter.

{% tabs %}
{% highlight xaml %}

<syncfusion:SfPdfViewerControl x:Name="pdfViewer"/>
<Button x:Name="ResetAnnotationButton" Click="ResetAnnotationButton_Click" />

{% endhighlight %}
{% highlight c# %}

private void ResetAnnotationButton_Click(object sender, RoutedEventArgs e)
{
	pdfViewer.FreeTextCalloutAnnotationCommand.Execute(false);
}

{% endhighlight %}
{% endtabs %}

## Customizing the appearance of free text callout annotations

You can customize the default values of text color, text size, stroke color, fill color, stroke width, and opacity of all free text callout annotations to be added. This will not affect the already added free text annotations.

### Setting the default text color

You can set the default text color of the free text callout annotations by using the [`TextColor`](https://help.syncfusion.com/cr/uwp/Syncfusion.Windows.PdfViewer.PdfViewerFreeTextAnnotationSettings.html#Syncfusion_Windows_PdfViewer_PdfViewerFreeTextAnnotationSettings_TextColor) property. Refer to the following code.

{% highlight c# %}

SfPdfViewerControl pdfViewer = new SfPdfViewerControl();
pdfViewer.FreeTextCalloutAnnotationSettings.TextColor = Color.FromArgb(255, 255, 0, 0);

{% endhighlight %}

### Setting the default text size

You can set the default text size of the free text callout annotations by using the [`TextSize`](https://help.syncfusion.com/cr/uwp/Syncfusion.Windows.PdfViewer.PdfViewerFreeTextAnnotationSettings.html#Syncfusion_Windows_PdfViewer_PdfViewerFreeTextAnnotationSettings_TextSize) property. Refer to the following code.

{% highlight c# %}

SfPdfViewerControl pdfViewer = new SfPdfViewerControl();
pdfViewer.FreeTextCalloutAnnotationSettings.TextSize = 10;

{% endhighlight %}

### Setting the default fill color

You can set the default fill background color of the free text callout annotations by using the [`FillColor`](https://help.syncfusion.com/cr/uwp/Syncfusion.Windows.PdfViewer.PdfViewerFreeTextCalloutAnnotationSettings.html#Syncfusion_Windows_PdfViewer_PdfViewerFreeTextCalloutAnnotationSettings_FillColor) property. Refer to the following code.

{% highlight c# %}

SfPdfViewerControl pdfViewer = new SfPdfViewerControl();
pdfViewer.FreeTextAnnotationCalloutSettings.FillColor= Color.FromArgb(255, 255, 0, 0);

{% endhighlight %}

### Setting the default border stroke color

You can set the default border stroke color of the free text callout annotations by using the [`StrokeColor`](https://help.syncfusion.com/cr/uwp/Syncfusion.Windows.PdfViewer.PdfViewerFreeTextCalloutAnnotationSettings.html#Syncfusion_Windows_PdfViewer_PdfViewerFreeTextCalloutAnnotationSettings_StrokeColor) property. Refer to the following code.

{% highlight c# %}

SfPdfViewerControl pdfViewer = new SfPdfViewerControl();
pdfViewer.FreeTextCalloutAnnotationSettings.StrokeColor = Color.FromArgb(255, 255, 0, 0);

{% endhighlight %}

### Setting the default border stroke width

You can set the default border stroke width of the free text callout annotations by using the [`StrokeWidth`](https://help.syncfusion.com/cr/uwp/Syncfusion.Windows.PdfViewer.PdfViewerFreeTextAnnotationSettings.html#Syncfusion_Windows_PdfViewer_PdfViewerFreeTextAnnotationSettings_StrokeWidth) property. Refer to the following code.

{% highlight c# %}

SfPdfViewerControl pdfViewer = new SfPdfViewerControl();
pdfViewer.FreeTextCalloutAnnotationSettings.StrokeWidth = 2;

{% endhighlight %}

### Setting the default opacity

You can set the default opacity of free text callout annotations by using the [`Opacity`](https://help.syncfusion.com/cr/uwp/Syncfusion.Windows.PdfViewer.PdfViewerFreeTextCalloutAnnotationSettings.html#Syncfusion_Windows_PdfViewer_PdfViewerFreeTextCalloutAnnotationSettings_Opacity) property. Opacity value ranges from 0 to 1. Refer to the following code example.

{% highlight c# %}

SfPdfViewerControl pdfViewer = new SfPdfViewerControl();
pdfViewer.FreeTextCalloutAnnotationSettings.Opacity = 0.5f;

{% endhighlight %}

### Setting the default minimum width and minimum size

By using the [`MinWidth`](https://help.syncfusion.com/cr/uwp/Syncfusion.Windows.PdfViewer.PdfViewerFreeTextCalloutAnnotationSettings.html#Syncfusion_Windows_PdfViewer_PdfViewerFreeTextCalloutAnnotationSettings_MinWidth) and [`MinHeight`](https://help.syncfusion.com/cr/uwp/Syncfusion.Windows.PdfViewer.PdfViewerFreeTextCalloutAnnotationSettings.html#Syncfusion_Windows_PdfViewer_PdfViewerFreeTextCalloutAnnotationSettings_MinHeight) properties, you can set the minimum width and height of the free text callout annotation for resizing.

{% highlight c# %}

SfPdfViewerControl pdfViewer = new SfPdfViewerControl();
pdfViewer.FreeTextCalloutAnnotationSettings.MinWidth= 100;
pdfViewer.FreeTextCalloutAnnotationSettings.MinHeight= 100;

{% endhighlight %}

### Enable a free text input box with automatic resizing

By using the [`AutoSizeFreeTextInputBox`](https://help.syncfusion.com/cr/uwp/Syncfusion.Windows.PdfViewer.PdfViewerFreeTextCalloutAnnotationSettings.html#Syncfusion_Windows_PdfViewer_PdfViewerFreeTextCalloutAnnotationSettings_AutoSizeFreeTextInputBox) property, you can enable or disable the automatic resizing of the free text input box.

{% highlight c# %}

SfPdfViewerControl pdfViewer = new SfPdfViewerControl();
pdfViewer.FreeTextCalloutAnnotationSettings.AutoSizeFreeTextInputBox= true;

{% endhighlight %}

### Setting the default callout line segment count

You can set the default callout line segment count of the free text callout annotations by using the [`CalloutLineSegmentCount`](https://help.syncfusion.com/cr/uwp/Syncfusion.Windows.PdfViewer.PdfViewerFreeTextCalloutAnnotationSettings.html#Syncfusion_Windows_PdfViewer_PdfViewerFreeTextCalloutAnnotationSettings_CalloutLineSegmentCount) property. By default, the free text callout annotation is added with two line segments.

{% highlight c# %}

SfPdfViewerControl pdfViewer = new SfPdfViewerControl();
pdfViewer.FreeTextCalloutAnnotationSettings.CalloutLineSegmentCount = CalloutLineSegmentCount.One;

{% endhighlight %}

### Changing the properties of a selected free text callout

You can change the properties of a selected free text callout annotation or remove it by right clicking it and choosing the desired property from the displayed options.
 
 ![customtoolbarimage](images/image7.png)

## Detecting the movement of free text callout annotations

The movement made in a free text callout annotations can be detected using the `FreeTextCalloutAnnotationMoved` event. The property values before and after the change can be obtained using the [`FreeTextCalloutAnnotationMovedEventArgs`](https://help.syncfusion.com/cr/uwp/Syncfusion.Windows.PdfViewer.FreeTextCalloutAnnotationMovedEventArgs.html) parameter of the event’s handler.

{% highlight c# %}

SfPdfViewerControl pdfViewer = new SfPdfViewerControl();
pdfViewer.FreeTextCalloutAnnotationMoved += PdfViewer_FreeTextCalloutAnnotationMoved;

private void PdfViewer_FreeTextCalloutAnnotationMoved (object sender, FreeTextCalloutAnnotationMovedEventArgs e)
{
         //Obtain the new bounds of entire annotation after change
	Rect newBounds =  e.NewBounds;
	// Obtain the old bounds of entire annotation after change
	Rect oldBounds = e.OldBounds;
	// Obtain the new bounds of callout text after change
	Rect newCalloutBounds = e.NewCalloutBounds;
 	// Obtain the old bounds of callout text after change
	Rect oldCalloutBounds = e.OldCalloutBounds;
}

{% endhighlight %}

## Detecting the resize of free text callout annotations

The resizing of the free text callout annotations can be detected using the `FreeTextCalloutAnnotationResized` event. The property values before and after the change can be obtained using the [`FreeTextCalloutAnnotationResizedEventArgs`](https://help.syncfusion.com/cr/uwp/Syncfusion.Windows.PdfViewer.FreeTextCalloutAnnotationResizedEventArgs.html) parameter of the event’s handler.

{% highlight c# %}

SfPdfViewerControl pdfViewer = new SfPdfViewerControl();
pdfViewer.FreeTextCalloutAnnotationResized += PdfViewer_FreeTextCalloutAnnotationResized;

private void PdfViewer_FreeTextCalloutAnnotationResized (object sender, FreeTextCalloutAnnotationResizedEventArgs e)
{
         //Obtain the new bounds of entire annotation after change
	Rect newBounds =  e.NewBounds;
	// Obtain the old bounds of entire annotation after change
	Rect oldBounds = e.OldBounds;
	// Obtain the new bounds of callout text after change
	Rect newCalloutBounds = e.NewCalloutBounds;
	// Obtain the old bounds of callout text after change
	Rect oldCalloutBounds = e.OldCalloutBounds;
}

{% endhighlight %}
