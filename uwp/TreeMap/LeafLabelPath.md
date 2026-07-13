---
layout: post
title: LeafLabelPath in UWP TreeMap control | Syncfusion
description: Learn here all about LeafLabelPath support in Syncfusion UWP TreeMap (SfTreeMap) control and more.
platform: uwp
control: SfTreeMap
documentation: ug
---

# LeafLabelPath in UWP TreeMap (SfTreeMap)

LeafLabelPath of SfTreeMap is a path to a field on the source object, which serves as the "label" of the object.

Code Sample:

{% highlight xaml %}

<Grid Background="{StaticResource ApplicationPageBackgroundThemeBrush}">

    <Grid.DataContext>

        <local:PopulationViewModel/>

    </Grid.DataContext>

    <syncfusion:SfTreeMap ItemsSource="{Binding PopulationDetails}"
                          LeafLabelPath="Country"/>

</Grid>
	
{% endhighlight %}

N> The specified field must be available in each and every sub class (object) defined in hierarchical (nested) data collection.
