---
layout: post
title: Getting Started with UWP Image Editor control | Syncfusion
description: Learn here about getting started with Syncfusion UWP Image Editor (SfImageEditor) control, its elements and more.
platform: uwp
control: SfImageEditor
documentation: ug
---
# Getting Started with UWP Image Editor (SfImageEditor)

This section explains the steps required to load an image to the image editor. Image editor has a built-in toolbar that has options to edit the image with shapes, path, text, crop, rotate and flip.

## Configuring SfImageEditor

After installing Essential Studio for UWP, you can find all the required assemblies in the installation folder,

**SfImageEditor** is available in the following assembly and namespace:

**Assembly**: Syncfusion.SfImageEditor.UWP

**Namespace**: Syncfusion.UI.Xaml.ImageEditor

N> In addition, you have to install a [`Win2D`](https://www.nuget.org/packages/Win2D.uwp) package to save the image.

## Initialize the image editor

* Import the SfImageEditor namespace as shown below,

{% capture codesnippet1 %}

{% tabs %}

{% highlight XAML %}

    xmlns:syncfusion="using:Syncfusion.UI.Xaml.ImageEditor"
    
{% endhighlight %}

{% highlight C# %}

    using Syncfusion.UI.Xaml.ImageEditor;
    
{% endhighlight %}

{% endtabs %}

{% endcapture %}

{{ codesnippet1 | UnOrderList_Indent_Level_1 }} 

* Initialize the image editor as shown below,

{% capture codesnippet2 %}

{% tabs %}

{% highlight XAML %}

    <syncfusion:SfImageEditor/>
    
{% endhighlight %}

{% highlight C# %}

    SfImageEditor editor = new SfImageEditor();
    grid.Children.Add(editor);
    
{% endhighlight %}

{% endtabs %}

{% endcapture %}

{{ codesnippet2 | UnOrderList_Indent_Level_1 }} 

## Loading an image to the image editor

It can be done by the following two ways:

* Using bitmap object
* Using Stream

### Using bitmap object

You can load an image to the control as a bitmap object.

{% highlight C# %}

     IRandomAccessStream stream = await file.OpenAsync(FileAccessMode.Read);
     BitmapImage bitMapImage = new BitmapImage();
     image.SetSource(stream);
     imageEditor.ImageSource = bitMapImage;
    
{% endhighlight %}

### Using Stream

You can load an image to the control as a stream.

{% highlight C# %}

    IRandomAccessStream stream = await file.OpenAsync(FileAccessMode.Read);
    imageEditor.Image = stream;

{% endhighlight %}

* After an image has been loaded to the SfImageEditor, you can start to edit an image by using the built-in Toolbar

![Output image of the SfImageEditor getting started](getting-started_images/LoadedImage.png)

## See also

[How to enable access permission in uwp application](https://support.syncfusion.com/kb/article/7751/how-to-enable-access-permission-in-uwp-application)