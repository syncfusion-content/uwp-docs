---
layout: post
title: Freeze Headers | SfPivotGrid | UWP | Syncfusion
description: freeze headers
platform: UWP
control: SfPivotGrid
documentation: ug
---

# Freeze Headers

SfPivotGrid provides built-in support to freeze the column and row headers. This is achieved by setting the `FreezeHeaders` property of SfPivotGrid to `true`.

Please refer the below code snippet to enable FreezeHeaders:

{% tabs %}

{% highlight xaml %}

<syncfusion:SfPivotGrid x:Name="PivotGrid1" **FreezeHeaders="True"**/>

{% endhighlight %}

{% highlight c# %}

// To freeze SfPivotGrid Headers
this.PivotGrid1.FreezeHeaders = true;

{% endhighlight %}

{% highlight vb %}

' To freeze SfPivotGrid Headers
Me.PivotGrid1.FreezeHeaders = True

{% endhighlight %}

{% endtabs %}

This is illustrated in the following screenshot:

![](Freeze-Headers_images/FreezeHeaders_image2.png)

A demo sample is available at the following location:

{system drive}:\Users\&lt;User Name&gt;\AppData\Local\Syncfusion\EssentialStudio\&lt;Version Number&gt;\Samples\UWP\SampleBrowser\PivotGrid\PivotGrid\View\GettingStarted.xaml