---
layout: post
title: Appearance and Styling in UWP SfCalculator | Syncfusion®
description: The appearance and styling in SfCalculator allows customizing the visual look of all panes using FunctionsPaneStyle, DisplayPaneStyle, and other properties.
platform: uwp
control: SfCalculator
documentation: ug
---

# Appearance and Styling in UWP SfCalculator

All the panes in SfCalculator can be customized easily. The panes can be styled as follows:

* FunctionsPaneStyle 
* DisplayPaneStyle
* InputPane Style

## Customizing functions panel

Function pane is the panel containing number buttons and mathematical symbols. It can be styled using FunctionsPaneStyle property.

{% tabs %}

{% highlight XAML %}

<Style TargetType="input:FunctionsPane">

<Setter Property="Foreground" Value="Red"/>

</Style>       

{% endhighlight %}

{% endtabs %}

## Customizing display panel

Display pane is the panel that contain elements displaying value and expression. It can be styled as follows.

{% tabs %}

{% highlight XAML %}

<Style TargetType="input:DisplayPane">

<Setter Property="Foreground" Value="Red"/>

<Setter Property="FontSize" Value="20"/>

</Style>

{% endhighlight %}

{% endtabs %}

![SfCalculator-images8](SfCalculator-images/SfCalculator-img8.jpeg)

## Customizing input panel

Input pane is a panel in SfCalculator that contains number buttons. It can be styled as follows.

{% tabs %}

{% highlight XAML %}

<Style TargetType="input:DisplayPane">

<Setter Property="Foreground" Value="Red"/>
   
<Setter Property="FontSize" Value="20"/>
   
</Style>


{% endhighlight %}

{% endtabs %}

![SfCalculator-images9](SfCalculator-images/SfCalculator-img9.jpeg)