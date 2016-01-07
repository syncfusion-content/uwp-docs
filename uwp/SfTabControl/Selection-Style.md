---
layout: post
title: Selection Style of SfTabControl control for UWP
description: Selection Style of SfTabControl control for UWP
platform: uwp
control: SfTabControl
documentation: ug
---

# Selection style 

Header of a selected item can be customized in SfTabControl.

## Selection style

Foreground and background of a selected tab item can be changed using SelectedForeground and SelectedBackground properties. These properties are dependent on the value of SfTabControl.SelectionStyle property. The enum values of SelectionStyle are HeaderText and CompleteHeader. The default value is HeaderText.

## Selected Foreground

SelectedForeground property is used to customize the foreground color of the header text when that tab item is selected and SelectionStyle=”HeaderText”. SelectedBackground has no effect when set in HeaderText selection style.

{% tabs %}

{% highlight XAML %}

<navigation:SfTabControl x:Name="tabControl" SelectionStyle="HeaderText">

<navigation:SfTabItem x:Name="paul" Header="Paul Vent"
                      Content="Description about Paul Vent"
					  SelectedBackground="Green" SelectedForeground="Red"/>

<navigation:SfTabItem Header="Niko" Content="Description about Niko"/>

<navigation:SfTabItem Header="James" Content="Description about James"/>

<navigation:SfTabItem Header="Carl" Content="Description about Carl"/>

</navigation:SfTabControl>

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

tabControl.SelectionStyle = Syncfusion.UI.Xaml.Controls.Navigation.SelectionStyle.HeaderText;

paul.SelectedBackground = new SolidColorBrush(Colors.Green);

paul.SelectedForeground = new SolidColorBrush(Colors.Red);


{% endhighlight %}

{% endtabs %}

![](Selection-Style-images/Selection-Style-img1.jpeg)


## Selected Background

SelectedBackground property is used to customize the background color of the header when that tab item is selected and SelectionStyle=”CompleteHeader”. SelectedForeground has no effect when set in CompleteHeader selection style.

{% tabs %}

{% highlight XAML %}

<navigation:SfTabControl x:Name="tabControl" SelectionStyle="CompleteHeader">
<navigation:SfTabItem x:Name="paul" Header="Paul Vent"
                      Content="Description about Paul Vent"
					  SelectedBackground="Green" SelectedForeground="Red"/>

<navigation:SfTabItem Header="Niko" Content="Description about Niko"/>

<navigation:SfTabItem Header="James" Content="Description about James"/>

<navigation:SfTabItem Header="Carl" Content="Description about Carl"/>

</navigation:SfTabControl>

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

tabControl.SelectionStyle = Syncfusion.UI.Xaml.Controls.Navigation.SelectionStyle.CompleteHeader;

paul.SelectedBackground = new SolidColorBrush(Colors.Green);

paul.SelectedForeground = new SolidColorBrush(Colors.Red);

{% endhighlight %}

{% endtabs %}


![](Selection-Style-images/Selection-Style-img2.jpeg)


