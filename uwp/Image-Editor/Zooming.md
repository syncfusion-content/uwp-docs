---
layout: post
title: Zooming and Panning operations in Syncfusion SfImageEditor UWP
description: Learn how to perform Zooming and panning in the image in SfImageEditor control for UWP platform
platform: UWP
control: ImageEditor
documentation: ug
---

# Zooming in SfImageEditor

The image editor control provides support to zoom and pan actions over an image. You can Zoom in and Zoom out the image in image editor control.

The following properties are used for zooming feature of the image editor control:

* EnableZooming

* PanningMode

## Enable zooming

You can enable or disable the zooming functionality by setting the [`EnableZooming`](https://help.syncfusion.com/cr/uwp/Syncfusion.SfImageEditor.UWP~Syncfusion.UI.Xaml.ImageEditor.SfImageEditor~EnableZooming.html) value to true or false. By default, the `EnableZooming` value is set to true.

{% tabs %}

{% highlight XAML %}
  
    <imageeditor:SfImageEditor x:Name="editor" EnableZooming="false"/>
     
{% endhighlight %}

{% highlight C# %}
   
     editor.EnableZooming = false;

{% endhighlight %}

{% endtabs %}

## Panning mode

The image editor control provides support for panning and allows to pan the image with two fingers or single finger by setting the [`PanningMode`](https://help.syncfusion.com/cr/uwp/Syncfusion.SfImageEditor.UWP~Syncfusion.UI.Xaml.ImageEditor.SfImageEditor~PanningMode.html).

The following properties are used for panning:

* `SingleFinger`: Zooms or pans the image with single finger, but shapes and text selection cannot be performed with this mode.
* `TwoFinger`: Zooms or pans the image with two finger. The shapes and text selection can be performed with this mode.

By default, the [`PanningMode`](https://help.syncfusion.com/cr/uwp/Syncfusion.SfImageEditor.UWP~Syncfusion.UI.Xaml.ImageEditor.SfImageEditor~PanningMode.html) value is set to `TwoFinger`.

{% tabs %}

{% highlight XAML %}

    <imageeditor:SfImageEditor x:Name="editor" EnableZooming="true" PanningMode="TwoFinger"/>

{% endhighlight %}

{% highlight C# %}

editor.PanningMode = PanningMode.TwoFinger;

{% endhighlight %}

{% endtabs %}