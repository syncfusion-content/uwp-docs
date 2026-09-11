---
layout: post
title: Quick Access Toolbar in UWP SfRibbon | Syncfusion®
description: The Quick Access Toolbar in SfRibbon groups the most commonly used commands, allowing easy access without searching through the menu bar.
platform: uwp
control: SfRibbon
documentation: ug
---

# Quick Access Toolbar in UWP Ribbon

The Quick Access Toolbar in the UWP Ribbon instance is used to group the most commonly used commands and access the commands easily without searching for them in the menu bar. The position of the QAT can also be moved above or below the UWP Ribbon dynamically.

## Add Default QAT Items

QAT items can be added as follows,

{% tabs %}

{% highlight xaml %}

<ribbon:SfRibbon x:Name="_ribbon" QATVisibility="Visible">

<ribbon:SfRibbon.QuickAccessToolBar>

<ribbon:QuickAccessToolBar DisplayItemsCount="3">

<Grid>

<StackPanel Orientation="Horizontal" x:Name="PART_QAT">

<ribbon:SfRibbonButton Icon="Assets/Undo.png">

</ribbon:SfRibbonButton>

<ribbon:SfRibbonButton Icon="Assets/Redo.png">

</ribbon:SfRibbonButton>

</StackPanel>

</Grid>

</ribbon:QuickAccessToolBar>

</ribbon:SfRibbon.QuickAccessToolBar>

{% endhighlight %}

{% endtabs %}

![QuickAccessToolbar showing default items](QuickAccessToolBar_images/QuickAccessToolBar_img1.jpeg)
