---
layout: post
title: Zooming in UWP Image Editor control | Syncfusion
description: Learn here all about Zooming support in Syncfusion UWP Image Editor (SfImageEditor) control and more.
platform: UWP
control: SfImageEditor
documentation: ug
---

The following namespaces are required for zooming and panning in the SfImageEditor control:

* `Syncfusion.UI.Xaml.ImageEditor`
* `Syncfusion.UI.Xaml.ImageEditor.Enums`

# Zooming in UWP Image Editor (SfImageEditor)

The image editor control provides support for zoom and pan actions over an image. You can zoom in and zoom out of the image in the image editor control.

The following properties are used for the zooming feature of the image editor control:

* `EnableZooming`
* `PanningMode`

## Enable zooming

You can enable or disable the zooming functionality by setting the [`EnableZooming`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.ImageEditor.SfImageEditor.html#Syncfusion_UI_Xaml_ImageEditor_SfImageEditor_EnableZooming) property to `true` or `false`. By default, the `EnableZooming` property is set to `true`.

{% tabs %}

{% highlight XAML %}

    xmlns:imageeditor="using:Syncfusion.UI.Xaml.ImageEditor"

    <imageeditor:SfImageEditor x:Name="editor" EnableZooming="false"/>

{% endhighlight %}

{% highlight C# %}

    using Syncfusion.UI.Xaml.ImageEditor;

    editor.EnableZooming = false;

{% endhighlight %}

{% endtabs %}

## Panning mode

The image editor control provides support for panning and allows you to pan the image with two fingers or a single finger by setting the [`PanningMode`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.ImageEditor.SfImageEditor.html#Syncfusion_UI_Xaml_ImageEditor_SfImageEditor_PanningMode).

The following values are used for panning:

* `SingleFinger`: Zooms or pans the image with a single finger, but shapes and text selection cannot be performed with this mode.
* `TwoFinger`: Zooms or pans the image with two fingers. Shapes and text selection can be performed with this mode.

By default, the [`PanningMode`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.ImageEditor.SfImageEditor.html#Syncfusion_UI_Xaml_ImageEditor_SfImageEditor_PanningMode) value is set to `TwoFinger`.

{% tabs %}

{% highlight XAML %}

    xmlns:imageeditor="using:Syncfusion.UI.Xaml.ImageEditor"

    <imageeditor:SfImageEditor x:Name="editor" EnableZooming="true" PanningMode="TwoFinger"/>

{% endhighlight %}

{% highlight C# %}

    using Syncfusion.UI.Xaml.ImageEditor.Enums;

    editor.PanningMode = PanningMode.TwoFinger;

{% endhighlight %}

{% endtabs %}

## Maximum zoom level

Zooming of the image can be restricted to a certain level based on the value of the [`MaximumZoomLevel`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.ImageEditor.SfImageEditor.html#Syncfusion_UI_Xaml_ImageEditor_SfImageEditor_MaximumZoomLevel) property.

{% tabs %}

{% highlight XAML %}

    xmlns:syncfusion="using:Syncfusion.UI.Xaml.ImageEditor"

    <syncfusion:SfImageEditor x:Name="editor" MaximumZoomLevel="2">
    </syncfusion:SfImageEditor>

{% endhighlight %}

{% highlight C# %}

    using Syncfusion.UI.Xaml.ImageEditor;

    SfImageEditor editor = new SfImageEditor();
    editor.MaximumZoomLevel = 2;

{% endhighlight %}

{% endtabs %}
