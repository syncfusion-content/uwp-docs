---
layout: post
title: populating color palette of SfRadialMenu control for UWP
description: populating color palette of SfRadialMenu control for UWP
platform: uwp
control: SfRadial Menu 
documentation: ug
---

# Populating Color Palette

Color Palette can be formed in SfRadialMenu with the Radial Color Items. 

{% highlight xaml %}

<navigation:SfRadialMenu IsOpen="True" >

    <navigation:SfRadialMenuItem Header="Font Color">



       <navigation:SfRadialMenuItem Header="Font"/>



       <navigation:SfRadialColorItem Color="Red">

           <navigation:SfRadialColorItem Color="DarkRed"/>

           <navigation:SfRadialColorItem Color="IndianRed"/>

           <navigation:SfRadialColorItem Color="OrangeRed"/>

           <navigation:SfRadialColorItem Color="MediumVioletRed"/>

       </navigation:SfRadialColorItem>

       <navigation:SfRadialColorItem Color="Green"/>

       <navigation:SfRadialColorItem Color="Blue"/>



     </navigation:SfRadialMenuItem>

</navigation:SfRadialMenu>

{% endhighlight %}

![](Populating-Color-Palette_images/Populating-Color-Palette_img1.png)







