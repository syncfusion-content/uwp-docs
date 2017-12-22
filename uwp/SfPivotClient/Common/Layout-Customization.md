---
layout: post
title: Layout Customization | SfPivotClient | UWP | Syncfusion
description: Layout Customization
platform: UWP
control: SfPivotClient
documentation: ug
---

# Layout Customization

## Display mode

By default, the SfPivotClient displays both the grid and chart components. To view any one of the required components or to view both in the SfPivotClient, the `DisplayMode` property is used.

**Chart only**

To view the PivotChart alone in the SfPivotClient, the `DisplayMode` property should be set as `ChartOnly` like specified in the below code snippet.

{% tabs %}

{% highlight xaml %}

<pivotclient:SfPivotClient x:Name="PivotClient1" DisplayMode="ChartOnly" OlapDataManager="{Binding OlapDataManager}"/>

{% endhighlight %}

{% highlight c# %}

PivotClient1.DisplayMode = PivotClientDisplayMode.ChartOnly;

{% endhighlight %}

{% highlight vb %}

PivotClient1.DisplayMode = PivotClientDisplayMode.ChartOnly

{% endhighlight %}

{% endtabs %}

![](Layout-Customization_images/DisplayMode-chart.png)

**Grid only**

To view the PivotGrid alone in the SfPivotClient, the `DisplayMode` property should be set as `GridOnly` like specified in the below code snippet.

{% tabs %}

{% highlight xaml %}

<pivotclient:SfPivotClient x:Name="PivotClient1" DisplayMode="GridOnly" OlapDataManager="{Binding OlapDataManager}"/>

{% endhighlight %}

{% highlight c# %}

PivotClient1.DisplayMode = PivotClientDisplayMode.GridOnly;

{% endhighlight %}

{% highlight vb %}

PivotClient1.DisplayMode = PivotClientDisplayMode.GridOnly

{% endhighlight %}

{% endtabs %}

![](Layout-Customization_images/DisplayMode-grid.png)

**Both**

To view both the PivotGrid and PivotChart in the SfPivotClient, the `DisplayMode` property should be set as `Both` like shown in the below code snippet.

{% tabs %}

{% highlight xaml %}

<pivotclient:SfPivotClient x:Name="PivotClient1" DisplayMode="Both" OlapDataManager="{Binding OlapDataManager}"/>

{% endhighlight %}

{% highlight c# %}

PivotClient1.DisplayMode = PivotClientDisplayMode.Both;

{% endhighlight %}

{% highlight vb %}

PivotClient1.DisplayMode = PivotClientDisplayMode.Both

{% endhighlight %}

{% endtabs %}

![](Layout-Customization_images/DisplayMode-both.png)

A demo sample is available at the following location:

{system drive}:\Users\&lt;User Name&gt;\AppData\Local\Syncfusion\EssentialStudio\&lt;Version Number&gt;\Samples\UWP\SampleBrowser\PivotClient\PivotClient\View\Configuration.xaml