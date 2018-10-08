---
layout: post
title: Dealing with Ticks in SfRangeSlider control for UWP
description: Explains about Ticks in SfRangeSlider control for UWP 
platform: uwp
control: SfRange Slider 
documentation: ug
---

# Dealing with Ticks 

It is possible to place tick marks along the track in a uniform manner. The position of tick marks can be customized. 

## Tick Frequency 

The Tick Frequency property is used to define the number of ticks along the track, based on Minimum and Maximum values. 

{% tabs %}

{% highlight xaml %}

<editors:SfRangeSlider x:Name="rangeSlider" Width="200"  Minimum="0"  Maximum="100" TickFrequency="20" Value="40" />

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight c# %}

   rangeSlider.TickFrequency = 20;

{% endhighlight %}

{% highlight VB %}

  rangeSlider.TickFrequency = 20

{% endhighlight %}

{% endtabs %}

![](Ticks_images/Ticks_img1.png)

N>  When the SnapsTo property is set to Ticks, the TickFrequency is used to specify the interval between snap points.

## Step Frequency  

When the SnapsTo property is set to StepValues, the StepFrequency property is used to specify the interval between snap points. 

{% tabs %}

{% highlight xaml %}

<editors:SfRangeSlider x:Name="rangeSlider" Width="200" VerticalAlignment="Center" Minimum="0"  Maximum="100" StepFrequency="20" Value="40"/>

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight c# %}

   rangeSlider.StepFrequency = 20;

{% endhighlight %}

{% highlight VB %}

   rangeSlider.StepFrequency = 20

{% endhighlight %}

{% endtabs %}

## Snaps To 

The SnapsTo property determines whether the RangeSlider snaps to steps or ticks. Available options for this property are 

1. StepValues 
2. Ticks 

Default option is StepValues and StepFrequency property is used to specify the interval between snap points in this case. If the SnapsTo property is set to Ticks, the TickFrequency property is used to specify the interval between snap points.  

## Tick Placement 

The TickPlacement property used to determine where to draw tick marks in relation to the track. Available options for this property are 

1. BottomRight 
2. Inline 
3. None 
4. Outside 
5. TopLeft 

The default option is Inline.  



### BottomRight  

Tick marks placed either below the track in horizontal orientation or right of the track in vertical orientation. 

{% tabs %}

{% highlight xaml %}

<editors:SfRangeSlider Width="200" Minimum="0"   Maximum="100"   x:Name="rangeSlider"                                                   

TickFrequency="20" TickPlacement="BottomRight" Value="40"   />

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight c# %}

   rangeSlider.TickPlacement = Syncfusion.UI.Xaml.Controls.Input.TickPlacement.BottomRight;

{% endhighlight %}

{% highlight VB %}

  rangeSlider.TickPlacement = Syncfusion.UI.Xaml.Controls.Input.TickPlacement.BottomRight

{% endhighlight %}

{% endtabs %}

![](Ticks_images/Ticks_img3.png)

N>  In Vertical Orientation, this option will place the ticks to right side. 

### TopLeft  

Tick marks placed either above the track in horizontal orientation or left of the track in vertical orientation. 

{% tabs %}

{% highlight xaml %}

<editors:SfRangeSlider x:Name="rangeSlider" Width="200"  Minimum="0"   Maximum="100" TickFrequency="20" TickPlacement="TopLeft"  Value="40"   />

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight c# %}

   rangeSlider.TickPlacement = Syncfusion.UI.Xaml.Controls.Input.TickPlacement.TopLeft;

{% endhighlight %}

{% highlight VB %}

  rangeSlider.TickPlacement = Syncfusion.UI.Xaml.Controls.Input.TickPlacement.TopLeft

{% endhighlight %}

{% endtabs %}

![](Ticks_images/Ticks_img5.png)


N>  In Vertical Orientation, this option will place the ticks to left side.

### Outside 

Tick marks placed on both sides of the track either in horizontal or vertical orientation.  

{% tabs %}

{% highlight xaml %}

<editors:SfRangeSlider x:Name="rangeSlider" Width="200" Minimum="0" Maximum="100" TickFrequency="20"  TickPlacement="Outside" Value="40"/>

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight c# %}

   rangeSlider.TickPlacement = Syncfusion.UI.Xaml.Controls.Input.TickPlacement.Outside;

{% endhighlight %}

{% highlight VB %}

   rangeSlider.TickPlacement = Syncfusion.UI.Xaml.Controls.Input.TickPlacement.Outside

{% endhighlight %}

{% endtabs %}

![](Ticks_images/Ticks_img7.png)

### Inline 

Ticks are placed inside the track.  

{% tabs %}

{% highlight xaml %}

<editors:SfRangeSlider x:Name="rangeSlider" Width="200" Minimum="0" Maximum="100" TickFrequency="20" TickPlacement="Inline" Value="40" />

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight c# %}

   rangeSlider.TickPlacement = Syncfusion.UI.Xaml.Controls.Input.TickPlacement.Inline;

{% endhighlight %}

{% highlight VB %}

  rangeSlider.TickPlacement = Syncfusion.UI.Xaml.Controls.Input.TickPlacement.Inline

{% endhighlight %}

{% endtabs %}

![](Ticks_images/Ticks_img8.png)

### None 

Tick marks not appear.  

{% tabs %}

{% highlight xaml %}

<editors:SfRangeSlider x:Name="rangeSlider" Width="200" Minimum="0" Maximum="100" TickFrequency="20" TickPlacement="None" Value="40" />

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight c# %}

   rangeSlider.TickPlacement = Syncfusion.UI.Xaml.Controls.Input.TickPlacement.None;

{% endhighlight %}

{% highlight VB %}

   rangeSlider.TickPlacement = Syncfusion.UI.Xaml.Controls.Input.TickPlacement.None

{% endhighlight %}

{% endtabs %}

![](Ticks_images/Ticks_img9.png)

## Customizing tick color

The range slider control provides the `TickBarFill` property to customize the color of ticks in tick bar.

{% tabs %}

{% highlight xaml %}

<editors:SfRangeSlider x:Name="rangeSlider" Width="300" TickBarFill="Blue" Minimum="100" Maximum="200" TickFrequency="20" TickPlacement="Outside" ShowValueLabels="True" LabelOrientation="Horizontal"/>

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight c# %}

   rangeSlider.TickBarFill= new SolidColorBrush(Color.FromArgb(255, (byte)0, (byte)0, (byte)255));

{% endhighlight %}

{% highlight VB %}

  rangeSlider.TickBarFill= new SolidColorBrush(Color.FromArgb(255, (byte)0, (byte)0, (byte)255))

{% endhighlight %}

{% endtabs %}

![](Ticks_images/Ticks_img10.png)



