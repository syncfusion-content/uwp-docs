---
layout: post
title: How to Render KML Shapes in ShapeFileLayer for UWP Maps | Syncfusion®
description: Learn how to render KML shapes in a ShapeFileLayer and configure KML files as embedded resources in UWP Maps.
platform: uwp
control: SfMap
documentation: ug
---

# How to Render KML Shapes in ShapeFileLayer for UWP Maps

A `KML` file can be rendered with the help of the [`ShapeFileLayer`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Maps.ShapeFileLayer.html) in [`SfMap`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Maps.SfMap.html). The KML file should be added as an embedded resource to the application project. The [`Uri`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Maps.ShapeFileLayer.html#Syncfusion_UI_Xaml_Maps_ShapeFileLayer_Uri) of the KML file must be given in the following order:

* Namespace of the project
* Folder names
* KmlFileName.kml



{% highlight xml %}

<syncfusion:SfMap>
    <syncfusion:SfMap.Layers>
        <syncfusion:ShapeFileLayer Uri="KmlImportDemo.Assets.KMLFiles.Eu.kml"/>
    </syncfusion:SfMap.Layers>
</syncfusion:SfMap>

{% endhighlight %}

![UWP Map Control KML Shapes Rendered in ShapeFileLayer](KML-Shapes-Rendered-in-ShapeFileLayer_images/KML-Shapes-Rendered-in-ShapeFileLayer_img1.png)



