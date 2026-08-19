---
layout: post
title: Freeze Headers in UWP Pivot Grid | Syncfusion®
description: Freeze Headers in Syncfusion® UWP Pivot Grid control keeps row and column headers visible during scrolling to improve readability and navigation.
platform: uwp
control: Pivot Grid
documentation: ug
---

# Freeze Headers in UWP Pivot Grid

The SfPivotGrid provides built-in support to freeze the column and row headers. This can be achieved by setting the `FreezeHeaders` property of SfPivotGrid to `true`.

Refer to the following code snippet to enable FreezeHeaders.

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

This is illustrated in the following screenshot.

![FreezeHeaders_image2](Freeze-Headers_images/FreezeHeaders_image2.png)

A demo sample is available in the following location.

{system drive}:\Users\&lt;User Name&gt;\AppData\Local\Syncfusion\EssentialStudio\&lt;Version Number&gt;\Samples\UWP\SampleBrowser\PivotGrid\PivotGrid\View\GettingStarted.xaml
