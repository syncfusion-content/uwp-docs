---
layout: post
title: Deals with Spin Button Alignment options of SfDomainUpDown control for UWP
description: Deals with Spin Button Alignment options of SfDomainUpDown control for UWP
platform: uwp
control: SfDomainUpDown
documentation: ug
---

# Spin Button Alignment

The spin button’s position in the SfDomainUpDown control can be changed using SpinButtonsAlignment. It contains three modes for positioning spin buttons:

1. Right
2. Left
3. Both



## Right

Spin buttons will be aligned on the right side of the control.

{% tabs %}

{% highlight xaml %}



<editors:SfDomainUpDown x:Name="domainUpDown"

                               HorizontalAlignment="Center"

                               VerticalAlignment="Center"

                               Width="200" 

SpinButtonsAlignment="Right"

                              ItemsSource="{Binding Employees}">

 </editors:SfDomainUpDown>
{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

domainUpDown.SpinButtonsAlignment = Syncfusion.UI.Xaml.Controls.SpinButtonsAlignment.Right;

{% endhighlight %}

{% highlight VB %}

domainUpDown.SpinButtonsAlignment = Syncfusion.UI.Xaml.Controls.SpinButtonsAlignment.Right

{% endhighlight %}

{% endtabs %}

![](Features_images/Features_img3.png)



## Left

Spin buttons will be aligned on the left side of the control.

{% tabs %}

{% highlight xaml %}



<editors:SfDomainUpDown x:Name="domainUpDown"

                               HorizontalAlignment="Center"

                               VerticalAlignment="Center"

                               Width="200" 

SpinButtonsAlignment="Left"

                              ItemsSource="{Binding Employees}">        </editors:SfDomainUpDown>

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

domainUpDown.SpinButtonsAlignment = Syncfusion.UI.Xaml.Controls.SpinButtonsAlignment.Left;

{% endhighlight %}

{% highlight VB %}

domainUpDown.SpinButtonsAlignment = Syncfusion.UI.Xaml.Controls.SpinButtonsAlignment.Left

{% endhighlight %}

{% endtabs %}

![](Features_images/Features_img4.png)



## Both

The spin button’s decrement button will be aligned on the left side of the control and the increment button will be aligned on the right side of the control.

{% tabs %}

{% highlight xaml %}

<editors:SfDomainUpDown x:Name="domainUpDown"

                               HorizontalAlignment="Center"

                               VerticalAlignment="Center"

                               Width="200" 

SpinButtonsAlignment="Both"

                              ItemsSource="{Binding Employees}">        </editors:SfDomainUpDown>          

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

domainUpDown.SpinButtonsAlignment = Syncfusion.UI.Xaml.Controls.SpinButtonsAlignment.Both;

{% endhighlight %}

{% highlight VB %}

domainUpDown.SpinButtonsAlignment = Syncfusion.UI.Xaml.Controls.SpinButtonsAlignment.Both

{% endhighlight %}

{% endtabs %}

![](Features_images/Features_img5.png)