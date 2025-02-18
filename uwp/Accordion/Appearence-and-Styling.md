---
layout: post
title: Appearance and Styling in UWP Accordion control | Syncfusion®
description: Learn here all about Appearance and Styling support in Syncfusion® UWP Accordion (SfAccordion) control and more.
platform: UWP
control: SfAccordion
documentation: ug

---

# Appearance and Styling in UWP Accordion (SfAccordion)

`AccentBrush` property is used to decorate the hot spots of a control with a solid color

{% tabs %}

{% highlight XAML %}

<layout:SfAccordion HorizontalAlignment="Center"

VerticalAlignment="Center"            

DisplayMemberPath="Name" 

AccentBrush="Green"

ItemsSource="{Binding Employees}" />

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

accordion.AccentBrush = new SolidColorBrush() { Color = Windows.UI.Colors.Red };

{% endhighlight %}

{% highlight VB %}

accordion.AccentBrush = New SolidColorBrush() With {.Color = Windows.UI.Colors.Red}

{% endhighlight %}

{% endtabs %}

![appearence-and-styling-img1](Appearence-and-Styling-images/appearence-and-styling-img1.jpeg)


## Customizing SfAccordion Item

`ItemContainerStyle` property is used to define the style for SfAccordionItems.

{% tabs %}

{% highlight XAML %}

<layout:SfAccordion SelectionMode="OneOrMore">

<layout:SfAccordion.ItemContainerStyle>

<Style TargetType="layout:SfAccordionItem">

<Setter Property="Background" Value="CornflowerBlue"/>

</Style>

</layout:SfAccordion.ItemContainerStyle>

<layout:SfAccordionItem Header="WPF"
                        Content="Essential Studio for WPF"/>

<layout:SfAccordionItem Header="Silverlight"
                        Content="Essential Studio for Silverlight"/>
						
<layout:SfAccordionItem Header="WinRT"
                        Content="Essential Studio for WinRT"/>
						
<layout:SfAccordionItem Header="Windows Phone"
                        Content="Essential Studio for Windows Phone"/>
						
<layout:SfAccordionItem Header="Universal"
                        Content="Essential Studio for Universal"/>
						
</layout:SfAccordion>

{% endhighlight %}

{% endtabs %}

![appearence-and-styling-img2](Appearence-and-Styling-images/appearence-and-styling-img2.jpeg)

## Customizing Accordion Button

`AccordionButtonStyle` property is used to style the expander button which contains the header and expander button.

