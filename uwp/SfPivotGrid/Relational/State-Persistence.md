---
layout: post
title: State Persistence | SfPivotGrid | UWP | Syncfusion
description: State Persistence
platform: UWP
control: SfPivotGrid
documentation: ug
---

# State Persistence

SfPivotGrid provides support to maintain the collapsed and expanded state of corresponding pivot item when it gets changed. This can be achieved by enabling the property of `StatePersistenceEnabled` in the SfPivotGrid control. Please refer the below code snippet to enable the state persistence:

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

![](State-Persistence_images/PivotGrid-with-state-persistence-enabled.png)

_SfPivotGrid with collapsed "Canada"_

![](State-Persistence_images/PivotGrid-with-state-persistence-enabled1.png)

_SfPivotGrid maintaining collapsed state of "Canada" after pivot change_