---
layout: post
title: Appearence and Styling of SfCalculator control for UWP
description: Appearence and Styling of SfCalculator control for UWP
platform: UWP
control: SfCalculator
documentation: ug
---

# Appearance and Styling

All the panes in SfCalculator can be customized easily. The panes can be styled as follows:

* FunctionsPaneStyle 
* DisplayPaneStyle
* InputPane Style

## FunctionsPane Style

Function pane is the panel containing number buttons and mathematical symbols. It can be styled using FunctionsPaneStyle property.

{% tabs %}

{% highlight XAML %}

<Style TargetType="input:FunctionsPane">

<Setter Property="Foreground" Value="Red"/>

</Style>       

{% endhighlight %}

{% endtabs %}

## DisplayPane Style

Display pane is the panel that contain elements displaying value and expression. It can be styled as follows.

{% tabs %}

{% highlight XAML %}

<Style TargetType="input:DisplayPane">

<Setter Property="Foreground" Value="Red"/>

<Setter Property="FontSize" Value="20"/>

</Style>

{% endhighlight %}

{% endtabs %}

![](SfCalculator-images/SfCalculator-img8.jpeg)

## InputPane Style

Input pane is a panel in SfCalulator that contains number buttons. It can be styled as follows.

{% tabs %}

{% highlight XAML %}

<Style TargetType="input:DisplayPane">

<Setter Property="Foreground" Value="Red"/>
   
<Setter Property="FontSize" Value="20"/>
   
</Style>


{% endhighlight %}

{% endtabs %}

![](SfCalculator-images/SfCalculator-img9.jpeg)