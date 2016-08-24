---
layout: post
title: Getting Started | SfKanban | uwp | Syncfusion
description: getting started
platform: uwp
control: SfKanban
documentation: ug
---

# Workflow configuration

A Kanban workflow is a set of Category and AllowedTransitions that an item moves through its lifecycle and typically represents processes within your organization.

* Category – It represents a state of an item at a particular point in a specific workflow.

* AllowedTransitions – It is a list of categories to where the card can be moved from the current category.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfKanban.Workflows>

<syncfusion:KanbanWorkflow Category="Open">

<syncfusion:KanbanWorkflow.AllowedTransitions>

<x:String>InProgress</x:String>

</syncfusion:KanbanWorkflow.AllowedTransitions>

</syncfusion:KanbanWorkflow>

<syncfusion:KanbanWorkflow Category="InProgress">

<syncfusion:KanbanWorkflow.AllowedTransitions>

<x:String>Review</x:String>

<x:String>Done</x:String>

</syncfusion:KanbanWorkflow.AllowedTransitions>

</syncfusion:KanbanWorkflow>

</syncfusion:SfKanban.Workflows>

{% endhighlight %}

{% highlight c# %}

var workFlows = new WorkflowCollection();

workFlows.Add(new KanbanWorkflow()

{

Category = "Open",

AllowedTransitions = new List<object>() {"InProgress"}

});

workFlows.Add(new KanbanWorkflow()

{

Category = "InProgress",

AllowedTransitions = new List<object>() {"Review", "Done"}

});

Kanban.Workflows = workFlows;

{% endhighlight %}

 {% endtabs %}

The following snap represents Kanban does not allow user to drop the Kanban card from the column of InProgress -> Open, since workflow does not specify it. 

![](SfKanban_images/SfKanban_img9.png)
