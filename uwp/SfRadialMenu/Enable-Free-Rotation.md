---
layout: post
title: Enable Free Rotation options of SfRadialMenu control for UWP
description: Enable Free Rotation options of SfRadialMenu control for UWP
platform: uwp
control: SfRadial Menu 
documentation: ug
---

# Enable Free Rotation

EnableFreeRotation property enable/disable rotation behavior of SfRadialMenu. 

{% tabs %}

{% highlight xaml %}

<navigation:SfRadialMenu x:Name="radialMenu"  EnableFreeRotation="False" IsOpen="True" />

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

radialMenu.EnableFreeRotation = false;

{% endhighlight %}

{% highlight VB %}

radialMenu.EnableFreeRotation = False

{% endhighlight %}

{% endtabs %}


