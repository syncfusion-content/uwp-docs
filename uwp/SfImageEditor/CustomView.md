---
layout : post
title : Custom view of Syncfusion SfImageEditor control in Universal windows
description : Learn how to add custom view in ImageEditor.
platform : uwp
control : ImageEditor
documentation : ug
---

# CustomView

You can add any custom shapes or views on the image by using the `AddCustomView` method in the SfImageEditor control. To add the custom view, specify any view and its desired `CustomViewSettings` as shown in the following code snippet.

{% highlight C# %}

Image customImage = new Image() { Height = 200, Width = 200 };
BitmapImage bitmapImage = new BitmapImage()
{
  UriSource = new Uri(BaseUri, "Images/SampleImage.png")
};
customImage.Source = bitmapImage;
imageEditor.AddCustomView(customImage, new CustomViewSettings());
  
{% endhighlight %}

## CustomViewSettings

CustomViewSettings is defined to set the values for `CanMaintainAspectRatio` and `Bounds`.
•	CanMaintainAspectRatio property is used to set the Boolean value to maintain the aspect ratio value or not when resizing the custom view.
•	Bounds property is used to set the bounds of the custom view. Using this property to position the custom view wherever you want on the image.

{% highlight C# %}

CustomViewSettings customViewSettings = new CustomViewSettings()
{
    CanMaintainAspectRatio = false,
    Bounds = new Rect(0, 0, 100, 100)
};

{% endhighlight %}

![](CustomView_Images/CustomView.png)
