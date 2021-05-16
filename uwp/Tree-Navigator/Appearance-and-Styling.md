---
layout: post
title: Appearance and Styling in UWP Tree Navigator control | Syncfusion
description: Learn here all about Appearance and Styling support in Syncfusion UWP Tree Navigator (SfTreeNavigator) control and more.
platform: uwp
control: SfTreeNavigator
documentation: ug
---

# Appearance and Styling in UWP Tree Navigator (SfTreeNavigator)

## Customizing TreeNavigator Header

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

![Appearance and Styling](Appearance-and-Styling-images/Appearance-and-Styling-img2.jpeg)


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

![HeaderStyle](Appearance-and-Styling-images/Appearance-and-Styling-img3.jpeg)

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

![HeaderStyle](Appearance-and-Styling-images/Appearance-and-Styling-img4.jpeg)

## Customizing TreeNavigatorItem Header

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

![Customizing TreeNavigatorItem Header](Appearance-and-Styling-images/Appearance-and-Styling-img5.jpeg)

## Customizing the control Hot-spot

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

![Customizing the control Hot-spot](Appearance-and-Styling-images/Appearance-and-Styling-img6.jpeg)


