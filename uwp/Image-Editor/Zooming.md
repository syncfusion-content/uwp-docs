---
layout: post
title: Zooming in UWP Image Editor control | Syncfusion
description: Learn here all about Zooming support in Syncfusion UWP Image Editor (SfImageEditor) control and more.
platform: UWP
control: SfImageEditor
documentation: ug
---

# Zooming in UWP Image Editor (SfImageEditor)

The image editor control provides support to zoom and pan actions over an image. You can zoom in and zoom out the image in image editor control.

The following properties are used for zooming feature of the image editor control:

* EnableZooming

* PanningMode

## Enable zooming

You can enable or disable the zooming functionality by setting the [`EnableZooming`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.ImageEditor.SfImageEditor.html#Syncfusion_UI_Xaml_ImageEditor_SfImageEditor_EnableZooming) value to true or false. By default, the `EnableZooming` value is set to true.

{% tabs %}

{% highlight XAML %}
  
    <imageeditor:SfImageEditor x:Name="editor" EnableZooming="false"/>
     
{% endhighlight %}

{% highlight C# %}
   
     editor.EnableZooming = false;

{% endhighlight %}

{% endtabs %}

## Panning mode

The image editor control provides support for panning and allows to pan the image with two fingers or single finger by setting the [`PanningMode`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.ImageEditor.SfImageEditor.html#Syncfusion_UI_Xaml_ImageEditor_SfImageEditor_PanningMode).

The following properties are used for panning:

* `SingleFinger`: Zooms or pans the image with single finger, but shapes and text selection cannot be performed with this mode.
* `TwoFinger`: Zooms or pans the image with two finger. The shapes and text selection can be performed with this mode.

By default, the [`PanningMode`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.ImageEditor.SfImageEditor.html#Syncfusion_UI_Xaml_ImageEditor_SfImageEditor_PanningMode) value is set to `TwoFinger`.

{% tabs %}

{% highlight XAML %}

    <imageeditor:SfImageEditor x:Name="editor" EnableZooming="true" PanningMode="TwoFinger"/>

{% endhighlight %}

{% highlight C# %}

editor.PanningMode = PanningMode.TwoFinger;

{% endhighlight %}

{% endtabs %}

## Maximum zoom level

Zooming of the image can be restricted to certain level based on the value of the [`MaximumZoomLevel`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.ImageEditor.SfImageEditor.html#Syncfusion_UI_Xaml_ImageEditor_SfImageEditor_MaximumZoomLevel) property.

{% tabs %}

{% highlight XAML %}

        <syncfusion:SfImageEditor x:Name="editor" MaximumZoomLevel="2">
          
        </syncfusion:SfImageEditor>

{% endhighlight %}

{% highlight C# %}

SfImageEditor editor = new SfImageEditor();
editor.MaximumZoomLevel = 2;

{% endhighlight %}

{% endtabs %}
