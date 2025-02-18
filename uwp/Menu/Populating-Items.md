---
layout: post
title: Populating Items in UWP Menu control | Syncfusion®
description: Learn here all about Populating Items support in Syncfusion® UWP Menu (SfMenu) control and more.
platform: UWP
control: SfMenu
documentation: ug
--- 

# Populating Items in UWP Menu (SfMenu)

`SfMenuItem` can be added as items of `SfMenu`. Items can be added using `Items` or `ItemsSource` property.

## Populating Items through adding SfMenuItem

`SfMenu` accepts `SfMenuItem` as its children when added directly.

### Adding Items to the Control

Here five `SfMenuItems` are added as the children of the `SfMenu`.

{% tabs %}

{% highlight XAML %}

<menu:SfMenu >

<menu:SfMenuItem Header="File"/>

<menu:SfMenuItem Header="Home"/>

<menu:SfMenuItem Header = "Insert"/>

<menu:SfMenuItem Header = "Design" />

<menu:SfMenuItem Header = "Layout" />

</menu:SfMenu>

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

SfMenu sfMenu = new SfMenu();

sfMenu.Items.Add(new SfMenuItem { Header = "File" });

sfMenu.Items.Add(new SfMenuItem { Header = "Home" });

sfMenu.Items.Add(new SfMenuItem { Header = "Insert" });

sfMenu.Items.Add(new SfMenuItem { Header = "Design" });

sfMenu.Items.Add(new SfMenuItem { Header = "Layout" });


{% endhighlight %}

{% endtabs %}

## Populating Items through Binding

`SfMenu` accepts any business object collection to be bound to its `ItemsSource` property.

### Adding items to the control

Follow the below steps to add the Items through `ItemsSource` property.

1.Create a model

{% tabs %}

{% highlight C# %}

public class Model

{

private string _header;

public string Header

{

get

{

return _header;

}

set

{

_header = value;

}

}

}



{% endhighlight %}

{% endtabs %}

2.Create a collection of model

{% tabs %}

{% highlight C# %}

public class ViewModel

{

private Observable

Collection<Model> _collection;

public ObservableCollection<Model> MenuCollection

{

get

{

return _collection;

}

set

{

_collection = value;

}

}

public ViewModel()

{

MenuCollection = new ObservableCollection<Model>();

MenuCollection.Add(new Model() { Header = "File" });

MenuCollection.Add(new Model() { Header = "Home" });

MenuCollection.Add(new Model() { Header = "Insert" });

MenuCollection.Add(new Model() { Header = "Design" });

MenuCollection.Add(new Model() { Header = "Layout" });

}

}

{% endhighlight %}

{% endtabs %}



3.Bind the MenuCollection to `ItemsSource` property of `SfMenu` Control.

{% tabs %}

{% highlight XAML %}

<menu:SfMenu ItemsSource="{Binding MenuCollection}" />

{% endhighlight %}

{% endtabs%}

`SfMenu` control is populated as follows:

![Populating-Items-img1](Populating-Items-images/Populating-Items-img1.jpg)


## Displaying the Item

Content can be displayed using the `DisplayMemberPath` and `ItemTemplate` property.

{% tabs %}

{% highlight XAML %}

<menu:SfMenu ItemsSource="{Binding MenuCollection}"  DisplayMemberPath="Header" />

{% endhighlight %}

{% endtabs %}



{% highlight XAML %}

<menu:SfMenu ItemsSource="{Binding MenuCollection}" >

<menu:SfMenu.ItemTemplate>

<DataTemplate>

<TextBlock Text="{Binding Header}"/>

</DataTemplate>

</menu:SfMenu.ItemTemplate>  

</menu:SfMenu>

{% endhighlight %}

![Populating-Items-img2](Populating-Items-images/Populating-Items-img2.jpg)
