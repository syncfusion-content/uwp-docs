---
layout: post
title: Appearance and Styling in UWP Radial Menu control | Syncfusion
description: Learn here all about Appearance and Styling support in Syncfusion UWP Radial Menu (SfRadialMenu) control and more.
platform: uwp
control: SfRadial Menu 
documentation: ug
---

# Appearance and Styling in UWP Radial Menu (SfRadialMenu)

## Radius 

RadiusX and RadiusY properties in the SfRadialMenu can be used to define the X and Y axis radius to render the control. 

{% tabs %}

{% highlight xaml %}

<navigation:SfRadialMenu x:Name="radialMenu" RadiusX="150" RadiusY="150" />

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight c# %}

 radialMenu.RadiusX = 150;
 radialMenu.RadiusY = 150;
 
{% endhighlight %}

{% highlight VB %}

radialMenu.RadiusX = 150
radialMenu.RadiusY = 150
 
{% endhighlight %}

{% endtabs %}

## CenterRimRadiusFactor

CenterRimRadiusFactor property can be used to define the radius of the center rim (inner circle). 

{% tabs %}

{% highlight xaml %}

<navigation:SfRadialMenu x:Name="radialMenu"  CenterRimRadiusFactor="0.3" IsOpen="True" />

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight c# %}

 radialMenu.CenterRimRadiusFactor = 0.3;
 
{% endhighlight %}

{% highlight VB %}

radialMenu.CenterRimRadiusFactor = 0.3
 
{% endhighlight %}

{% endtabs %}

![RadialMenu Center RimRadius Factor view](Appearance-and-Styling_images/Appearance-and-Styling_img1.png)

## RimBackground

RimBackground property used to fill the outer rim (outer circle).

{% tabs %}

{% highlight xaml %}

<navigation:SfRadialMenu x:Name="radialMenu"  IsOpen="True" RimBackground="Green" />

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight c# %}

 radialMenu.RimBackground = new SolidColorBrush(Colors.Green);
 
{% endhighlight %}

{% highlight VB %}

radialMenu.RimBackground = New SolidColorBrush(Colors.Green)

{% endhighlight %}

{% endtabs %}


![RadialMenu RimBackground view](Appearance-and-Styling_images/Appearance-and-Styling_img2.png)


## RimActiveBrush

RimActiveBrush property used to fill the expander rim and this expander rim only visible when the items have sub items.   

{% tabs %}

{% highlight xaml %}

<navigation:SfRadialMenu x:Name="radialMenu" RimActiveBrush="Red" RimBackground="Green" IsOpen="True" />

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight c# %}

 radialMenu.RimActiveBrush = new SolidColorBrush(Colors.Red);
 
{% endhighlight %}

{% highlight VB %}

radialMenu.RimActiveBrush = New SolidColorBrush(Colors.Red)

{% endhighlight %}

{% endtabs %}

![RadialMenu RimActiveBrush view](Appearance-and-Styling_images/Appearance-and-Styling_img3.png)



## RimRadiusFactor

RimRadiusFactor property of SfRadialMenu can be used to set the radius of the items panel. Lowest values to this factor increases the thickness of the outer rim. Highest values to this factor decreases the thickness of the outer rim. 

{% tabs %}

{% highlight xaml %}

<navigation:SfRadialMenu x:Name="radialMenu" RimActiveBrush="Red" RimRadiusFactor="0.7" RimBackground="Green"   IsOpen="True" />

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight c# %}

 radialMenu.RimRadiusFactor = 0.7 ;
 
{% endhighlight %}

{% highlight VB %}

radialMenu.RimRadiusFactor = 0.7 

{% endhighlight %}

{% endtabs %}

![RadialMenu RimRadiusFactor view](Appearance-and-Styling_images/Appearance-and-Styling_img5.png)


## Navigation Button Style

The navigation button displayed in the center of SfRadialMenu can be styled using NavigationButtonStyle property. 

{% tabs %}

{% highlight xaml %}

<syncfusion:SfRadialMenu NavigationButtonStyle="{StaticResource NavigationButtonStyle}"

IsOpen="True" />

{% endhighlight %}

{% endtabs %}

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

{% endtabs %}

{% tabs %}

{% highlight c# %}

radialMenu.DrillDownItem = edit;

{% endhighlight %}

{% highlight VB %}

radialMenu.DrillDownItem = edit

{% endhighlight %}

{% endtabs %}

![RadialMenu DrillDownItem view](Appearance-and-Styling_images/Appearance-and-Styling_img6.png)




