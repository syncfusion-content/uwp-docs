---
layout: post
title: Selecting Color of SfColorPicker control for UWP
description: Selecting Color of SfColorPicker control for UWP
platform: uwp
control: SfColorPicker
documentation: ug
---

# Selecting Color

## Change color selection

`SelectedColor` property is used to get the selected color in `SfColorPicker`. The selected color is marked by the selected color thumb. SelectedColor can also be set using hexadecimal color code.

{% tabs %}

{% highlight XAML %}

<media:SfColorPicker SelectedColor="#FF008000"/>

{% endhighlight %}

{% highlight C# %}

colorPicker.SelectedColor = Colors.Green;

{% endhighlight %}

{% endtabs %}

![](Selecting-Color-images/Selecting-Color-img1.jpeg)

## Previous Color

`PreviousColor` property is used to get the previously selected color in `SfColorPicker`. The previous color is displayed in the ellipse placed at right bottom of `SfColorPicker` control.

{% tabs %}

{% highlight C# %}

Color previousColor = colorPicker.PreviousColor;

{% endhighlight %}

{% endtabs %}

![](Selecting-Color-images/Selecting-Color-img2.jpeg)

## SelectedColorChanged event

`SelectedColorChanged` event is fired when the selected color is changed in `SfColorPicker`

{% tabs %}

{% highlight XAML %}

<media:SfColorPicker x:Name="colorPicker"
                     SelectedColorChanged="colorPicker_SelectedColorChanged"/>

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

private void colorPicker_SelectedColorChanged(object sender, DependencyPropertyChangedEventArgs e)

{

}

{% endhighlight %}

{% endtabs %}

