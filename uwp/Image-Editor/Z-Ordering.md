---
layout: post
title: Z-Ordering in UWP Image Editor control | Syncfusion
description: Learn here all about Z-Ordering support in Syncfusion UWP Image Editor (SfImageEditor) control and more.
platform: UWP
control: ImageEditor
documentation: ug
---

# Z-Ordering in UWP Image Editor (SfImageEditor)

The image editor control allows to change the position of shapes/edits that are arranged over the editor. This can be achieved using the following methods:

1. BringToFront
2. SendToBack
3. BringForward
4. SendBackward

## BringToFront

The [`BringToFront`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.ImageEditor.SfImageEditor.html#Syncfusion_UI_Xaml_ImageEditor_SfImageEditor_BringToFront) method is used to bring the selected shapes or text to the front in a group of elements over an image.

{% tabs %}

{% highlight C# %}

   editor.BringToFront();

{% endhighlight %}

{% endtabs %}

## SendToBack

The [`SendToBack`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.ImageEditor.SfImageEditor.html#Syncfusion_UI_Xaml_ImageEditor_SfImageEditor_SendToBack) method is used to send the selected shapes or text to the back of a group of elements over an image.

{% tabs %}

{% highlight C# %}

   editor.SendToBack();

{% endhighlight %}

{% endtabs %}

## BringForward

The [`BringForward`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.ImageEditor.SfImageEditor.html#Syncfusion_UI_Xaml_ImageEditor_SfImageEditor_BringForward) method is used to bring the selected shapes/text to one step front of a group of elements over an image.

{% tabs %}

{% highlight C# %}

   editor.BringForward();

{% endhighlight %}

{% endtabs %}

## SendBackward

The [`SendBackward`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.ImageEditor.SfImageEditor.html#Syncfusion_UI_Xaml_ImageEditor_SfImageEditor_SendBackward) method is used to send the selected shapes/text to one step backward of a group of elements over an image.

{% tabs %}

{% highlight C# %}

   editor.SendBackward();

{% endhighlight %}

{% endtabs %}

