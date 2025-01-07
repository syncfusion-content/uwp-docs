---
layout: post
title: Exporting in UWP Pivot Chart control | Syncfusion
description: Learn here all about Exporting support in Syncfusion® UWP Pivot Chart (SfPivotChart) control and more.
platform: UWP
control: SfPivotChart
documentation: ug
---

# Exporting in UWP Pivot Chart (SfPivotChart)

The SfPivotChart can be exported to an image, Microsoft Word, and PDF file formats. To perform exporting operation, refer to the following assembly in the application:

* Syncfusion.SfPivotChartConverter.UWP

## Export to image

By using the **SaveToImageAsync()** method, the SfPivotChart can be exported to an image with any of the following image formats:

* .bmp
* .gif
* .png
* .jpg
* .jxr
* .tiff

The following code snippet shows how to export SfPivotChart to an image.

{% tabs %}

{% highlight c# %}

PivotChart1.SaveToImageAsync();

{% endhighlight %}

{% highlight vb %}

PivotChart1.SaveToImageAsync()

{% endhighlight %}

{% endtabs %}

![relationalExportedImage](Exporting_images/relationalExportedImage.png)

## Export to Word document

To export the SfPivotChart contents to Word, include the namespace **Syncfusion.UI.Xaml.PivotChartConverter** in the code-behind file. Then, create an instance of `ExportPivotChartToWord` object to access the `ExportToDocument` method. `FileSavePicker` can be used to save the exported file in the preferred location.

Refer to the following code snippet to export the SfPivotChart to Word document.

{% tabs %}
  
{% highlight c# %}

FileSavePicker savePicker = new FileSavePicker();
savePicker.SuggestedFileName = "Sample";
ExportPivotChartToWord export = new ExportPivotChartToWord(this.PivotChart1);
export.ExportToDocument("Sample");

{% endhighlight %}

{% highlight vb %}

Dim savePicker As New FileSavePicker()
savePicker.SuggestedFileName = "Sample"
Dim export As New ExportPivotChartToWord(Me.PivotChart1)
export.ExportToDocument("Sample")

{% endhighlight %}

{% endtabs %}

![relationalExportedWord](Exporting_images/relationalExportedWord.png)

## Export to PDF document

To export the SfPivotChart contents to PDF, include the namespace **Syncfusion.UI.Xaml.PivotChartConverter** in the code-behind file. Then, create an instance of `ExportPivotChartToPdf` object to access the `ExportToDocument` method. The `FileSavePicker` can be used to save the exported file in the preferred location.

Refer to the following code snippet to export the SfPivotChart to PDF document.

{% tabs %}

{% highlight c# %}

FileSavePicker savePicker = new FileSavePicker();
savePicker.SuggestedFileName = "Sample";
ExportPivotChartToPdf export = new ExportPivotChartToPdf(this.PivotChart1);
export.ExportToDocument("Sample");

{% endhighlight %}

{% highlight vb %}

Dim savePicker As New FileSavePicker()
savePicker.SuggestedFileName = "Sample"
Dim export As New ExportPivotChartToPdf(Me.PivotChart1)
export.ExportToDocument("Sample")

{% endhighlight %}

{% endtabs %}

![relationalExportedPDF](Exporting_images/relationalExportedPDF.png)

N> You can use a *Button* instance to the page and specify the required code snippet for exporting the SfPivotChart in the `Click` event handler method.
