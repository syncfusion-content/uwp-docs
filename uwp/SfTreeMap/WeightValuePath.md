---
layout: post
title: WeightValuePath in TreeMap control
description: WeightValuePath
platform: UWP
control: TreeMap
documentation: ug
---

# WeightValuePath

WeightValuePath ofSfTreeMap is a path to a field on the source object, which serve as the "weight" of the object. 

Code Sample:

{% highlight xml %}

    <Grid Background="{StaticResource ApplicationPageBackgroundThemeBrush}">

        <Grid.DataContext>

            <local:PopulationViewModel/>

        </Grid.DataContext>

        <syncfusion:SfTreeMap ItemsSource="{Binding PopulationDetails}" 

                              WeightValuePath="Population”/>

    </Grid>

{% endhighlight %}

N>  The specified field must be available in each and every sub class (object) defined in hierarchical (nested) data collection.
