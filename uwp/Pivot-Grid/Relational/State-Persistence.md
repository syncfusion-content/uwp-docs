---
layout: post
title: State Persistence in UWP Pivot Grid control | Syncfusion
description: Learn here all about State Persistence support in Syncfusion UWP Pivot Grid (SfPivotGrid) control and more.
platform: UWP
control: SfPivotGrid
documentation: ug
---

# State Persistence in UWP Pivot Grid (SfPivotGrid)

The SfPivotGrid supports maintaining the collapsed and expanded state of the corresponding pivot item when it gets changed. This can be achieved by enabling the `StatePersistenceEnabled` property in the SfPivotGrid control. Refer to the following code snippet to enable the state persistence.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfPivotGrid x:Name="PivotGrid1" StatePersistenceEnabled="True"/>

{% endhighlight %}

{% highlight C# %}

PivotGrid1.StatePersistenceEnabled = true;

{% endhighlight %}

{% highlight vb %}

PivotGrid1.StatePersistenceEnabled = True

{% endhighlight %}

{% endtabs %}

![PivotGrid-with-state-persistence-enabled](State-Persistence_images/PivotGrid-with-state-persistence-enabled.png)

_SfPivotGrid with collapsed "Canada"_

![PivotGrid-with-state-persistence-enabled1](State-Persistence_images/PivotGrid-with-state-persistence-enabled1.png)

_SfPivotGrid maintaining collapsed state of "Canada" after pivot change_
