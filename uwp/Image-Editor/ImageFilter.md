---
layout: post
title: ImageFilter in Syncfusion SfImageEditor control in UWP
description: This section describes how to apply image filter support in SfImageEditor control for UWP platform and also about image effects toolbar
platform: UWP
control: ImageEditor
documentation: ug
---

# Image Filter in SfImageEditor

By using the SfImageEditor control, you can add effects such as Hue, Saturation, Brightness, Contrast, Blur, and Sharpen to the image. These effects can be applied from toolbar or using the ApplyImageEffect method. The [`ApplyImageEffect`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.ImageEditor.SfImageEditor.html#Syncfusion_UI_Xaml_ImageEditor_SfImageEditor_ApplyImageEffect_Syncfusion_UI_Xaml_ImageEditor_Enums_ImageEffect_System_Single_) method contains two arguments: [`ImageEffect`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.ImageEditor.SfImageEditor.html#Syncfusion_UI_Xaml_ImageEditor_SfImageEditor_ImageEffect) and [`EffectValue`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.ImageEditor.SfImageEditor.html#Syncfusion_UI_Xaml_ImageEditor_SfImageEditor_EffectValue). The ImageEffect is an Enum, which contains the following effects:

* Hue
* Saturation
* Brightness
* Contrast
* Blur
* Sharpen 
* None

The EffectValue is the corresponding ImageEffect values, which varies for each effect, and they are explained as follows.

## Hue

The hue represents the dominant wavelength of the color. The value of hue effect ranges from -180 to 180.

{% highlight C# %}

public MainPage()
{               
    . . .
    imageEditor.ApplyImageEffect(ImageEffect.Hue, 120);
    . . .
}

{% endhighlight %}

![SfImageEditor hue image effects](ImageFilter_Images/Hue.png)

## Saturation

The saturation represents the intensity of the color. The value of the saturation effect ranges from -100 to 100.

{% highlight C# %}

public MainPage()
{               
    . . .
    imageEditor.ApplyImageEffect(ImageEffect.Saturation, -80);
    . . .
}

{% endhighlight %}

![SfImageEditor saturation image effects](ImageFilter_Images/Saturation.png)

## Brightness

The brightness represents how bright the color is. The value of brightness effect ranges from -100 to 100.

{% highlight C# %}

public MainPage()
{               
    . . .
    imageEditor.ApplyImageEffect(ImageEffect.Brightness, -60);
    . . .
}

{% endhighlight %}

![SfImageEditor brightness image effects](ImageFilter_Images/Brightness.png)

## Contrast

The contrast represents the color contrast of an image. The value of contrast effect ranges from -100 to 100.

{% highlight C# %}

public MainPage()
{               
    . . .
    imageEditor.ApplyImageEffect(ImageEffect.Contrast, -30);
    . . .
}

{% endhighlight %}

![SfImageEditor contrast image effects](ImageFilter_Images/Contrast.png)

## Blur

The blur represents the clearness of the image. The value of blur effect ranges from 0 to 6.

{% highlight C# %}

public MainPage()
{               
    . . .
    imageEditor.ApplyImageEffect(ImageEffect.Blur, 4);
    . . .
}

{% endhighlight %}

![SfImageEditor blur image effects](ImageFilter_Images/Blur.png)

## Sharpen

Sharpen is used to highlight edges and fine details in an image. The value of sharpen effect ranges from 0 to 6.

{% highlight C# %}

public MainPage()
{               
    . . .
    imageEditor.ApplyImageEffect(ImageEffect.Sharpen, 2);
    . . .
}

{% endhighlight %}

![SfImageEditor sharpen image effects](ImageFilter_Images/Sharpen.png)

N> The ImageEffect enum also contains “None” option, which removes all the previously applied effects, which are not saved and displays the original image. When applying effect using the ApplyImageEffect method, the effects will be saved automatically. But, if you apply effects from the toolbar, each effect will be saved only by clicking the OK button, else all the applied effects will not be saved.

![SfImageEditor image effect image](ImageFilter_Images/ImageFilter.png)