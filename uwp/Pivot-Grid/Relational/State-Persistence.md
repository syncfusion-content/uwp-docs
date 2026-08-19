---
layout: post
title: State Persistence in UWP Pivot Grid | Syncfusion®
description: State Persistence in Syncfusion® UWP Pivot Grid control preserves collapsed or expanded states of pivot items when schema changes using StatePersistenceEnabled.
platform: uwp
control: Pivot Grid
documentation: ug
---

# State Persistence in UWP Pivot Grid

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
