---
layout: post
title: overview of Syncfusion SfPulsingTile control for UWP
description: overview of Syncfusion SfPulsingTile control for UWP
platform: uwp
control: SfPulsingTile
documentation: ug
---

# SfPulsingTile

`SfPulsingTile` control allows to create a tile similar to Music and Video hub tile in Windows phone. The content zooms in/out randomly with random translation in X and Y axis.

## Overview

### Features

Animation properties are completely customizable  

### Visual structure

1.WinRT

![](SfpulsingTile-images/SfpulsingTile-img1.jpeg)

2.Windows phone

![](SfpulsingTile-images/SfpulsingTile-img2.jpeg)

![](SfpulsingTile-images/SfpulsingTile-img3.jpeg)

## Creating SfSplitMosaicTile control

Create a Universal Windows project in Visual Studio and refer to the following assemblies.

1. Syncfusion. SfHubTile.UWP

2. Syncfusion.SfShared.UWP

### Adding SfSplitMosaicTile control through XAML Code

1.Include the namespace for Syncfusion.SfHubTile.UWP assembly in MainPage.xaml

{% tabs %}

{% highlight XAML %}

<Page xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"

xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"

xmlns:notification="using:Syncfusion.UI.Xaml.Controls.Notification">

{% endhighlight %}

{% endtabs %}

2.Now add the `SfSplitMosaicTile` control with a required optimal name using the included namespace

{% tabs %}

{% highlight XAML %}

<notification:SfSplitMosaicTile x:Name="splitMosaicTile">

{% endhighlight %}

{% endtabs %}

### Adding SfSplitMosaicTile control through C# Code

1.Include the namespace for Syncfusion. SfHubTile.UWP assembly in MainPage.xaml.cs

{% tabs %}

{% highlight C# %}

using Syncfusion.UI.Xaml.Controls.Notification;

{% endhighlight %}

{% endtabs %}

2.Now add the SfSplitMosaicTile control with an optimal name 

{% tabs %}

{% highlight C# %}

SfSplitMosaicTile splitMosaicTile = new SfSplitMosaicTile();

{% endhighlight %}

{% endtabs %}

## Configuring the tile

`SfSplitMosaicTile` can be configured with header and images as follows:

### Setting the header

`Header` property is used to set a display text at the bottom of the tile.

{% tabs %}

{% highlight XAML %}

<notification:SfPulsingTile Header="Pulsing tile" x:Name="pulsingTile"/> 

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

pulsingTile.Header = "Pulsing Tile";

{% endhighlight %}

{% endtabs %}

![](SfpulsingTile-images/SfpulsingTile-img4.jpeg)

### Setting the content

Animation is performed on the content of pulsing tile regardless of its type. Here is an example to set an image as content of pulsing tile.

{% tabs %}

{% highlight XAML %}

<notification:SfPulsingTile Header="Pulsing tile" x:Name="pulsingTile">

<Image Source="Assets/PulsingTile.jpg" Stretch="UniformToFill" VerticalAlignment="Center"

HorizontalAlignment="Center"/>

</notification:SfPulsingTile>

{% endhighlight %}

{% endtabs %}

![](SfpulsingTile-images/SfpulsingTile-img5.jpeg)

## Customizing animation

The animation properties that can be changed are pulsing depth, pulsing duration, translation duration, height and width.

### Pulse depth

`PulseScale` property specifies the range of translation in the x- and y-axis while pulsing the content.

{% tabs %}

{% highlight XAML %}

<notification:SfPulsingTile PulseScale="1.2" x:Name="pulsingTile">

<Image Source="Assets/PulsingTile.jpg" Stretch="UniformToFill"
       VerticalAlignment="Center" HorizontalAlignment="Center" Height="150" />

</notification:SfPulsingTile>

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

pulsingTile.PulseScale = 1.2;

{% endhighlight %}

{% endtabs %}

### Pulse duration

`PulseDuration` property specifies the time taken for a single scaling animation to complete in pulsing tile. Animation happens repeatedly if it is not frozen.

{% tabs %}

{% highlight XAML %}

<notification:SfPulsingTile Height="150" Width="150"
                            PulseDuration="0:0:2" PulseScale="1.2" x:Name="pulsingTile">

<Image Source="Assets/PulsingTile.jpg" Stretch="UniformToFill"
       VerticalAlignment="Center" HorizontalAlignment="Center" Height="150" />

</notification:SfPulsingTile>

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

pulsingTile.PulseDuration = TimeSpan.FromSeconds(2);

{% endhighlight %}

{% endtabs %}

### Translation width

`RadiusX` property specifies the range of translation in pulsing tile along x-axis.

{% tabs %}

{% highlight XAML %}

<notification:SfPulsingTile RadiusX="2" x:Name="pulsingTile">

<Image Source="Assets/PulsingTile.jpg" Stretch="UniformToFill"
       VerticalAlignment="Center" HorizontalAlignment="Center" Height="150" />

</notification:SfPulsingTile>

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

pulsingTile.RadiusX = 2.0;

{% endhighlight %}

{% endtabs %}

### Translation height

`RadiusY` property specifies the range of translation in pulsing tile along y-axis.

{% tabs %}

{% highlight XAML %}

<notification:SfPulsingTile RadiusY="2" x:Name="pulsingTile">

<Image Source="Assets/PulsingTile.jpg" Stretch="UniformToFill"
       VerticalAlignment="Center" HorizontalAlignment="Center" Height="150" />

</notification:SfPulsingTile>

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

pulsingTile.RadiusY = 2.0;

{% endhighlight %}

{% endtabs %}

### Translation duration

`TranslateDuration` property specifies the time taken for a single translation animation to complete in pulsing tile. Animation happens repeatedly if it is not frozen.

{% tabs %}

{% highlight XAML %}

<notification:SfPulsingTile RadiusX="2" RadiusY="2" TranslationDuration="0:0:2" x:Name="pulsingTile">

<Image Source="Assets/PulsingTile.jpg" Stretch="UniformToFill"
       VerticalAlignment="Center" HorizontalAlignment="Center" Height="150" />

</notification:SfPulsingTile>

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

pulsingTile.TranslationDuration = TimeSpan.FromSeconds(2);

{% endhighlight %}

{% endtabs %}

Flip effect customization, tile click & command, pausing and resuming animation, AccentBrush, TitleStyle topics are available under HubTileBase section.
