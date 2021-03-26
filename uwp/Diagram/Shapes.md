---
layout: post
title: Basic Shapes with Syncfusion Essential Diagram for UWP.
description: How do add different shapes to diagram 
platform: uwp
control: SfDiagram
documentation: ug
---

# Shapes

We have provided some basic built-in shapes as ResourceDictionary.

The following code example illustrates how to merge shapes into diagram.

{% highlight xaml %}
            <ResourceDictionary.MergedDictionaries>
                <ResourceDictionary Source="ms-appx:///Syncfusion.SfDiagram.UWP/Resources/BasicShapes.xaml"/>
            </ResourceDictionary.MergedDictionaries>  
{% endhighlight %}


## Basic Shapes

The following code example illustrates how to assign Shape property of the Node.

{% highlight xaml %}
<ResourceDictionary.MergedDictionaries>
                <ResourceDictionary Source="ms-appx:///Syncfusion.SfDiagram.UWP/Resources/BasicShapes.xaml"/>
            </ResourceDictionary.MergedDictionaries>
            <!--Style for Shape of the Node-->
            <Style TargetType="Path" x:Key="ShapeStyle">
                <Setter Property="Fill" Value="#FF5B9BD5"/>
                <Setter Property="Stretch" Value="Fill"/>
                <Setter Property="Stroke" Value="Black"/>
            </Style>
{% endhighlight %}
{% highlight xaml %}
<!--Add Node with basic shape-->
<Syncfusion:NodeViewModel x:Name="Node1" ID="Begin" OffsetX="300" OffsetY="200" Shape="{StaticResource Rectangle}" UnitHeight="100" UnitWidth="100" ShapeStyle="{StaticResource ShapeStyle}"/>   
{% endhighlight %}

Output Node will be,

 ![UWP SfDiagram Shapes Image1](Shapes_images\Shapes_image1.PNG)
  
 The list of basic shapes are as follows
 
 ![UWP SfDiagram Shapes Image2](Shapes_images\Shapes_image2.PNG)
 
The list of flow shapes are as follows

![UWP SfDiagram Shapes Image4](Shapes_images\Shapes_image4.PNG)
 
The list of arrow shapes are as follows

![UWP SfDiagram Shapes Image5](Shapes_images\Shapes_image5.PNG)





 
 











