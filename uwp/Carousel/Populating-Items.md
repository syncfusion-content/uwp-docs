---
layout: post
title: Populating Items in UWP Carousel control | Syncfusion
description: Learn here all about Populating Items support in Syncfusion UWP Carousel (SfCarousel) control and more.
platform: uwp
control: SfCarousel
documentation: ug
---

# Populating Items in UWP Carousel (SfCarousel)

`SfCarouselItem` can be added as items of `SfCarousel`. Items of `SfCarousel` can be added though `Items` or `ItemSource` property.

## Using Items

`SfCarousel` accepts `SfCarouselItem` as its children when added directly.

### Adding items to the control

Here five `SfCarouselItems` are added as the children of the `SfCarousel`.

{% tabs %}

{% highlight XAML %}

<layout:SfCarousel>

<layout:SfCarouselItem/>

<layout:SfCarouselItem/>

<layout:SfCarouselItem/>

<layout:SfCarouselItem/>

<layout:SfCarouselItem/>

</layout:SfCarousel>

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

SfCarousel carousel = new SfCarousel();

carousel.Items.Add(new SfCarouselItem());

carousel.Items.Add(new SfCarouselItem());

carousel.Items.Add(new SfCarouselItem());

carousel.Items.Add(new SfCarouselItem());

carousel.Items.Add(new SfCarouselItem());

{% endhighlight %}

{% highlight VB %}

Dim carousel As New SfCarousel()

carousel.Items.Add(New SfCarouselItem())

carousel.Items.Add(New SfCarouselItem())

carousel.Items.Add(New SfCarouselItem())

carousel.Items.Add(New SfCarouselItem())

carousel.Items.Add(New SfCarouselItem())

{% endhighlight %}

{% endtabs %}

### Displaying the items

`Content` property helps to set the content for `SfCarouselItem`. `SfCarouselItem` is a ContentControl so that any object can be added as its content. 

{% tabs %}

{% highlight XAML %}

<layout:SfCarousel>

<layout:SfCarouselItem Content="Item 1"/>

<layout:SfCarouselItem Content="Item 2"/>

<layout:SfCarouselItem Content="Item 3"/>

<layout:SfCarouselItem Content="Item 4"/>

<layout:SfCarouselItem Content="Item 5"/>

</layout:SfCarousel>

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

SfCarousel carousel = new SfCarousel();

carousel.Items.Add(new SfCarouselItem() { Content = "Item 1" });

carousel.Items.Add(new SfCarouselItem() { Content = "Item 2"});

carousel.Items.Add(new SfCarouselItem() { Content = "Item 3" });

carousel.Items.Add(new SfCarouselItem() { Content = "Item 4"});

carousel.Items.Add(new SfCarouselItem() { Content = "Item 5"});

{% endhighlight %}

{% highlight VB %}

Dim carousel As New SfCarousel()

carousel.Items.Add(New SfCarouselItem() With {.Content = "Item 1"})

carousel.Items.Add(New SfCarouselItem() With {.Content = "Item 2"})

carousel.Items.Add(New SfCarouselItem() With {.Content = "Item 3"})

carousel.Items.Add(New SfCarouselItem() With {.Content = "Item 4"})

carousel.Items.Add(New SfCarouselItem() With {.Content = "Item 5"})

{% endhighlight %}

{% endtabs %}

![Provided the Content to Carousel](SfCarousel-images/SfCarousel-img4.jpeg)

## Using ItemsSource

`SfCarousel` accepts any business object collection to be bound to its `ItemsSource` property. 

### Adding items to the control

Follow the below steps to add the Items through `ItemsSource` property.

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

4.Bind the Employees collection to `ItemsSource` property of `SfCarousel` Control

{% tabs %}

{% highlight XAML %}

<layout:SfCarousel ItemsSource="{Binding Employees}"/>

{% endhighlight %}

{% endtabs %}

`SfCarousel` control is populated as follows:

![Provided the ItemSource to Carousel](SfCarousel-images/SfCarousel-img5.jpeg)

### Displaying the item

Content can be displayed using the `DisplayMemberPath` and `ItemTemplate` property.

{% tabs %}

{% highlight XAML %}

<layout:SfCarousel ItemsSource="{Binding Employees}" DisplayMemberPath="Name"/>

{% endhighlight %}

{% endtabs %}

![Provided the DisplayMemberPath to Carousel](SfCarousel-images/SfCarousel-img6.jpeg)

{% tabs %}

{% highlight XAML %}

<layout:SfCarousel ItemsSource="{Binding Employees}">

<layout:SfCarousel.ItemTemplate>

<DataTemplate>

<TextBlock Text="{Binding Name}"/>

</DataTemplate>

</layout:SfCarousel.ItemTemplate>

</layout:SfCarousel>

{% endhighlight %}

{% endtabs %}

