---
layout: post
title: DataBinding in UWP TreeMap control | Syncfusion
description: Learn here all about DataBinding support in Syncfusion UWP TreeMap (SfTreeMap) control and more.
platform: UWP
control: TreeMap
documentation: ug
---

# DataBinding in UWP TreeMap (SfTreeMap)

The SfTreeMap is bound to an external data source to display the data. It supports the data sources such as List, ObservableCollection, and so on. ItemsSource property helps to bind the TreeMap with the collection of objects.

In order to bind the data source of the SfTreeMap, set the `ItemsSource` property and to generate the treemap items set `WeightValuePath` as shown below

If the data source implements ICollectionChanged interface, then SfTreeMap will automatically refresh the view when an item is added, removed or while list cleared. When you add or remove an item in ObservableCollection, the SfTreeMap automatically refreshes the view as the ObservableCollection implements the INotifyCollectionChanged. But when you do the same in List, SfTreeMap will not refresh the view automatically.

If the data model implements the INotifyPropertyChanged interface, then the SfTreeMap responds to the property change in runtime to update the view. 

## WeightValuePath

`WeightValuePath` of SfTreeMap is a path to a field on the source object, which serve as the "weight" of the object.

The SfTreeMap generates treemap items based on the property `WeightValuePath` . It is a bindable property and it decides how to display the treemap items.

TreeMap calculates the size of the object with the help of `WeightValuePath`.

Code Sample:

{% highlight xaml %}

    <Grid Background="{ThemeResource ApplicationPageBackgroundThemeBrush}">
        <syncfusion:SfTreeMap Name="TreeMap" ItemsSource="{Binding PopulationDetails}" WeightValuePath="Population" >

        </syncfusion:SfTreeMap>
    </Grid>

{% endhighlight %}

N>  The specified field must be available in each and every sub class (object) defined in hierarchical (nested) data collection and it should be numerical value.

![treemapimage](GettingStarted_images/treemapimage.png)


## ColorValuePath

`ColorValuePath` of SfTreeMap is a path to a field on the source object, which serves as the "Color" of the object.

The SfTreeMap applying colors to the treemap nodes based on the property `ColorValuePath` . It is a bindable property and it decides how to Color the treemap node.


Code Sample:

{% highlight xaml %}

     <Grid Background="{ThemeResource ApplicationPageBackgroundThemeBrush}">
        <syncfusion:SfTreeMap Name="TreeMap" ItemsSource="{Binding PopulationDetails}" WeightValuePath="Population" ColorValuePath="Growth" >

        </syncfusion:SfTreeMap>
    </Grid>

{% endhighlight %}

N>  The specified field must be available in each and every sub class (object) defined in hierarchical (nested) data collection.

