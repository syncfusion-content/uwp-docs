---
layout: post
title: ColorValuePath in TreeMap control
description: ColorValuePath
platform: UWP
control: TreeMap
documentation: ug
---

# ColorValuePath

ColorValuePath ofSfTreeMap is a path to a field on the source object, which serves as the "color" of the object. 

Code Sample:

{% highlight xml %}

      <Grid Background="{StaticResource ApplicationPageBackgroundThemeBrush}">

	<Grid.DataContext>

		<local:PopulationViewModel/>

	</Grid.DataContext>

	<syncfusion:SfTreeMap ItemsSource="{Binding PopulationDetails}" ColorValuePath="Growth"/>

    </Grid>

{% endhighlight %}

N>  The specified field must be available in each and every sub class (object) defined in hierarchical (nested) data collection.
