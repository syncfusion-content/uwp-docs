---
layout: post
title: Group two or more relevant objects | Syncfusion.
description: How to group two or more nodes and connectors?
platform: uwp
control: SfDiagram
documentation: ug
---

# Group

Group is used to cluster multiple Nodes and Connectors into a single element. It acts like a container for its children (Nodes, Groups, and Connectors). Every change made to the Group also affects the children. Child elements can be edited individually.

## Create Group

### Add Group

The following code illustrates how to create a Group Node.

{% highlight C# %}

ObservableCollection<NodeViewModel> nodes = new ObservableCollection<NodeViewModel>();
NodeViewModel node = new NodeViewModel()
{
	UnitWidth = 100,
	UnitHeight = 100,
	OffsetX = 100,
	OffsetY = 100,
	Shape = new RectangleGeometry() { Rect = new Rect(0, 0, 10, 10) },
	ShapeStyle = this.diagram.Resources["shapestyle"] as Style
};
NodeViewModel node1 = new NodeViewModel()
{
	UnitWidth = 100,
	UnitHeight = 100,
	OffsetX = 200,
	OffsetY = 200,
	Shape = new RectangleGeometry() { Rect = new Rect(0, 0, 10, 10) },
	ShapeStyle = this.diagram.Resources["shapestyle"] as Style
};

//Creates the Group collection
ObservableCollection<GroupViewModel> groups = new ObservableCollection<GroupViewModel>();

//Create the Group
GroupViewModel group = new GroupViewModel()
{
	//Defines the Collection of Nodes
	Nodes = new ObservableCollection<NodeViewModel>()
	{
		node,
		node1
	},
};

//Adds the Groups to the SfDiagram
groups.Add(group);
diagram.Groups = groups;

{% endhighlight %}

### Group from Stencil

Group Nodes can be predefined and added to stencil. You can drop those Groups into Diagram, when required. 

To explore how to add Groups from stencil, refer to [Stencil](/uwp/sfdiagram/stencil "Stencil").

## Interaction

You can edit the Group and its children at runtime. For more information about how to interact with a Group, refer to [Interaction](/uwp/sfdiagram/interaction "Interaction").