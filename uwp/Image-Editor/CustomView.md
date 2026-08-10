---
layout: post
title: Custom View in UWP Image Editor control | Syncfusion
description: Learn here all about Custom View support in Syncfusion UWP Image Editor (SfImageEditor) control and more.
platform: uwp
control: SfImageEditor
documentation: ug
---

# Adding custom view in UWP Image Editor (SfImageEditor)

You can add any custom shape or view to an image using the [`AddCustomView`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.ImageEditor.SfImageEditor.html#Syncfusion_UI_Xaml_ImageEditor_SfImageEditor_AddCustomView_Windows_UI_Xaml_FrameworkElement_Syncfusion_UI_Xaml_ImageEditor_CustomViewSettings_) method. To add a custom view, specify the view and its desired `CustomViewSettings` as demonstrated in the following code snippet.

{% tabs %}

{% highlight C# %}

Image customImage = new Image() { Height = 100, Width = 100 };
customImage.Source = new BitmapImage(new Uri("ms-appx:///customImage.png"));
imageEditor.AddCustomView(customImage, new CustomViewSettings());

{% endhighlight %}

{% endtabs %}

N> If the SfImageEditor is loaded in a view without an image, call the [`AddCustomView`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.ImageEditor.SfImageEditor.html#Syncfusion_UI_Xaml_ImageEditor_SfImageEditor_AddCustomView_Windows_UI_Xaml_FrameworkElement_Syncfusion_UI_Xaml_ImageEditor_CustomViewSettings_) method after a time delay. If the SfImageEditor is loaded in a view with an image, call the [`AddCustomView`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.ImageEditor.SfImageEditor.html#Syncfusion_UI_Xaml_ImageEditor_SfImageEditor_AddCustomView_Windows_UI_Xaml_FrameworkElement_Syncfusion_UI_Xaml_ImageEditor_CustomViewSettings_) method in the [`ImageLoaded`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.ImageEditor.SfImageEditor.html#Syncfusion_UI_Xaml_ImageEditor_SfImageEditor_ImageLoaded) event as shown in the following code sample.

{% tabs %}

{% highlight C# %}

imageEditor.ImageLoaded += (Object sender, ImageLoadedEventArgs args) =>
{
    Image customImage = new Image() { Height = 100, Width = 100 };
    customImage.Source = new BitmapImage(new Uri("ms-appx:///customImage.png"));
    imageEditor.AddCustomView(customImage, new CustomViewSettings());
};

{% endhighlight %}

{% endtabs %}

## Custom view settings

`CustomViewSettings` defines values for the `CanMaintainAspectRatio`, `Bounds`, `Angle`, and `EnableDrag` properties.

* `CanMaintainAspectRatio` decides whether the aspect ratio is maintained when resizing the custom view.

* `Bounds` sets the boundaries of the custom view. You can position the custom view anywhere on the image. In percentage, the values should fall between 0 and 100.

* `Angle` sets the angle for the custom view. You can rotate the custom view to the desired angle.

* [`EnableDrag`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.ImageEditor.CustomViewSettings.html#Syncfusion_UI_Xaml_ImageEditor_CustomViewSettings_EnableDrag) controls the dragging of the selected view over the image.

{% tabs %}

{% highlight C# %}

CustomViewSettings customViewSettings = new CustomViewSettings()
{
    CanMaintainAspectRatio = false,
    Bounds = new Rect(30, 30, 30, 30)
};

{% endhighlight %}

{% endtabs %}

![Custom view settings in UWP ImageEditor](CustomView_Images/CustomView_Settings.png)

## Custom view rotation

You can rotate and resize the custom view by enabling the `RotatableElements` property of the image editor. `ImageEditorElements` is an enum type with values `Text`, `CustomView`, and `None` as demonstrated in the following code snippet.

{% tabs %}

{% highlight C# %}

imageEditor.RotatableElements = Syncfusion.UI.Xaml.ImageEditor.Enums.ImageEditorElements.CustomView;

{% endhighlight %}

{% endtabs %}

N> The default value for `RotatableElements` is `None`.

You can rotate the custom view to a specific angle using the `Angle` property in `CustomViewSettings` as demonstrated in the following code snippet.

{% tabs %}

{% highlight C# %}

imageEditor.AddCustomView(customImage, new CustomViewSettings() { Angle = 45 });

{% endhighlight %}

{% endtabs %}

![Rotating and resizing the custom view in UWP ImageEditor](CustomView_Images/CustomView_Rotation.png)

## Restricting the custom view resize

You can restrict custom view resizing using the [`IsResizable`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.ImageEditor.CustomViewSettings.html#Syncfusion_UI_Xaml_ImageEditor_CustomViewSettings_IsResizable) property. By default, the value of `IsResizable` is `true`, so you can resize the custom view added on an image. When the [`IsResizable`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.ImageEditor.CustomViewSettings.html#Syncfusion_UI_Xaml_ImageEditor_CustomViewSettings_IsResizable) property is disabled, the custom view added on an image cannot be resized and you can only drag the custom view over an image as shown in the following code sample.

{% tabs %}

{% highlight C# %}

Image customImage = new Image() { Height = 100, Width = 100 };
customImage.Source = new BitmapImage(new Uri("ms-appx:///customImage.png"));
imageEditor.AddCustomView(customImage, new CustomViewSettings() { IsResizable = false });

{% endhighlight %}

{% endtabs %}

## See also

[How to disable resizing the shapes, text, and custom view](https://www.syncfusion.com/kb/9476/how-to-disable-resizing-the-shapes-text-and-customview)