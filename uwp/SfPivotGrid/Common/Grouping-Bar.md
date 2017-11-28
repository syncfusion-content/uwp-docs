---
layout: post
title: Grouping Bar | SfPivotGrid | UWP | Syncfusion
description: Grouping Bar
platform: UWP
control: SfPivotGrid
documentation: ug
---

# Grouping Bar

Grouping Bar allows you to slice and dice the fields between column, row, value and filter areas. It allows you to add, re-arrange, or remove the fields to show the exact data that we want in SfPivotGrid. The following are the different kinds of grouping bar available in SfPivotGrid.

* **Filter Grouping Bar** holds the filter items of SfPivotGrid control.
* **Value Grouping Bar** holds the value items SfPivotGrid control.
* **Column Grouping Bar** holds the column items of SfPivotGrid control.
* **Row Grouping Bar** holds the row items of SfPivotGrid control.

By default, the grouping bar is disabled in SfPivotGrid control and it can be enabled by using the property of `ShowGroupingBar`. The following code snippet defines how to enable grouping bar.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfPivotGrid  x:Name="PivotGrid1" **ShowGroupingBar="True"**/>

{% endhighlight %}

{% highlight C# %}

this.PivotGrid1.ShowGroupingBar = true;

{% endhighlight %}

{% highlight vb %}

Me.PivotGrid1.ShowGroupingBar = True

{% endhighlight %}

{% endtabs %}

![](Grouping-Bar_images/grouping-bar.png)

## Grouping Bar Operations

Grouping bar allows to perform sorting, filtering and summarizing the data in the way that you want at run time. Each grouping bar item includes following components.

* A **caption** string to identify the content of the field.
* A **filter button** to filter the field values by end-users.
* A **sort indicator** to identify the sort order applied to field's values.
* A **remove button** to remove the corresponding field.

N> **Remarks:** Sorting and filtering operations are restricted for value items. Similarly, sorting operation cannot be performed for filter items.

**Filtering Operation**

The filtering operation of grouping bar can be enabled or disabled with the help of `EnableGroupingBarFiltering` property in SfPivotGrid. The following code snippet illustrates how to hide the filtering operation.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfPivotGrid  x:Name="PivotGrid1" ShowGroupingBar="True" **EnableGroupingBarFiltering="False"**/>

{% endhighlight %}

{% highlight C# %}

this.PivotGrid1.ShowGroupingBar = true;
this.PivotGrid1.EnableGroupingBarFiltering = false;

{% endhighlight %}

{% highlight vb %}

Me.PivotGrid1.ShowGroupingBar = True
Me.PivotGrid1.EnableGroupingBarFiltering = False

{% endhighlight %}

{% endtabs %}

![](Grouping-Bar_images/grouping-bar-without-filter-icon.png)

**Sorting Operation**

The sorting operation in grouping bar can be enabled or disabled by using the property of `EnableGroupingBarSorting` in SfPivotGrid. The below code snippet shows how to disable the sorting operation.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfPivotGrid  x:Name="PivotGrid1" EnableGroupingBarSorting="False"/>

{% endhighlight %}

{% highlight C# %}

this.PivotGrid1.EnableGroupingBarSorting = false;

{% endhighlight %}

{% highlight vb %}

Me.PivotGrid1.EnableGroupingBarSorting = False

{% endhighlight %}

{% endtabs %}

The following screen shots shows the SfPivotGrid without the sorting icons.

![](Grouping-Bar_images/grouping-bar-without-sort-icon.png)

**Removing Operation**

The removing operation can be disabled by setting the property of `EnableGroupingBarRemoving` to false as specified in the below code snippet. By default, it is true.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfPivotGrid  x:Name="PivotGrid1" ShowGroupingBar="True" EnableGroupingBarRemoving="False"/>

{% endhighlight %}

{% highlight C# %}

this.PivotGrid1.ShowGroupingBar = true;
this.PivotGrid1.EnableGroupingBarRemoving = false;

{% endhighlight %}

{% highlight vb %}

Me.PivotGrid1.ShowGroupingBar = True;
Me.PivotGrid1.EnableGroupingBarRemoving = False

{% endhighlight %}

{% endtabs %}

![](Grouping-Bar_images/grouping-bar-without-remove-icon.png)

## Grouping Bar Customization

**Grouping Bar Background**

You can customize the background color of grouping bar by using the property of `GroupingBarBackground` as specified in the following code snippet.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfPivotGrid  x:Name="PivotGrid1" ShowGroupingBar="True" **GroupingBarBackground="BurlyWood"**/>

{% endhighlight %}

{% highlight C# %}

this.PivotGrid1.ShowGroupingBar = true;
this.PivotGrid1.GroupingBarBackground = new SolidColorBrush(Colors.BurlyWood);

{% endhighlight %}

{% highlight vb %}

Me.PivotGrid1.ShowGroupingBar = True
Me.PivotGrid1.GroupingBarBackground = New SolidColorBrush(Colors.BurlyWood)

{% endhighlight %}

{% endtabs %}

![](Grouping-Bar_images/customized-groupingbar-background.png)

**Grouping Bar Item Background**

We can customize the background color of individual grouping bar items by defining the property of `GroupingBarItemBackground` in SfPivotGrid control.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfPivotGrid  x:Name="PivotGrid1" ShowGroupingBar="True" **GroupingBarItemBackground="BurlyWood"**/>

{% endhighlight %}

{% highlight C# %}

this.PivotGrid1.ShowGroupingBar = true;
this.PivotGrid1.GroupingBarItemBackground = new SolidColorBrush(Colors.BurlyWood);

{% endhighlight %}

{% highlight vb %}

Me.PivotGrid1.ShowGroupingBar = True
Me.PivotGrid1.GroupingBarItemBackground = New SolidColorBrush(Colors.BurlyWood)

{% endhighlight %}

{% endtabs %}

![](Grouping-Bar_Images/customized-grouping-bar-item-background.png)

## Disabling Specific Grouping Bar

SfPivotGrid provides support for disabling the grouping bar of specific area as illustrated below.

**Disabling Row Grouping Bar**

`EnableRowHeaderArea` property of SfPivotGrid allows to customize the visibility of grouping Bar in row header area. The following code snippet shows how to disable the row grouping bar.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfPivotGrid  x:Name="PivotGrid1" EnableRowHeaderArea="False"/>

{% endhighlight %}

{% highlight C# %}

this.PivotGrid1.EnableRowHeaderArea = false;

{% endhighlight %}

{% highlight vb %}

Me.PivotGrid1.EnableRowHeaderArea = False

{% endhighlight %}

{% endtabs %}

![](Grouping-Bar_images/customized-row-grouping-bar-disabled.png)

**Disabling Column Grouping Bar**

`EnableColumnHeaderArea` property of SfPivotGrid allows to customize the visibility of grouping Bar in column header area. The following code snippet shows how to disable the column grouping bar.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfPivotGrid  x:Name="PivotGrid1" EnableColumnHeaderArea="False"/>

{% endhighlight %}

{% highlight C# %}

this.PivotGrid1.EnableColumnHeaderArea = false;

{% endhighlight %}

{% highlight vb %}

Me.PivotGrid1.EnableColumnHeaderArea = False

{% endhighlight %}

{% endtabs %}

![](Grouping-Bar_images/customized-column-grouping-bar-disabled.png)

**Disabling Value Grouping Bar**

`EnableValueHeaderArea` property of SfPivotGrid allows to customize the visibility of grouping Bar in value header area. The following code snippet shows how to disable the value grouping bar.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfPivotGrid  x:Name="PivotGrid1" EnableValueHeaderArea="False"/>

{% endhighlight %}

{% highlight C# %}

this.PivotGrid1.EnableValueHeaderArea = false;

{% endhighlight %}

{% highlight vb %}

Me.PivotGrid1.EnableValueHeaderArea = False

{% endhighlight %}

{% endtabs %}

![](Grouping-Bar_images/customized-value-grouping-bar-disabled.png)

**Disabling Filter Grouping Bar**

`EnableFilterHeaderArea` property of SfPivotGrid allows to customize the visibility of grouping Bar in filter header area. The following code snippet shows how to disable the filter grouping bar.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfPivotGrid  x:Name="PivotGrid1" EnableFilterHeaderArea="False"/>

{% endhighlight %}

{% highlight C# %}

this.PivotGrid1.EnableFilterHeaderArea = false;

{% endhighlight %}

{% highlight vb %}

Me.PivotGrid1.EnableFilterHeaderArea = False

{% endhighlight %}

{% endtabs %}

![](Grouping-Bar_images/customized-filter-grouping-bar-disabled.png)

A demo sample is available at the following location.

{system drive}:\Users\&lt;User Name&gt;\AppData\Local\Syncfusion\EssentialStudio\&lt;Version Number&gt;\Samples\UWP\SampleBrowser\PivotGrid\PivotGrid\View\GroupingBar.xaml
