---
layout: post
title: Crop | SfImageEditor | uwp | Syncfusion
description: This section explains how to crop an image in different ways in the SfImageEditor control for UWP platform
platform: uwp
control: SfImageEditor
documentation: ug
---
# Crop in SfImageEditor

The image editor control gives you an option to crop the image as desired. Cropping the image can be done in following two ways:

* From Toolbar
* Cropping programmatically

### From Toolbar

To enable cropping, in the `Transforms` submenu, click the `Crop` icon. When the `Crop` icon is tapped, a sub toolbar will appear on top of that toolbar. While the cropping is enabled, the crop sub toolbar, `Cancel` and `OK` buttons will be available. From that sub toolbar, you can able to crop the image with the following aspect ratios.

* `Free`- crop the image to any desired size.
* `Original`-crop the image based on image width and height. 
* `Square`-crop the image based on equal width and height.
* Crop the image to specific aspect ratio such as `3:1, 1:3, 3:2, 2:3, 4:3, 3:4, 5:4, 4:5, 16:9, 9:16`. On double tapping the aspect ratio icon reversed ratio will shown. 

To disable cropping,click the `Cancel` button. To save the cropped area, after selected the desired area, Click the `OK` button, the toolbars will reappear after the cropping operation is completed.

### Cropping programmatically

Cropping operation can be done programmatically in following two ways:

* Enable Cropping and Select the Crop region visually.
* Manually set the cropping area.

#### Handling the cropping tool

The `ToggleCropping` method in the SfImageEditor control is used to enable and disable a cropping region placed over the image to visually choose the area for cropping. 

*	To crop the image to any desired size.

{% tabs %}

{% highlight C# %}

//  for free hand cropping

imageEditor.ToggleCropping();    

{% endhighlight %}

{% endtabs %}

* To crop an image based on original width and height of the image.

{% tabs %}

{% highlight C# %}

// for cropping the image with original width and height of the image.

imageEditor.ToggleCropping(float.NaN,float.NaN);    

{% endhighlight %}

{% endtabs %}

* To crop an image as square dimension.

{% tabs %}

{% highlight C# %}

// for cropping the image in square format.

imageEditor.ToggleCropping(1, 1);    

{% endhighlight %}

{% endtabs %}

* To crop an image based on specific ratio.

{% tabs %}

{% highlight C# %}

// for cropping the image with ratio x value as 9 and y value as 17

imageEditor.ToggleCropping(9,17);    

{% endhighlight %}

{% endtabs %}

* To position the cropping window with custom location, pass the desired rectangle in ToggleCropping method. Each value in the rectangle should be in offset value(0 to 100).

{% tabs %}

{% highlight C# %}

Rect rect = new Rect(20,20,50,50);

editor.ToggleCropping(rect);    

{% endhighlight %}

{% endtabs %} 

![crop window output image in SfImageEditor](crop_images/cropaspectUWP.JPG)

After the cropping area has been selected, the `Crop` method is called which in turn crops the selected region and displays the cropped image on the ImageEditor.

{% tabs %}

{% highlight C# %}

// After selecting the crop area visually

imageEditor.Crop(new Rect(0, 0, 0, 0));

{% endhighlight %}

{% endtabs %}

## Manually set the cropping area

To manually set the cropping rectangle without even enabling the cropping functionality, use overloaded Crop(Rectangle rect) method. This can be done by defining a rectangle and pass it to Crop(rect) method.


{% highlight C# %}

    imageEditor.Crop(new Rect(200, 150, 150, 150));

{% endhighlight %}
