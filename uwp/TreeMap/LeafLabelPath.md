---
layout: post
title: Leaf Label Path in UWP TreeMap | Syncfusion®
description: Leaf label path in the UWP TreeMap displays labels for leaf items and supports customization of label content for improved data visualization.
platform: uwp
control: SfTreeMap
documentation: ug
---

# Leaf Label Path in UWP TreeMap

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
