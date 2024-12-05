---
layout: post
title: Localization in UWP Diagram control | Syncfusion®
description: Learn here all about Localization support in the Syncfusion® UWP Diagram (SfDiagram) control and more.
platform: uwp
control: SfDiagram
documentation: ug
---

# Localization in UWP Diagram (SfDiagram)

Localization is the process of providing controls in different cultures to help you set your own culture easily. Diagram provides localization support for Context Menu items.

## Customizing Context Menu

![Localizing context menu](Localization_images/Localization_img1.jpeg)

The following code illustrates how to provide localization support for Context Menu items.

{% highlight C# %}

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
