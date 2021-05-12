---
layout: post
title: Layout Customization in UWP Pivot Client control | Syncfusion
description: Learn here all about Layout Customization support in Syncfusion UWP Pivot Client (SfPivotClient) control and more.
platform: UWP
control: SfPivotClient
documentation: ug
---

# Layout Customization in UWP Pivot Client (SfPivotClient)

## Display mode

By default, the SfPivotClient displays both the grid and chart components. To view any one of the required components or to view both in the SfPivotClient, the `DisplayMode` property is used.

**Chart only**

To view the pivot chart alone in the SfPivotClient, the `DisplayMode` property should be set to `ChartOnly` as specified in the following code snippet.

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

![DisplayMode-chart](Layout-Customization_images/DisplayMode-chart.png)

**Grid only**

To view the pivot grid alone in the SfPivotClient, the `DisplayMode` property should be set to `GridOnly` as specified in the following code snippet.

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

![DisplayMode-grid](Layout-Customization_images/DisplayMode-grid.png)

**Both**

To view both the pivot grid and pivot chart in the SfPivotClient, the `DisplayMode` property should be set to `Both` as shown in the following code snippet.

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

![DisplayMode-both](Layout-Customization_images/DisplayMode-both.png)

A demo sample is available in the following location.

{system drive}:\Users\&lt;User Name&gt;\AppData\Local\Syncfusion\EssentialStudio\&lt;Version Number&gt;\Samples\UWP\SampleBrowser\PivotClient\PivotClient\View\Configuration.xaml
