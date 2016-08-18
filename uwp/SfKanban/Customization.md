---
layout: post
title: Getting Started | SfKanban | uwp | Syncfusion
description: getting started
platform: uwp
control: SfKanban
documentation: ug
---
# Customization

KanbanCardStyle – It is used to customize the Kanban cards.

{% highlight xml %}

<syncfusion:SfKanban.CardStyle>

<syncfusion:KanbanCardStyle Foreground="DarkBlue"

Stroke="Green"

StrokeThickness="1.25"

FontSize="13"

TitleColor="Black"

TitleFontSize="15"

CornerRadius="10"

TitleHorizontalAlignment="Center"

Background="#FFEEEEEE">

</syncfusion:KanbanCardStyle>

</syncfusion:SfKanban.CardStyle>

{% endhighlight %}

![](SfKanban_images/SfKanban_img12.png)


PlaceHolderStyle – It is used to customize the place holder of Kanban cards.

{% highlight xml %}

<syncfusion:SfKanban.PlaceholderStyle>

<syncfusion:PlaceholderStyle CategoryHoverBrush="DarkGray" 

Fill="LightGray"

Stroke="Black" 

StrokeDashArray="4,4"

StrokeThickness="2"

Foreground="DarkBlue">

</syncfusion:PlaceholderStyle>

</syncfusion:SfKanban.PlaceholderStyle>

{% endhighlight %}

![](SfKanban_images/SfKanban_img13.png)


Category hover brush – Indicates the color, when hover on any category of multiple categories in a single column as shown in the below snapshot.

![](SfKanban_images/SfKanban_img14.png)