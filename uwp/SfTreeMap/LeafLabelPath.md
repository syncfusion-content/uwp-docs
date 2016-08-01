---
layout: post
title: LeafLabelPath in TreeMap control
description: LeafLabelPath
platform: UWP
control: TreeMap
documentation: ug
---

# LeafLabelPath

LeafLabelPath of SfTreeMap is a path to a field on the source object, which serves as the "label" of the object.

Code Sample:

{% highlight xaml %}

    <Grid Background="{StaticResource ApplicationPageBackgroundThemeBrush}">

        <Grid.DataContext>

            <local:PopulationViewModel/>

        </Grid.DataContext>

        <syncfusion:SfTreeMap ItemsSource="{Binding PopulationDetails}" 

                              LeafLabelPath="Country”/>

    </Grid>
	
{% endhighlight %}

N>  The specified field must be available in each and every sub class (object) defined in hierarchical (nested) data collection.
