---
layout: post
title: Appearance and Styling | SfAccordion | UWP | Syncfusion
description: Appearance and Styling of Syncfusion SfAccordion control for UWP
platform: UWP
control: SfAccordion
documentation: ug

---

# Appearance and Styling

`AccentBrush` property is used to decorate the hot spots of a control with a solid color

{% tabs %}

{% highlight XAML %}

<layout:SfAccordion HorizontalAlignment="Center"

VerticalAlignment="Center"            

DisplayMemberPath="Name" 

AccentBrush="Green"

ItemsSource="{Binding Employees}" />

{% endhighlight %}

{% highlight C# %}

accordion.AccentBrush = new SolidColorBrush() { Color = Windows.UI.Colors.Red };

{% endhighlight %}

{% endtabs %}

![](Appearence-and-Styling-images/Appearence-and-Styling-img1.jpeg)


