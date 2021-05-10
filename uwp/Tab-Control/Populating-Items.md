---
layout: post
title: Populating Items in UWP Tab Control control | Syncfusion
description: Learn here all about Populating Items support in Syncfusion UWP Tab Control (SfTabControl) control and more.
platform: uwp
control: SfTabControl
documentation: ug
---

# Populating Items in UWP Tab Control (SfTabControl)

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

{% endtabs %}

{% tabs %}

{% highlight C# %}

SfTabControl tabControl = new SfTabControl();

tabControl.Items.Add(new SfTabItem());

tabControl.Items.Add(new SfTabItem());

tabControl.Items.Add(new SfTabItem());

tabControl.Items.Add(new SfTabItem());

tabControl.Items.Add(new SfTabItem());

{% endhighlight %}

{% highlight VB %}

Dim tabControl As New SfTabControl()

tabControl.Items.Add(New SfTabItem())

tabControl.Items.Add(New SfTabItem())

tabControl.Items.Add(New SfTabItem())

tabControl.Items.Add(New SfTabItem())

tabControl.Items.Add(New SfTabItem())

{% endhighlight %}

{% endtabs %}

![Populating-Items-img1](Populating-Items-images/Populating-Items-img1.jpeg)


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

{% endtabs %}

{% tabs %}

{% highlight C# %}

SfTabControl tabControl = new SfTabControl();

tabControl.Items.Add(new SfTabItem() { Header = "Paul Vent" });

tabControl.Items.Add(new SfTabItem() { Header = "Niko "});

tabControl.Items.Add(new SfTabItem() { Header = "James " });

tabControl.Items.Add(new SfTabItem() { Header = "Carl "});

{% endhighlight %}

{% highlight VB %}

Dim tabControl As New SfTabControl()

tabControl.Items.Add(New SfTabItem() With {.Header = "Paul Vent"})

tabControl.Items.Add(New SfTabItem() With {.Header = "Niko "})

tabControl.Items.Add(New SfTabItem() With {.Header = "James "})

tabControl.Items.Add(New SfTabItem() With {.Header = "Carl "})

{% endhighlight %}

{% endtabs %}

![Populating-Items-img2](Populating-Items-images/Populating-Items-img2.jpeg)


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

{% endtabs %}

{% tabs %}

{% highlight C# %}

SfTabControl tabControl = new SfTabControl();

tabControl.Items.Add(new SfTabItem() { Header = "Paul Vent" ,Content = "Description about Paul Vent" });

tabControl.Items.Add(new SfTabItem() { Header = "Niko" ,Content = "Description about Niko "});

tabControl.Items.Add(new SfTabItem() { Header = "James" ,Content = "Description about James " });

tabControl.Items.Add(new SfTabItem() { Header = "Carl" ,Content = "Description about Carl "});

{% endhighlight %}

{% highlight VB %}

Dim tabControl As New SfTabControl()

tabControl.Items.Add(New SfTabItem() With {
	.Header = "Paul Vent",
	.Content = "Description about Paul Vent"
})

tabControl.Items.Add(New SfTabItem() With {
	.Header = "Niko",
	.Content = "Description about Niko "
})

tabControl.Items.Add(New SfTabItem() With {
	.Header = "James",
	.Content = "Description about James "
})

tabControl.Items.Add(New SfTabItem() With {
	.Header = "Carl",
	.Content = "Description about Carl "
})

{% endhighlight %}

{% endtabs %}


![Populating-Items-img3](Populating-Items-images/Populating-Items-img3.jpeg)


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

{% highlight VB %}

Public Class Employee


Public Property Name() As String

Public Property Description() As String

End Class

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

{% highlight VB %}

Private employees_Renamed As List(Of Employee)

Public Property Employees() As List(Of Employee)


  Get
	  Return employees_Renamed
  End Get

  Set(ByVal value As List(Of Employee))
	  employees_Renamed = value
  End Set

End Property

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

{% highlight VB %}

Employees = New List(Of Employee)()

Employees.Add(New Employee() With {
	.Name = "James",
	.Description = "Description about James"
})

Employees.Add(New Employee() With {
	.Name = "Linda",
	.Description = "Description about Linda"
})

Employees.Add(New Employee() With {
	.Name = "Carl",
	.Description = "Description about Carl"
})

Employees.Add(New Employee() With {
	.Name = "Niko",
	.Description = "Description about Niko"
})

{% endhighlight %}

{% endtabs %}

4.Bind the Employees collection to ItemsSource property of SfTabControl Control

{% tabs %}

{% highlight XAML %}

<navigation:SfTabControl ItemsSource="{Binding Employees}"/>

{% endhighlight %}


{% endtabs %}


Tile view items need a template to render so SfTabControl control is populated as follows:

![Populating-Items-img4](Populating-Items-images/Populating-Items-img4.jpeg)


### Setting header for items

Header can be displayed using the property DisplayMemberPath. This property is used to get the header from Model class. 

{% tabs %}

{% highlight XAML %}

<navigation:SfTabControl ItemsSource="{Binding Employees}" DisplayMemberPath="Name"/>

{% endhighlight %}


{% endtabs %}


![Populating-Items-img5](Populating-Items-images/Populating-Items-img5.jpeg)


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

![Populating-Items-img6](Populating-Items-images/Populating-Items-img6.jpeg)


