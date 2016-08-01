---
layout: post
title: Highlighting Support in TreeMap control
description: Highlighting Support
platform: UWP
control: TreeMap
documentation: ug
---

# Highlighting Support

While selecting a leaf node, you can highlight it by setting `HighlightOnSelection` property of SfTreeMap to “True”. The border of highlight on selection can be customized by HighlightBorderBrush and HighlightBorderThickness properties of SfTreeMap.

Code Sample:

{% highlight xaml %}

    <syncfusion:SfTreeMap ItemsSource="{Binding PopulationDetails}"

                      WeightValuePath="Population" ColorValuePath="Growth"

                      HighlightOnSelection="True" 

                      HighlightBorderBrush="Yellow" 

                      HighlightBorderThickness="5">

    <syncfusion:SfTreeMap.Levels>

        <syncfusion:TreeMapFlatLevel GroupPath="Continent" GroupGap="10"/>

    </syncfusion:SfTreeMap.Levels>

    </syncfusion:SfTreeMap>

{% endhighlight %}