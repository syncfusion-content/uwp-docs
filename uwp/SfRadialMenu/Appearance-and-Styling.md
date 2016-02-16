---
layout: post
title: Appearance and Styling of Syncfusion SfRadialMenu  control for UWP
description: Appearance and Styling of Syncfusion SfRadialMenu  control for UWP 
platform: uwp
control: SfRadial Menu 
documentation: ug
---

# Appearance and Styling 

## Radius 

RadiusX and RadiusY properties in the SfRadialMenu can be used to define the X and Y axis radius to render the control. 

{% highlight xaml %}



<navigation:SfRadialMenu RadiusX="150" RadiusY="150" />

{% endhighlight %}

## CenterRimRadiusFactor

CenterRimRadiusFactor property can be used to define the radius of the center rim (inner circle). 

{% highlight xaml %}



<navigation:SfRadialMenu   CenterRimRadiusFactor="0.3" IsOpen="True" />

{% endhighlight %}

![](Appearance-and-Styling_images/Appearance-and-Styling_img1.png)

## RimBackground

RimBackground property used to fill the outer rim (outer circle).

{% highlight xaml %}

<navigation:SfRadialMenu IsOpen="True" RimBackground="Green" />

{% endhighlight %}


![](Appearance-and-Styling_images/Appearance-and-Styling_img2.png)


## RimActiveBrush

RimActiveBrush property used to fill the expander rim and this expander rim only visible when the items have sub items.   

{% highlight xaml %}

<navigation:SfRadialMenu RimActiveBrush="Red" RimBackground="Green" IsOpen="True" />

{% endhighlight %}


![](Appearance-and-Styling_images/Appearance-and-Styling_img3.png)



## RimRadiusFactor

RimRadiusFactor property of SfRadialMenu can be used to set the radius of the items panel. Lowest values to this factor increases the thickness of the outer rim. Highest values to this factor decreases the thickness of the outer rim. 

{% highlight xaml %}

<navigation:SfRadialMenu RimActiveBrush="Red" RimRadiusFactor="0.7" RimBackground="Green"   IsOpen="True" />

{% endhighlight %}


![](Appearance-and-Styling_images/Appearance-and-Styling_img5.png)


## Navigation Button Style

The navigation button displayed in the center of SfRadialMenu can be styled using NaviationButtonStyle property. 

{% highlight xaml %}

<syncfusion:SfRadialMenu NavigationButtonStyle="{StaticResource NavigationButtonStyle}"

IsOpen="True" />

{% endhighlight %}


## Editing SubMenu Items Programmatically

With the DrillDownItem property, you can access and edit submenu items of SfRadialMenu at various hierarchy levels programmatically. The following code example and screen shot illustrate this.
{% tabs %}
{% highlight xaml %}

<Page xmlns:navigation="using:Syncfusion.UI.Xaml.Controls.Navigation">

     <Grid Background="{StaticResource ApplicationPageBackgroundThemeBrush}">

<navigation:SfRadialMenu  x:Name="radialmenu">

<navigation:SfRadialMenuItem Header="Edit" x:Name="edit">

<navigation:SfRadialMenuItem Header="Cut"/>

<navigation:SfRadialMenuItem Header="Copy"/>

<navigation:SfRadialMenuItem Header="Paste"/>

</navigation:SfRadialMenuItem>

<navigation:SfRadialMenuItem Header="Bold"/>

<navigation:SfRadialMenuItem Header="Italics"/>

<navigation:SfRadialMenuItem Header="Underline"/>

</navigation:SfRadialMenu>

     </Grid>

</Page>

{% endhighlight %}
{% highlight c# %}

radialmenu.DrillDownItem = edit;

{% endhighlight %}
{% endtabs %}

![](Appearance-and-Styling_images/Appearance-and-Styling_img6.png)




