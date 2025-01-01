---
layout: post
title: Exporting in UWP Charts control | Syncfusion
description: Learn everything about Exporting support in Syncfusion® UWP Charts (SfChart) control and explore additional features.
platform: uwp
control: SfChart
documentation: ug
---
# Exporting in UWP Charts (SfChart)

[`SfChart`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.SfChart.html) can be exported into the following types of image formats:

* JPG or JPEG
* JPEG-XR
* GIF
* TIFF
* PNG
* BMP

The following example illustrates exporting of the chart.

![Chart For Printing](Exporting_images/Exporting.png)

## Methods

[`SfChart`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.SfChart.html) contains the following overloading methods for saving a chart as an image.

### Save()

This method will export the chart as image into a desired location by using FileSavePicker.

{% highlight c# %}

private void SaveImageButton_Click(object sender, RoutedEventArgs e)
{
    this.SampleChart.Save();
}

{% endhighlight %}

### Save(string fileName, StorageFolder folderLocation)

This method will export the chart as image to the specified location. The following code example illustrates the usage of this method.

{% highlight c# %}

private void SaveImageLocation_Click(object sender, RoutedEventArgs e)
{
    StorageFolder storageFolder = Windows.Storage.KnownFolders.PicturesLibrary;
    this.SampleChart.Save("ChartImage", storageFolder);
}

{% endhighlight %}

If you did not specify any location, the image will be saved to the corresponding application’s bin\x86\Debug\AppX

{% highlight c# %}

Chart.Save("Chart", null);

{% endhighlight %}

### Save(IRandomAccessStream stream, Guid bitmapEncoderID)

This method allows you to export the chart into a stream. It is described in following code example.

{% highlight c# %}

private async void SaveImageEncoder_Click(object sender, RoutedEventArgs e)
{
    StorageFile storageFile = await Windows.Storage.KnownFolders.PicturesLibrary.CreateFileAsync("EncodedChartImage");
    Guid encoder = BitmapEncoder.BmpEncoderId;
    this.SampleChart.Save(await storageFile.OpenAsync(FileAccessMode.ReadWrite), encoder);
}

{% endhighlight %}

The following screenshot represents the exported image.

![Chart Printed](Exporting_images/Exported.PNG)
