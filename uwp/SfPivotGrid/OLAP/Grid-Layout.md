---
layout: post
title: Grid Layout | SfPivotGrid | UWP | Syncfusion
description: Grid Layout for SfPivotGrid with OLAP Data
platform: UWP
control: SfPivotGrid
documentation: ug
---

# Grid Layout

The position of summary cells in the SfPivotGrid can be customized with the help of `Layout` property. It can be positioned at the top or bottom of each parent member.

The following are the five different kinds of layouts supported by the SfPivotGrid:

* Normal Layout
* Excel Like Layout
* Normal Top Summary Layout
* No Summaries Layout

**Normal layout**

'Normal' layout is the default layout of SfPivotGrid in which the summary cells are positioned at the bottom of value cells. Refer the below code snippet to customize the grid layout:

{% tabs %}

{% highlight xaml %}

<syncfusion:SfPivotGrid x:Name="PivotGrid1" Layout="Normal"
                        OlapDataManager="{Binding OlapDataManager}">
</syncfusion:SfPivotGrid>

{% endhighlight %}

{% highlight c# %}

this.PivotGrid1.Layout = GridLayout.Normal;

{% endhighlight %}

{% highlight vb %}

Me.PivotGrid1.Layout = GridLayout.Normal

{% endhighlight %}

{% endtabs %}

![](Grid-Layouts_images/Grid-Layouts_img1.png)

**Excel like layout**

In the 'Excel-Like' layout, the summary cells are positioned at the bottom alone and the child members appear below the parent member with some indent space.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfPivotGrid x:Name="PivotGrid1" Layout="ExceLikeLayout"
                        OlapDataManager="{Binding OlapDataManager}">
</syncfusion:SfPivotGrid>

{% endhighlight %}

{% highlight c# %}

this.PivotGrid1.Layout = GridLayout.ExcelLikeLayout;

{% endhighlight %}

{% highlight vb %}

Me.PivotGrid1.Layout = GridLayout.ExcelLikeLayout

{% endhighlight %}

{% endtabs %}

![](Grid-Layouts_images/Grid-Layouts_img2.png)

**Normal top summary layout**

In 'Normal Top Summary' layout, the summary cells are positioned at the top of each parent member and the child members appear adjacent to it.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfPivotGrid x:Name="PivotGrid1" Layout="NormalTopSummary"
                        OlapDataManager="{Binding OlapDataManager}">
</syncfusion:SfPivotGrid>

{% endhighlight %}

{% highlight c# %}

this.PivotGrid1.Layout = GridLayout.NormalTopSummary;

{% endhighlight %}

{% highlight vb %}

Me.PivotGrid1.Layout = GridLayout.NormalTopSummary

{% endhighlight %}

{% endtabs %}

![](Grid-Layouts_images/Grid-Layouts_img3.png)

**No summaries layout**

In 'No Summaries' layout, the summary cells can be hidden and the child members can be appeared adjacent to the parent member.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfPivotGrid x:Name="PivotGrid1" Layout="NoSummaries"
                        OlapDataManager="{Binding OlapDataManager}">
</syncfusion:SfPivotGrid>

{% endhighlight %}

{% highlight c# %}

this.PivotGrid1.Layout = GridLayout.NoSummaries;

{% endhighlight %}

{% highlight vb %}

Me.PivotGrid1.Layout = GridLayout.NoSummaries

{% endhighlight %}

{% endtabs %}

![](Grid-Layouts_images/Grid-Layouts_img4.png)

A demo sample is available at the following location:

{system drive}:\Users\&lt;User Name&gt;\AppData\Local\Syncfusion\EssentialStudio\&lt;Version Number&gt;\Samples\UWP\SampleBrowser\PivotGrid\PivotGrid\View\GridLayout.xaml
