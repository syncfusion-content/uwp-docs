---
layout: post
title: Getting Started | SfKanban | uwp | Syncfusion
description: getting started
platform: uwp
control: SfKanban
documentation: ug
---

# Other features in Kanban

AllowDrag – It enable or disable the dragging cards in the corresponding Kanban column.

AlllowDrop – It used to enable or disable the Kanban column to drop the Kanban cards while dragging. 

{% tabs %}

{% highlight xaml %}

<syncfusion:KanbanColumn x:Name="Column1" 

Categories="Open"

Title="To Do"

AllowDrag="False"

AllowDrop="False"/>

{% endhighlight %}

{% highlight c# %}

KanbanColumn column=new KanbanColumn();

column.Categories = "Open";

column.Title = "To Do";

column.AlllowDrop = false;

column.AllowDrag = false;

kanban.Columns.Add(column);

{% endhighlight %} {% endtabs %}

