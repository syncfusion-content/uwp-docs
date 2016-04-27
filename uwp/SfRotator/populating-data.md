---
layout : post
title : Populating data in Syncfusion Rotator control in UWP.
description : Learn how to set the DataSource in Rotator for UWP.
platform : UWP
control : Rotator 
documentation : ug
---

# Populating Data

## DataSource

SfRotator items can be populated with a collection of image datas using `DataSource` property.

{% highlight C# %}

	ArrayList rotatorItems=new ArrayList();
	For(int i=1;i<18;i++)
	{
	SfRotatorItem rotatorItems =new SfRotatorItem ();
	item.ImageName="image"+i;
	rotatorItems.add(item);
	}
	rotator.DataSource=rotatorItems;

{% endhighlight %}