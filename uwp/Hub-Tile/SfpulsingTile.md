---
layout: post
title: SfPulsingTile in UWP Hub Tile control | Syncfusion
description: Learn here all about SfPulsingTile support in Syncfusion UWP Hub Tile (HubTiles) control, its elements, features, and more.
platform: uwp
control: SfPulsingTile
documentation: ug
---

# SfPulsingTile in UWP Hub Tile (HubTiles)

`SfPulsingTile` control allows to create a tile similar to Music and Video hub tile in Windows Phone. The content zooms in/out randomly with random translation in X and Y axis.

## Features

Animation properties are completely customizable  

## Getting Started

This section explains how to create a Windows Phone “Music" tile using `SfPulsing` control.

### Adding SfSplitMosaicTile control

Create a Universal Windows Platform project in Visual Studio and refer to the following assemblies.

* Syncfusion.SfHubTile.UWP

* Syncfusion.SfShared.UWP

1.Include the namespace for Syncfusion.SfHubTile.UWP assembly in MainPage.xaml

{% tabs %}

{% highlight XAML %}

<Page xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"

xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"

xmlns:notification="using:Syncfusion.UI.Xaml.Controls.Notification">

{% endhighlight %}

{% endtabs %}

2.Now add the `SfPulsingTile` control with a required optimal name using the included namespace

{% tabs %}

{% highlight XAML %}

<notification:SfPulsingTile x:Name="pulsingTile">

{% endhighlight %}

{% highlight C# %}

 SfPulsingTile pulsingTile = new SfPulsingTile();

{% endhighlight %}

{% highlight VB %}

Dim pulsingTile As New SfPulsingTile()

{% endhighlight %}

{% endtabs %}

### Adding image to the tile

Set the image as Content of `SfPulsingTile` as given below:

{% tabs %}

{% highlight XAML %}

<notification:SfPulsingTile Width="183" Height="173"
                            Header="Pulsing tile">
                            
<Image Source="Assets/PulsingTile.jpg" Stretch="UniformToFill"
       VerticalAlignment="Center" HorizontalAlignment="Center"
       Height="200" />
       
</notification:SfPulsingTile>

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

  SfPulsingTile pulsingTile = new SfPulsingTile() { Width = 183, Height = 173, Header = "Pulsing tile" };

  pulsingTile.Content = new Image() { Source = new BitmapImage(new Uri(@"ms-appx:///Assets/PulsingTile.jpg", UriKind.RelativeOrAbsolute)),Height=200 , Stretch = Stretch.UniformToFill };

{% endhighlight %}

{% highlight VB %}

   Dim pulsingTile As New SfPulsingTile() With {
	  .Width = 183,
	  .Height = 173,
	  .Header = "Pulsing tile"
  }

   pulsingTile.Content = New Image() With {
				.Source = New BitmapImage(New Uri("ms-appx:///Assets/PulsingTile.jpg", UriKind.RelativeOrAbsolute)),
				.Height=200,
				.Stretch = Stretch.UniformToFill
			}

{% endhighlight %}

{% endtabs %}

![Pulsing tile displayed bitmap](SfpulsingTile-images/SfpulsingTile-img1.jpeg)

### Applying zoom animation

Adjusts the values of properties such as PulseScale, RadiusX and RadiusY.


{% tabs %}

{% highlight XAML %}


<notification:SfPulsingTile Width="183" Height="173"
                            Header="Pulsing tile" RadiusX="0"
                            RadiusY="0" PulseScale="2">
                            
<Image Source="Assets/PulsingTile.jpg" Stretch="UniformToFill"
       VerticalAlignment="Center" HorizontalAlignment="Center"
       Height="200" />
       
</notification:SfPulsingTile>

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

 SfPulsingTile pulsingTile = new SfPulsingTile() { Width = 183, Height = 173, Header = "Pulsing tile", RadiusX = 0, RadiusY = 0, PulseScale = 2};

 pulsingTile.Content = new Image() { Source = new BitmapImage(new Uri(@"ms-appx:///Assets/PulsingTile.jpg", UriKind.RelativeOrAbsolute)),Height=200 , Stretch = Stretch.UniformToFill };

{% endhighlight %}

{% highlight VB %}

 Dim pulsingTile As New SfPulsingTile() With {
	 .Width = 183,
	 .Height = 173,
	 .Header = "Pulsing tile",
	 .RadiusX = 0,
	 .RadiusY = 0,
	 .PulseScale = 2
 }

pulsingTile.Content = New Image() With {
				.Source = New BitmapImage(New Uri("ms-appx:///Assets/PulsingTile.jpg", UriKind.RelativeOrAbsolute)),
				.Height=200,
				.Stretch = Stretch.UniformToFill}
 
{% endhighlight %}

{% endtabs %}

![Pulsing tile zoom displayed bitmap content](sfpulsingtile-images/sfpulsingtile-img1.jpeg)

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

{% highlight VB %}

pulsingTile.Header = "Pulsing Tile"

{% endhighlight %}

{% endtabs %}

![Pulsing tile displayed header](sfpulsingtile-images/sfpulsingtile-img4.jpeg)

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

{% tabs %}

{% highlight C# %}

SfPulsingTile pulsingTile = new SfPulsingTile() { Width = 183, Height = 173, Header = "Pulsing tile" };

pulsingTile.Content = new Image() { Source = new BitmapImage(new Uri(@"ms-appx:///Assets/PulsingTile.jpg", UriKind.RelativeOrAbsolute)),Height=200 , Stretch = Stretch.UniformToFill };

{% endhighlight %}

{% highlight VB %}

Dim pulsingTile As New SfPulsingTile() With {
	.Width = 183,
	.Height = 173,
	.Header = "Pulsing tile"
}

pulsingTile.Content = New Image() With {
	.Source = New BitmapImage(New Uri("ms-appx:///Assets/PulsingTile.jpg", UriKind.RelativeOrAbsolute)),
	.Height=200,
	.Stretch = Stretch.UniformToFill
}

{% endhighlight %}

{% endtabs %}

![Pulsing tile displayed bitmap content](sfpulsingtile-images/sfpulsingtile-img5.jpeg)

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

{% highlight VB %}

pulsingTile.PulseScale = 1.2

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

{% highlight VB %}

pulsingTile.PulseDuration = TimeSpan.FromSeconds(2)

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

{% highlight VB %}

pulsingTile.RadiusX = 2.0

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

{% highlight VB %}

pulsingTile.RadiusY = 2.0

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

{% highlight VB %}

pulsingTile.TranslationDuration = TimeSpan.FromSeconds(2)

{% endhighlight %}

{% endtabs %}

Flip effect customization, tile click & command, pausing and resuming animation, AccentBrush, TitleStyle topics are available under HubTileBase section.
