---
layout: post
title: Localization in UWP SfDiagram | Syncfusion®
description: Learn about localization in the Syncfusion® UWP SfDiagram control, including customizing and localizing context menu items for different cultures.
platform: uwp
control: SfDiagram
documentation: ug
---

# Localization in UWP SfDiagram

Localization is the process of providing controls in different cultures to help you set your own culture easily. Diagram provides localization support for Context Menu items.

## Customizing Context Menu

![Localizing context menu](Localization_images/Localization_img1.jpeg)

The following code illustrates how to provide localization support for Context Menu items.

{% highlight c# %}

//Sets the Culture 
System.Threading.Thread.CurrentThread.CurrentUICulture = new System.Globalization.CultureInfo("fr");//French

System.Resources.ResourceManager manager;

//Sets the Assembly
Assembly assembly = Application.Current.GetType().Assembly;

manager = new System.Resources.ResourceManager("Localization.Resources.Syncfusion.SfDiagram.UWP", 
          assembly);

{% endhighlight %}

![Node with localized context menu](Localization_images/Localization_img2.jpeg)

N> You have to define the textual descriptions of the context menu items for your custom cultures.
