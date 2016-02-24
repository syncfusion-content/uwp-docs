---
layout: post
title: Customize icon of SfRadialMenu for UWP
description: Customize icon of SfRadialMenu for UWP
platform: uwp
control: SfRadial Menu 
documentation: ug
---

# Icon  

The Icon property of the SfRadialMenu is used to customize the icon displayed in the center of RadialMenu circle.   

{% highlight xaml %}

<navigation:SfRadialMenu IsOpen="True" >

<navigation:SfRadialMenu.Icon>

                <Grid Background="White">

                    <Image Source="ms-appx:///Assets/text.png" Width="20"  

 	 	 	                Stretch="Uniform"/>

                </Grid>

            </navigation:SfRadialMenu.Icon>

 </navigation:SfRadialMenu>

{% endhighlight %}


![](Icon_images/Icon_img1.png)





