---
layout: post
title: Re-ordering and Orientation in UWP Tile View control | Syncfusion®
description: Learn here all about Re-ordering and Orientation support in Syncfusion® UWP Tile View (SfTileView) control and more.
platform: uwp
control: SfTileView
documentation: ug
---

# Re-ordering and Orientation in UWP Tile View (SfTileView)

## Reordering through touch

`SfTileView` control provides tab reordering feature through touch drag and drop. Set the properties AllowDragDrop and AllowReorder to enable/disable this feature.

{% tabs %}

{% highlight XAML %}

<layout:SfTileView Width="500" Height="300" ItemsSource="{Binding Employees}" >

<layout:SfTileView.ItemTemplate>

<DataTemplate>

<Border Background="LightBlue">

<TextBlock Text="{Binding Name}"/>

</Border>

</DataTemplate>

</layout:SfTileView.ItemTemplate>

<layout:SfTileView.MaximizedItemTemplate>

<DataTemplate>

<Border Background="LightBlue" >

<TextBlock Text="{Binding Description}" Foreground="DarkBlue" FontSize="18"/>

</Border>

</DataTemplate>

</layout:SfTileView.MaximizedItemTemplate>

</layout:SfTileView>

{% endhighlight %}

{% endtabs %}

![Re-ordering-and-orientation-img1](Re-ordering-and-orientation-images/Re-ordering-and-orientation-img1.jpeg)

## Orientation

### Orientation for TileView

Orientation specifies the arrangement sequence of tile view items. Both horizontal and vertical orientation are supported.

**Horizontal**

{% tabs %}

{% highlight XAML %}

<layout:SfTileView x:Name="tileView" Width="500" Height="300" Orientation="Horizontal">

<layout:SfTileViewItem Background="LightBlue" Content="PaulVent" MaximizedContent="Description about Paul" />

<layout:SfTileViewItem Background="LightBlue" Content="James" MaximizedContent="Description about James"/>

<layout:SfTileViewItem Background="LightBlue" Content="Carl" MaximizedContent="Description about Carl"/>

<layout:SfTileViewItem Background="LightBlue" Content="Niko" MaximizedContent="Description about Niko"/>

</layout:SfTileView>

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

tileView.Orientation = Orientation.Horizontal;

{% endhighlight %}

{% highlight VB %}

tileView.Orientation = Orientation.Horizontal

{% endhighlight %}

{% endtabs %}

![Re-ordering-and-orientation-img2](Re-ordering-and-orientation-images/Re-ordering-and-orientation-img2.jpeg)

**Vertical**

{% tabs %}

{% highlight XAML %}

<layout:SfTileView x:Name="tileView" Width="500" Height="300" Orientation="Vertical">

<layout:SfTileViewItem Background="LightBlue" Content="PaulVent" MaximizedContent="Description about Paul" />

<layout:SfTileViewItem Background="LightBlue" Content="James" MaximizedContent="Description about James"/>

<layout:SfTileViewItem Background="LightBlue" Content="Carl" MaximizedContent="Description about Carl"/>

<layout:SfTileViewItem Background="LightBlue" Content="Niko" MaximizedContent="Description about Niko"/>

</layout:SfTileView>

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

tileView.Orientation = Orientation.Vertical;

{% endhighlight %}

{% highlight VB %}

tileView.Orientation = Orientation.Vertical

{% endhighlight %}

{% endtabs %}

![Re-ordering-and-orientation-img3](Re-ordering-and-orientation-images/Re-ordering-and-orientation-img3.jpeg)

### Orientation for MinimizedTileViewItems

The orientation of minimized items panel can be changed using `MinimizedItemsOrientation` property. The supported orientations are 

* Top 
* Bottom
* Left 
* Right

**Top**

Minimized items are placed at top of the control and maximized item at the bottom of the control.

{% tabs %}

{% highlight XAML %}

<layout:SfTileView x:Name="tileView" MinimizedItemsOrientation="Top">

<layout:SfTileViewItem Background="LightBlue" Content="PaulVent">

<layout:SfTileViewItem.MaximizedContent>

<Border Background="LightBlue">

<TextBlock Text="Description about Paul"/>

</Border>

</layout:SfTileViewItem.MaximizedContent>

</layout:SfTileViewItem>

<layout:SfTileViewItem Background="LightBlue" Content="James">

<layout:SfTileViewItem.MaximizedContent>

<Border Background="LightBlue">

<TextBlock Text="Description about James"/>

</Border>

</layout:SfTileViewItem.MaximizedContent>

</layout:SfTileViewItem>

<layout:SfTileViewItem Background="LightBlue" Content="Carl">

<layout:SfTileViewItem.MaximizedContent>

<Border Background="LightBlue">

<TextBlock Text="Description about Carl"/>

</Border>

</layout:SfTileViewItem.MaximizedContent>

</layout:SfTileViewItem>

<layout:SfTileViewItem Background="LightBlue" Content="Niko">

<layout:SfTileViewItem.MaximizedContent>

<Border Background="LightBlue">

<TextBlock Text="Description about Niko"/>

</Border>

</layout:SfTileViewItem.MaximizedContent>

</layout:SfTileViewItem>

</layout:SfTileView>

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

tileView.MinimizedItemsOrientation = Syncfusion.UI.Xaml.Controls.Layout.MinimizedItemsOrientation.Top;

{% endhighlight %}

{% highlight VB %}

tileView.MinimizedItemsOrientation = Syncfusion.UI.Xaml.Controls.Layout.MinimizedItemsOrientation.Top

{% endhighlight %}

{% endtabs %}

![Re-ordering-and-orientation-img4](Re-ordering-and-orientation-images/Re-ordering-and-orientation-img4.jpeg)

**Bottom**

Minimized items are placed at bottom of the control and maximized item at the top of the control.

{% tabs %}

{% highlight XAML %}

<layout:SfTileView x:Name="tileView" MinimizedItemsOrientation="Bottom">

</layout:SfTileView>

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

tileView.MinimizedItemsOrientation = Syncfusion.UI.Xaml.Controls.Layout.MinimizedItemsOrientation.Bottom;

{% endhighlight %}

{% highlight VB %}

tileView.MinimizedItemsOrientation = Syncfusion.UI.Xaml.Controls.Layout.MinimizedItemsOrientation.Bottom

{% endhighlight %}

{% endtabs %}

![Re-ordering-and-orientation-img5](Re-ordering-and-orientation-images/Re-ordering-and-orientation-img5.jpeg)

**Left**

Minimized items are placed at left side of the control and maximized item at the right side of the control. 

{% tabs %}

{% highlight XAML %}

<layout:SfTileView x:Name="tileView" MinimizedItemsOrientation="Left">

</layout:SfTileView>

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

tileView.MinimizedItemsOrientation = Syncfusion.UI.Xaml.Controls.Layout.MinimizedItemsOrientation.Left;

{% endhighlight %}

{% highlight VB %}

tileView.MinimizedItemsOrientation = Syncfusion.UI.Xaml.Controls.Layout.MinimizedItemsOrientation.Left

{% endhighlight %}

{% endtabs %}

![Re-ordering-and-orientation-img6](Re-ordering-and-orientation-images/Re-ordering-and-orientation-img6.jpeg)

**Right**

Minimized items are placed at right side of the control and maximized item at the left side of the control. 

{% tabs %}

{% highlight XAML %}

<layout:SfTileView x:Name="tileView" MinimizedItemsOrientation="Right">

</layout:SfTileView>

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

tileView.MinimizedItemsOrientation = Syncfusion.UI.Xaml.Controls.Layout.MinimizedItemsOrientation.Right;

{% endhighlight %}

{% highlight VB %}

tileView.MinimizedItemsOrientation = Syncfusion.UI.Xaml.Controls.Layout.MinimizedItemsOrientation.Right

{% endhighlight %}

{% endtabs %}

![Re-ordering-and-orientation-img7](Re-ordering-and-orientation-images/Re-ordering-and-orientation-img7.jpeg)


