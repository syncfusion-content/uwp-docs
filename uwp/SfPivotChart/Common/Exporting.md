---
layout: post
title: Exporting | SfPivotChart | UWP | Syncfusion
description: Exporting
platform: UWP
control: SfPivotChart
documentation: ug
---

# Exporting

The SfPivotChart can be exported to image, Word and PDF file formats. In-order to perform exporting operation refer the following assembly in the application.

* Syncfusion.SfPivotChartConverter.UWP

## Export to Image

By using the method of **SaveToImageAsync()**, SfPivotChart can be exported as an image with any of the following image formats.

* .bmp
* .gif
* .png
* .jpg
* .jxr
* .tiff

The following code snippet shows how to export SfPivotChart as an image.

{% tabs %}

{% highlight c# %}

PivotChart1.SaveToImageAsync();

{% endhighlight %}

{% highlight vb %}

PivotChart1.SaveToImageAsync()

{% endhighlight %}

{% endtabs %}

![](Exporting_images/relationalExportedImage.png)

## Export to Word Document

To export the SfPivotChart contents to Word, include the namespace **Syncfusion.UI.Xaml.PivotChartConverter** in the code-behind file. Then create an instance of `ExportPivotChartToWord` object to access the `ExportToDocument` method. `FileSavePicker` option can be used to save the exported file in the preferred location.

Please refer the below code snippet to export the SfPivotChart to Word document.

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

![](Exporting_images/relationalExportedWord.png)

## Export to PDF Document

To export the SfPivotChart contents to PDF, include the namespace **Syncfusion.UI.Xaml.PivotChartConverter** in the code-behind file. Then create an instance of `ExportPivotChartToPdf` object to access the `ExportToDocument` method. `FileSavePicker` option can be used to save the exported file in the preferred location.

Please refer the below code snippet to export the SfPivotChart to Pdf document.

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

![](Exporting_images/relationalExportedPDF.png)

N> You can use a *Button* instance to the page and then specify the required code snippet for exporting the SfPivotChart in the `Click` event handler method.