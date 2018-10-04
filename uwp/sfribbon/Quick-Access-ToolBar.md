---
layout: post
title: Access frequently used commands easily using Ribbon QAT
description: Access frequently used commands easily using Ribbon QAT
platform: uwp
control: SfRibbon (Touch Ribbon)
documentation: ug
---

# QuickAccessToolBar

Quick Access Toolbar in the ribbon instance is used to group the most commonly used commands and access the commands easily without searching for the command in the menu bar. Also position of QAT can be moved above or below to the ribbon dynamically

## Add Default QAT Items


QAT items can be added as follows,

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

![D:/sugapriyadocumentation/images/sfribbon/Getting-Started_img5.png](QuickAccessToolBar_images/QuickAccessToolBar_img1.jpeg)


