---
layout: post
title: Appearance and Styling of SfTreeNavigator control for UWP
description: Appearance and Styling of SfTreeNavigator control for UWP
platform: uwp
control: SfTreeNavigator
documentation: ug
---

# Appearance and Styling

## TreeNavigator Header

`SfTreeNavigator` has support to display a header text using Header property.

{% tabs %}

{% highlight XAML %}

<navigation:SfTreeNavigator>

<navigation:SfTreeNavigatorItem Header="WPF"/>

<navigation:SfTreeNavigatorItem Header="Silverlight" />

<navigation:SfTreeNavigatorItem Header="Windows Phone"/>

<navigation:SfTreeNavigatorItem Header="WinRT"/>

<navigation:SfTreeNavigatorItem Header="Universal"/>

</navigation:SfTreeNavigator>

{% endhighlight %}

{% endtabs %}

![](Appearance-and-Styling-images/Appearance-and-Styling-img1.jpeg)

## TreeNavigator Header Template

`HeaderTemplate` property of SfTreeNavigator is used to apply a customized template for `SfTreeNavigator` header.

{% tabs %}

{% highlight XAML %}

<navigation:SfTreeNavigator>

<navigation:SfTreeNavigator.HeaderTemplate>

<DataTemplate>

<TextBlock Text="{Binding}" Foreground="Red"/>

</DataTemplate>

</navigation:SfTreeNavigator.HeaderTemplate>

<navigation:SfTreeNavigatorItem Header="WPF"/>

<navigation:SfTreeNavigatorItem Header="Silverlight" />

<navigation:SfTreeNavigatorItem Header="Windows Phone"/>

<navigation:SfTreeNavigatorItem Header="WinRT"/>

<navigation:SfTreeNavigatorItem Header="Universal"/>

</navigation:SfTreeNavigator>

{% endhighlight %}

{% endtabs %}

![](Appearance-and-Styling-images/Appearance-and-Styling-img2.jpeg)

## TreeNavigator Header Style

`HeaderStyle` property of SfTreeNavigator is used to customize the `SfTreeNavigator` header.

{% tabs %}

{% highlight XAML %}

<navigation:SfTreeNavigator>

<navigation:SfTreeNavigator.HeaderStyle>

<Style TargetType="ContentControl">

<Setter Property="Foreground" Value="Red"/>

</Style>                      

</navigation:SfTreeNavigator.HeaderStyle>

<navigation:SfTreeNavigatorItem Header="WPF"/>

<navigation:SfTreeNavigatorItem Header="Silverlight" />

<navigation:SfTreeNavigatorItem Header="Windows Phone"/>

<navigation:SfTreeNavigatorItem Header="WinRT"/>

<navigation:SfTreeNavigatorItem Header="Universal"/>

</navigation:SfTreeNavigator>

{% endhighlight %}

{% endtabs %}

![](Appearance-and-Styling-images/Appearance-and-Styling-img3.jpeg)

## TreeNavigatorItem Header Template

`HeaderTemplate` property of `SfTreeNavigatorItem` is used to apply a customized template for `SfTreeNavigator` header.

{% tabs %}

{% highlight XAML %}

<navigation:SfTreeNavigator>

<navigation:SfTreeNavigatorItem Header="WPF">

<navigation:SfTreeNavigatorItem.HeaderTemplate>

<DataTemplate>

<TextBlock Text="{Binding}" FontStyle="Italic"
           FontWeight="Bold" Foreground="Green"/>

</DataTemplate>

</navigation:SfTreeNavigatorItem.HeaderTemplate>

</navigation:SfTreeNavigatorItem>

<navigation:SfTreeNavigatorItem Header="Silverlight" />

<navigation:SfTreeNavigatorItem Header="Windows Phone"/>

<navigation:SfTreeNavigatorItem Header="WinRT"/>

<navigation:SfTreeNavigatorItem Header="Universal"/>

</navigation:SfTreeNavigator>

{% endhighlight %}

{% endtabs %}

![](Appearance-and-Styling-images/Appearance-and-Styling-img4.jpeg)

## TreeNavigator HeaderItem Style

The stacked headers in Extended navigation mode can be styled as follows:

{% tabs %}

{% highlight XAML %}

<Page.Resources>

<Style TargetType="navigation:TreeNavigatorHeaderItem">

<Setter Property="Background" Value="Pink"/>

</Style>

</Page.Resources>

<navigation:SfTreeNavigator NavigationMode="Extended">            

<navigation:SfTreeNavigatorItem Header="WPF">

<navigation:SfTreeNavigatorItem Header="Chart"/>

<navigation:SfTreeNavigatorItem Header="Grid"/>

<navigation:SfTreeNavigatorItem Header="Tools"/>

</navigation:SfTreeNavigatorItem>                                            

<navigation:SfTreeNavigatorItem Header="Silverlight" />

<navigation:SfTreeNavigatorItem Header="Windows Phone"/>

<navigation:SfTreeNavigatorItem Header="WinRT"/>

<navigation:SfTreeNavigatorItem Header="Universal"/>

</navigation:SfTreeNavigator>

{% endhighlight %}

{% endtabs %}

![](Appearance-and-Styling-images/Appearance-and-Styling-img5.jpeg)

## Accent Brush

`AccentBrush` property is used to change the selected item background color.

{% tabs %}

{% highlight XAML %}

<navigation:SfTreeNavigator Width="350" VerticalAlignment="Center"
                            HorizontalAlignment="Center" x:Name="treeNavigator">            

<navigation:SfTreeNavigatorItem Header="WPF" AccentBrush="Green"/>               

<navigation:SfTreeNavigatorItem Header="Silverlight" />

<navigation:SfTreeNavigatorItem Header="Windows Phone"/>

<navigation:SfTreeNavigatorItem Header="WinRT"/>

<navigation:SfTreeNavigatorItem Header="Universal"/>

</navigation:SfTreeNavigator>

{% endhighlight %}

{% endtabs %}

![](Appearance-and-Styling-images/Appearance-and-Styling-img6.jpeg)


