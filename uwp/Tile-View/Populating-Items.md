---
layout: post
title: Populating Items in UWP Tile View control | Syncfusion
description: Learn here all about Populating Items support in Syncfusion UWP Tile View (SfTileView) control and more.
platform: uwp
control: SfTileView
documentation: ug
---

# Populating Items in UWP Tile View (SfTileView)

`SfTileViewItem` are added as items of `SfTileView`. Items can be added using `Items` or `ItemSource` property.

## Using Items

`SfTileView` accepts SfTileViewItem as its children when added directly.

### Adding items to the control

`SfTileView` accepts `SfTileViewItem` as its children when added directly. Here five `SfTileViewItems` are added as the children of `SfTileView`. Adding items as follows display a blank screen.

{% tabs %}

{% highlight XAML %}

<layout:SfTileView>

<layout:SfTileViewItem/>

<layout:SfTileViewItem/>

<layout:SfTileViewItem/>

<layout:SfTileViewItem/>

<layout:SfTileViewItem/>

</layout:SfTileView>

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

SfTileView tileView = new SfTileView();

tileView.Items.Add(new SfTileViewItem());

tileView.Items.Add(new SfTileViewItem());

tileView.Items.Add(new SfTileViewItem());

tileView.Items.Add(new SfTileViewItem());

tileView.Items.Add(new SfTileViewItem());

{% endhighlight %}

{% highlight VB %}

Dim tileView As New SfTileView()

tileView.Items.Add(New SfTileViewItem())

tileView.Items.Add(New SfTileViewItem())

tileView.Items.Add(New SfTileViewItem())

tileView.Items.Add(New SfTileViewItem())

tileView.Items.Add(New SfTileViewItem())

{% endhighlight %}

{% endtabs %}

### Setting content for items

`Content` property helps to set the content for `SfTileViewItem`. `SfTileViewItem` is a ContentControl so that any object can be added as its content. Content is visible only if the item is minimized.

{% tabs %}

{% highlight XAML %}

<layout:SfTileView>

<layout:SfTileViewItem Background="LightBlue" Content="Description about Paul Vent"/>

<layout:SfTileViewItem Background="LightBlue" Content="Description about Niko"/>

<layout:SfTileViewItem Background="LightBlue" Content="Description about James"/>

<layout:SfTileViewItem Background="LightBlue" Content="Description about Carl"/>

<layout:SfTileViewItem Background="LightBlue" Content="Description about Niko"/>

</layout:SfTileView>

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

SfTileView tileView = new SfTileView();

tileView.Items.Add(new SfTileViewItem() {
Content = "Description about Paul Vent" });

tileView.Items.Add(new SfTileViewItem() {
Content = "Description about Niko "});

tileView.Items.Add(new SfTileViewItem() {
Content = "Description about James " });

tileView.Items.Add(new SfTileViewItem() {
Content = "Description about Paul "});

tileView.Items.Add(new SfTileViewItem() {
Content = "Description about Paul "});

{% endhighlight %}

{% highlight VB %}

Dim tileView As New SfTileView()

tileView.Items.Add(New SfTileViewItem() With {.Content = "Description about Paul Vent"})

tileView.Items.Add(New SfTileViewItem() With {.Content = "Description about Niko "})

tileView.Items.Add(New SfTileViewItem() With {.Content = "Description about James "})

tileView.Items.Add(New SfTileViewItem() With {.Content = "Description about Paul "})

tileView.Items.Add(New SfTileViewItem() With {.Content = "Description about Paul "})

{% endhighlight %}

{% endtabs %}

![Populating-Items-img1](Populating-Items-images/Populating-Items-img1.jpeg)

### Setting MaximizedContent for items

`MaximizedContent` property helps to set the maximized content for `SfTileViewItem`. MaximizedContent is visible only if the item is maximized.

Set the `MaximizedContent` property as given below:

{% tabs %}

{% highlight XAML %}

<layout:SfTileView Width="500" Height="300">

<layout:SfTileViewItem Background="LightBlue" Content="PaulVent" 

MaximizedContent="Description about Paul" />

<layout:SfTileViewItem Background="LightBlue" Content="James" 

MaximizedContent="Description about James"/>

<layout:SfTileViewItem Background="LightBlue" Content="Carl" 

MaximizedContent="Description about Carl"/>

<layout:SfTileViewItem Background="LightBlue" Content="Niko"

MaximizedContent="Description about Niko"/> 

</layout:SfTileView>

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

SfTileView tileView = new SfTileView();

tileView.Items.Add(new SfTileViewItem()
{
   Content = "PaulVent",
   MaximizedContent = "Description about Paul"
});

tileView.Items.Add(new SfTileViewItem()
{
   Content = "James",
   MaximizedContent="Description about James"
});

tileView.Items.Add(new SfTileViewItem()
{
   Content = "Carl",
   MaximizedContent="Description about Carl"
});

tileView.Items.Add(new SfTileViewItem()
{
   Content = "Niko",
   MaximizedContent="Description about Niko"
});

{% endhighlight %}

{% highlight VB %}

Dim tileView As New SfTileView()

tileView.Items.Add(New SfTileViewItem() With {
	.Content = "PaulVent",
	.MaximizedContent = "Description about Paul"
})

tileView.Items.Add(New SfTileViewItem() With {
	.Content = "James",
	.MaximizedContent="Description about James"
})

tileView.Items.Add(New SfTileViewItem() With {
	.Content = "Carl",
	.MaximizedContent="Description about Carl"
})

tileView.Items.Add(New SfTileViewItem() With {
	.Content = "Niko",
	.MaximizedContent="Description about Niko"
})

{% endhighlight %}

{% endtabs %}

![Populating-Items-img2](Populating-Items-images/Populating-Items-img2.jpeg)

## Using ItemsSource

### Adding items to the control

`SfTileView` accepts any business object collection to be bound to its `ItemsSource` property. 

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

4.Bind the Employees collection to ItemsSource property of SfTileView Control

{% tabs %}

{% highlight XAML %}

<layout:SfTileView ItemsSource="{Binding Employees}"/>

{% endhighlight %}

{% endtabs %}

Tile view items need a template to render so `SfTileView` control is populated as follows:

![Populating-Items-img3](Populating-Items-images/Populating-Items-img3.jpeg)

### Setting content for items

Template for tile view items can be set using the `ItemTemplate` property. ItemTemplate helps to decorate the item with visual elements. At this point, the control is populated with a list of employees. The class Employee has two properties, Name and Description. In this case, control is set to display content based on Name:

{% tabs %}

{% highlight XAML %}

<layout:SfTileView ItemsSource="{Binding Employees}">

<layout:SfTileView.ItemTemplate>

<DataTemplate>

<TextBlock Text="{Binding Name}"/>

</DataTemplate>

</layout:SfTileView.ItemTemplate> 

<layout:SfTileView.ItemContainerStyle>

<Style TargetType="layout:SfTileViewItem">

<Setter Property="HorizontalAlignment" Value="Stretch"/>

<Setter Property="VerticalAlignment" Value="Stretch"/>

<Setter Property="HorizontalContentAlignment" Value="Stretch"/>

<Setter Property="VerticalContentAlignment" Value="Stretch"/>

</Style>

</layout:SfTileView.ItemContainerStyle>

</layout:SfTileView>

{% endhighlight %}

{% endtabs %}

![Populating-Items-img4](Populating-Items-images/Populating-Items-img4.jpeg)

Click on the Tile “Niko” to maximize it. Maximized item is not rendered because it requires  MaximizedItemTemplate other than ItemTemplate.

![Populating-Items-img5](Populating-Items-images/Populating-Items-img5.jpeg)

### Setting maximized content for items

Template for maximized item is set using `MaximizedItemTemplate` property. It can be set as follows:

{% tabs %}

{% highlight XAML %}

<layout:SfTileView Width="500" Height="300" ItemsSource="{Binding Employees}" >

<layout:SfTileView.ItemContainerStyle>

<Style TargetType="layout:SfTileViewItem">

<Setter Property="HorizontalAlignment" Value="Stretch"/>

<Setter Property="VerticalAlignment" Value="Stretch"/>

<Setter Property="HorizontalContentAlignment" Value="Stretch"/>

<Setter Property="VerticalContentAlignment" Value="Stretch"/>

</Style>

</layout:SfTileView.ItemContainerStyle>

<layout:SfTileView.ItemTemplate>

<DataTemplate>

<Border Background="LightBlue">

<TextBlock Text="{Binding Name}"/>

</Border>

</DataTemplate>

</layout:SfTileView.ItemTemplate>

<layout:SfTileView.MaximizedItemTemplate>

<DataTemplate>

<Border Background="LightBlue" >

<TextBlock Text="{Binding Description}" Foreground="DarkBlue" FontSize="18"/>

</Border>

</DataTemplate>

</layout:SfTileView.MaximizedItemTemplate>

</layout:SfTileView>

{% endhighlight %}

{% endtabs %}

![Populating-Items-img6](Populating-Items-images/Populating-Items-img6.jpeg)


