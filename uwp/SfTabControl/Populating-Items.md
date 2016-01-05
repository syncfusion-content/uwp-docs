---
layout: post
title: Populating Items of SfTabControl control for UWP
description: Explains about Populating Items of SfTabControl control for UWP
platform: uwp
control: SfTabControl
documentation: ug
---

# Populating Items

SfTabItems are added as items of SfTabControl. Items can be added using Items or ItemSource property.

## Using Items

SfTabControl accepts SfTabItem as its children when added directly.

### Adding items to the control

Here five SfTabItems are added as the children of SfTabControl. Adding items as follows display items with “Untitled” header.

{% tabs %}

{% highlight XAML %}

<navigation:SfTabControl>

<navigation:SfTabItem/>

<navigation:SfTabItem/>

<navigation:SfTabItem/>

<navigation:SfTabItem/>

<navigation:SfTabItem/>

</navigation:SfTabControl>

{% endhighlight %}

{% highlight C# %}

SfTabControl tabControl = new SfTabControl();

tabControl.Items.Add(new SfTabItem());

tabControl.Items.Add(new SfTabItem());

tabControl.Items.Add(new SfTabItem());

tabControl.Items.Add(new SfTabItem());

tabControl.Items.Add(new SfTabItem());

{% endhighlight %}

{% endtabs %}

![](Populating-Items-images/Populating-Items-img1.jpeg)


### Setting header for items

Header property helps to set the header for SfTabItem. Tab item can be selected by clicking on its header.

{% tabs %}

{% highlight XAML %}

<navigation:SfTabControl>

<navigation:SfTabItem Header="Paul Vent"/>

<navigation:SfTabItem Header="Niko"/>

<navigation:SfTabItem Header="James"/>

<navigation:SfTabItem Header="Carl"/>

</navigation:SfTabControl>

{% endhighlight %}

{% highlight C# %}

SfTabControl tabControl = new SfTabControl();

tabControl.Items.Add(new SfTabItem() { Header = "Paul Vent" });

tabControl.Items.Add(new SfTabItem() { Header = "Niko "});

tabControl.Items.Add(new SfTabItem() { Header = "James " });

tabControl.Items.Add(new SfTabItem() { Header = "Carl "});

{% endhighlight %}

{% endtabs %}

![](Populating-Items-images/Populating-Items-img2.jpeg)


### Setting content for items

Content property helps to set the content for SfTabItem. SfTabItem is a ContentControl so that any object can be added as its content. Content is visible only if the item is selected.

{% tabs %}

{% highlight XAML %}

<navigation:SfTabControl>

<navigation:SfTabItem Header="Paul Vent" Content="Description about Paul Vent"/>

<navigation:SfTabItem Header="Niko" Content="Description about Niko"/>

<navigation:SfTabItem Header="James" Content="Description about James"/>

<navigation:SfTabItem Header="Carl" Content="Description about Carl"/>

</navigation:SfTabControl>

{% endhighlight %}

{% highlight C# %}

SfTabControl tabControl = new SfTabControl();

tabControl.Items.Add(new SfTabItem() { Header = "Paul Vent" ,Content = "Description about Paul Vent" });

tabControl.Items.Add(new SfTabItem() { Header = "Niko" ,Content = "Description about Niko "});

tabControl.Items.Add(new SfTabItem() { Header = "James" ,Content = "Description about James " });

tabControl.Items.Add(new SfTabItem() { Header = "Carl" ,Content = "Description about Carl "});

{% endhighlight %}

{% endtabs %}


![](Populating-Items-images/Populating-Items-img3.jpeg)


## Using ItemsSource

### Adding items to the control

SfTabControl accepts any business object collection to be bound to its ItemsSource property. 

1.Create a model 


{% tabs %}

{% highlight C# %}

public class Employee

{
	
public string Name { get; set; }

public string Description { get; set; }

}

{% endhighlight %}

{% endtabs %}



 2.Create a collection of model

{% tabs %}

{% highlight C# %}

private List<Employee> employees;

public List<Employee> Employees

{
	
  get { return employees; }
  
  set { employees = value; }
  
}


{% endhighlight %}

{% endtabs %}

3.Populate the collection

{% tabs %}

{% highlight C# %}

Employees = new List<Employee>();

Employees.Add(new Employee() { Name = "James", Description = "Description about James" });

Employees.Add(new Employee() { Name = "Linda", Description = "Description about Linda" });

Employees.Add(new Employee() { Name = "Carl", Description = "Description about Carl" });

Employees.Add(new Employee() { Name = "Niko", Description = "Description about Niko" });


{% endhighlight %}

{% endtabs %}

4.Bind the Employees collection to ItemsSource property of SfTabControl Control

{% tabs %}

{% highlight XAML %}

<navigation:SfTabControl ItemsSource="{Binding Employees}"/>

{% endhighlight %}


{% endtabs %}


Tile view items need a template to render so SfTabControl control is populated as follows:

![](Populating-Items-images/Populating-Items-img4.jpeg)


### Setting header for items

Header can be displayed using the property DisplayMemberPath. This property is used to get the header from Model class. 

{% tabs %}

{% highlight XAML %}

<navigation:SfTabControl ItemsSource="{Binding Employees}" DisplayMemberPath="Name"/>

{% endhighlight %}


{% endtabs %}


![](Populating-Items-images/Populating-Items-img5.jpeg)


### Setting content for items

Content can be displayed using the ContentTemplate property. Content is visible only when the item is selected. ContentTemplateSelector property is also provided to apply content template based on the selection logic.

{% tabs %}

{% highlight XAML %}

<navigation:SfTabControl ItemsSource="{Binding Employees}"
                         DisplayMemberPath="Name">

<navigation:SfTabControl.ContentTemplate>

<DataTemplate>

<TextBlock Text="{Binding Description}"/>

</DataTemplate>

</navigation:SfTabControl.ContentTemplate>

</navigation:SfTabControl>


{% endhighlight %}


{% endtabs %}

![](Populating-Items-images/Populating-Items-img6.jpeg)


