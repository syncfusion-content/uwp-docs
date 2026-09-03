---
layout: post
title: Selecting Color in UWP SfColorPicker | Syncfusion®
description: The selecting color feature in SfColorPicker allows selecting a color using the SelectedColor property or setting it via hexadecimal color code.
platform: uwp
control: SfColorPicker
documentation: ug
---

# Selecting Color in UWP Color Picker

## Retrieving the Current Selected Color

`SelectedColor` property is used to get the selected color in `UWP Color Picker`. The selected color is marked by the selected color thumb. SelectedColor can also be set using hexadecimal color code.

{% tabs %}

{% highlight XAML %}

<media:SfColorPicker SelectedColor="#FF008000"/>

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

colorPicker.SelectedColor = Colors.Green;

{% endhighlight %}

{% highlight VB %}

colorPicker.SelectedColor = Colors.Green

{% endhighlight %}

{% endtabs %}

![Selecting-Color-img1](Selecting-Color-images/Selecting-Color-img1.jpeg)

## Retrieving the Previous Selected Color

`PreviousColor` property is used to get the previously selected color in `UWP Color Picker`. The previous color is displayed in the ellipse placed at right bottom of the control.

{% tabs %}

{% highlight C# %}

Color previousColor = colorPicker.PreviousColor;

{% endhighlight %}

{% highlight VB %}

Dim previousColor As Color = colorPicker.PreviousColor

{% endhighlight %}

{% endtabs %}

![Selecting-Color-img2](Selecting-Color-images/Selecting-Color-img2.jpeg)

## Notifying the Selected Color Change

`SelectedColorChanged` event is fired when the selected color is changed in the `UWP Color Picker`

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

{% highlight VB %}

Private Sub colorPicker_SelectedColorChanged(ByVal sender As Object, ByVal e As DependencyPropertyChangedEventArgs)


End Sub

{% endhighlight %}

{% endtabs %}

