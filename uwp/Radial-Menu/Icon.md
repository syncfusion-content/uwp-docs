---
layout: post
title: Icon in UWP Radial Menu control | Syncfusion
description: Learn here all about Icon support in Syncfusion UWP Radial Menu (SfRadialMenu) control and more.
platform: uwp
control: SfRadial Menu 
documentation: ug
---

# Icon in UWP Radial Menu (SfRadialMenu)

The Icon property of the SfRadialMenu is used to customize the icon displayed in the center of RadialMenu circle.   

{% tabs %}

{% highlight xaml %}

<navigation:SfRadialMenu IsOpen="True" >

<navigation:SfRadialMenu.Icon>

                <Grid Background="White">

                    <Image Source="ms-appx:///Assets/text.png" Width="20"  

 	 	 	                Stretch="Uniform"/>

                </Grid>

            </navigation:SfRadialMenu.Icon>

 </navigation:SfRadialMenu>

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

 SfRadialMenu radialMenu = new SfRadialMenu() { IsOpen = true };

 Grid _grid = new Grid() { Background = new SolidColorBrush(Colors.White) };

 Image img = new Image() { Width = 20, Stretch = Stretch.Uniform };

 img.Source = new BitmapImage(new Uri(@"ms-appx:///Assets/text.png", UriKind.RelativeOrAbsolute)) ;

 _grid.Children.Add(img);

 radialMenu.Icon = _grid;

{% endhighlight %}

{% highlight VB %}

Dim radialMenu As New SfRadialMenu() With {.IsOpen = True}

 Dim _grid As New Grid() With {.Background = New SolidColorBrush(Colors.White)}

 Dim img As New Image() With {
	 .Width = 20,
	 .Stretch = Stretch.Uniform
 }

 img.Source = New BitmapImage(New Uri("ms-appx:///Assets/text.png", UriKind.RelativeOrAbsolute))

 _grid.Children.Add(img)

 radialMenu.Icon = _grid

{% endhighlight %}

{% endtabs %}

![RadialMenu Icon view](Icon_images/Icon_img1.png)





