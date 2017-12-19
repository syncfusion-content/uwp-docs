---
layout: post
title: Exporting | SfChart | uwp | Syncfusion
description: Exporting
platform: uwp
control: SfChart
documentation: ug
---
# Exporting

Chart can be exported into the following types of image formats:

* JPG or JPEG
* JPEG-XR
* GIF
* TIFF
* PNG
* BMP

## Methods

Chart contains the following overloading methods for saving a chart as an image.

### Save()

This method will export the chart as image into a desired location by using FileSavePicker.

{% highlight c# %}

Chart.Save();

{% endhighlight %}

### Save(string fileName, StorageFolder folderLocation)

This method will export the chart as image to the specified location. The following code example illustrates the usage of this method.

{% highlight c# %}

chart.Save("a.png", Windows.Storage.KnownFolders.PicturesLibrary);

{% endhighlight %}

If you did not specify any location, the image will be saved to the corresponding application’s bin\x86\Debug\AppX

{% highlight c# %}

Chart.Save("Chart", null);

{% endhighlight %}

### Save(IRandomAccessStream stream, Guid bitmapEncoderID)

This method allows you to export the chart into a stream. It is described in following code example.

{% highlight c# %}

Guid id = BitmapEncoder.GifEncoderId;

StorageFolder storageFolder = ApplicationData.Current.LocalFolder;

StorageFile sampleFile = await storageFolder.CreateFileAsync("Chart.png", CreationCollisionOption.ReplaceExisting);

Stream x = await sampleFile.OpenStreamForWriteAsync();

Chart.Save(x.AsRandomAccessStream(), id);

{% endhighlight %}






