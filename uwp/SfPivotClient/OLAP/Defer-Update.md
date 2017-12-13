---
layout: post
title: Defer Update | SfPivotClient | UWP | Syncfusion
description: Defer Update
platform: UWP
control: SfPivotClient
documentation: ug
---

# Defer Update

Defer update support allows users to refresh the control on-demand and not during every user interaction. To enable on-demand refreshing of data, the `EnableAutoExecute` property must be set to false. If this support is enabled, the *Auto Execute* button ![](Defer-Update_images/Defer-update-icon.png) will be appeared on SfPivotClient's toolbar. To enable the defer update support, you can make use of the following code snippet.

{% tabs %}

{% highlight xaml %}

<pivotclient:SfPivotClient x:Name="PivotClient1" EnableAutoExecute="False" OlapDataManager="{Binding OlapDataManager}"/>

{% endhighlight %}

{% highlight c# %}

PivotClient1.EnableAutoExecute = false;

{% endhighlight %}

{% highlight vb %}

PivotClient1.EnableAutoExecute = False

{% endhighlight %}

{% endtabs %}

![](Defer-Update_images/PivotClient-defer-update-button.png)

N> If the defer update support is enabled, SfPivotClient control will not be updated for any UI interactions and the OlapReport gets updated in the back-end to maintain the actions done so far. To update the SfPivotClient, the *Auto Execute* button has to be clicked manually and so, the SfPivotClient control will be refreshed based on the OlapReport available at that instant.

A demo sample is available at the following location.

{system drive}:\Users\&lt;User Name&gt;\AppData\Local\Syncfusion\EssentialStudio\&lt;Version Number&gt;\Samples\UWP\SampleBrowser\PivotClient\PivotClient\View\DeferUpdate.xaml