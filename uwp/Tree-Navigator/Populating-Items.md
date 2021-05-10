---
layout: post
title: Populating Items in UWP Tree Navigator control | Syncfusion
description: Learn here all about Populating Items support in Syncfusion UWP Tree Navigator (SfTreeNavigator) control and more.
platform: uwp
control: SfTreeNavigator
documentation: ug
---

# Populating Items in UWP Tree Navigator (SfTreeNavigator)

`SfTreeNavigatorItem` are added as items of SfTreeNavigator. Items can be added using `Items` or `ItemSource` property.

## Adding Items

`SfTreeNavigator` accepts `SfTreeNavigatorItem` as its children when added directly. Here five `SfTreeNavigatorItems` are added as the children of SfTreeNavigator. Adding items as follows display items with blank header.

{% tabs %}

{% highlight XAML %}

<navigation:SfTreeNavigator>

<navigation:SfTreeNavigatorItem/>

<navigation:SfTreeNavigatorItem/>

<navigation:SfTreeNavigatorItem/>

<navigation:SfTreeNavigatorItem/>

<navigation:SfTreeNavigatorItem/>

</navigation:SfTreeNavigator>

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

SfTreeNavigator treeNavigator = new SfTreeNavigator();

treeNavigator.Items.Add(new SfTreeNavigatorItem());

treeNavigator.Items.Add(new SfTreeNavigatorItem());

treeNavigator.Items.Add(new SfTreeNavigatorItem());

treeNavigator.Items.Add(new SfTreeNavigatorItem());

treeNavigator.Items.Add(new SfTreeNavigatorItem());

{% endhighlight %}

{% highlight VB %}

Dim treeNavigator As New SfTreeNavigator()

treeNavigator.Items.Add(New SfTreeNavigatorItem())

treeNavigator.Items.Add(New SfTreeNavigatorItem())

treeNavigator.Items.Add(New SfTreeNavigatorItem())

treeNavigator.Items.Add(New SfTreeNavigatorItem())

treeNavigator.Items.Add(New SfTreeNavigatorItem())

{% endhighlight %}

{% endtabs %}

![Populating Items](Populating-Items-images/Populating-Items-img1.jpeg)

## Setting Header

`Header` property helps to set the header for `SfTreeNavigatorItem`. Tree navigator item can be selected by clicking on its header.

{% tabs %}

{% highlight XAML %}

<navigation:SfTreeNavigator>

<navigation:SfTreeNavigatorItem Header="WPF"/>

<navigation:SfTreeNavigatorItem Header="Silverlight"/>

<navigation:SfTreeNavigatorItem Header="Windows Phone"/>

<navigation:SfTreeNavigatorItem Header="WinRT"/>

<navigation:SfTreeNavigatorItem Header="Universal"/> 

</navigation:SfTreeNavigator>

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

SfTreeNavigator treeNavigator = new SfTreeNavigator();

treeNavigator.Items.Add(new SfTreeNavigatorItem () { 
Header = "WPF" });

treeNavigator.Items.Add(new SfTreeNavigatorItem () { 
Header = "Silverlight"});

treeNavigator.Items.Add(new SfTreeNavigatorItem () { 
Header = "Windows Phone" });

treeNavigator.Items.Add(new SfTreeNavigatorItem () { 
Header = "WinRT"});

treeNavigator.Items.Add(new SfTreeNavigatorItem () { 
Header = "Universal"});

{% endhighlight %}

{% highlight VB %}

Dim treeNavigator As New SfTreeNavigator()

treeNavigator.Items.Add(New SfTreeNavigatorItem() With {.Header = "WPF"})

treeNavigator.Items.Add(New SfTreeNavigatorItem() With {.Header = "Silverlight"})

treeNavigator.Items.Add(New SfTreeNavigatorItem() With {.Header = "Windows Phone"})

treeNavigator.Items.Add(New SfTreeNavigatorItem() With {.Header = "WinRT"})

treeNavigator.Items.Add(New SfTreeNavigatorItem() With {.Header = "Universal"})

{% endhighlight %}

{% endtabs %}

![Header property](Populating-Items-images/Populating-Items-img2.jpeg)

## Adding SubItems

`Items` property helps to add sub items for `SfTreeNavigatorItem`. `SfTreeNavigatorItem` is an ItemsControl so that a collection of tree navigator items can be added to it. Sub items are viewable only after it is navigated to next level.

{% tabs %}

{% highlight XAML %}

<navigation:SfTreeNavigator>

<navigation:SfTreeNavigatorItem Header="WPF">

<navigation:SfTreeNavigatorItem Header="Chart"/>

<navigation:SfTreeNavigatorItem Header="Grid"/>

<navigation:SfTreeNavigatorItem Header="Tools"/>

</navigation:SfTreeNavigatorItem>

<navigation:SfTreeNavigatorItem Header="Silverlight"/>

<navigation:SfTreeNavigatorItem Header="Windows Phone"/>

<navigation:SfTreeNavigatorItem Header="WinRT"/>

<navigation:SfTreeNavigatorItem Header="Universal"/> 

</navigation:SfTreeNavigator>

{% endhighlight %}

{% endtabs %}

{% tabs %}


{% highlight C# %}

SfTreeNavigator treeNavigator = new SfTreeNavigator();

SfTreeNavigatorItem WPF = new SfTreeNavigatorItem () { 
Header = "WPF" };

WPF.Items.Add(new SfTreeNavigatorItem () { 
Header = "Chart" });

WPF.Items.Add(new SfTreeNavigatorItem () { 
Header = "Grid" });

WPF.Items.Add(new SfTreeNavigatorItem () { 
Header = "Tools" });

treeNavigator.Items.Add(WPF);

treeNavigator.Items.Add(new SfTreeNavigatorItem () { 
Header = "Silverlight"});

treeNavigator.Items.Add(new SfTreeNavigatorItem () { 
Header = "Windows Phone" });

treeNavigator.Items.Add(new SfTreeNavigatorItem () { 
Header = "WinRT"});

treeNavigator.Items.Add(new SfTreeNavigatorItem () { 
Header = "Universal"});

{% endhighlight %}

{% highlight VB %}

Dim treeNavigator As New SfTreeNavigator()

Dim WPF As New SfTreeNavigatorItem() With {.Header = "WPF"}

WPF.Items.Add(New SfTreeNavigatorItem() With {.Header = "Chart"})

WPF.Items.Add(New SfTreeNavigatorItem() With {.Header = "Grid"})

WPF.Items.Add(New SfTreeNavigatorItem() With {.Header = "Tools"})

treeNavigator.Items.Add(WPF)

treeNavigator.Items.Add(New SfTreeNavigatorItem() With {.Header = "Silverlight"})

treeNavigator.Items.Add(New SfTreeNavigatorItem() With {.Header = "Windows Phone"})

treeNavigator.Items.Add(New SfTreeNavigatorItem() With {.Header = "WinRT"})

treeNavigator.Items.Add(New SfTreeNavigatorItem() With {.Header = "Universal"})

{% endhighlight %}

{% endtabs %}

![Adding SubItems](Populating-Items-images/Populating-Items-img3.jpeg)

## Using ItemsSource

### Adding Items

`SfTreeNavigator` accepts any business object collection to be bound to its `ItemsSource` property. 

1.Create a model

{% tabs %}

{% highlight C# %}

public class TreeModel : NotificationObject

{

public TreeModel()

{

Models = new ObservableCollection<TreeModel>();

}

private string header;

public string Header

{

get { return header; }

set

{

header = value;

RaisePropertyChanged("Header");

}

}
private ObservableCollection<TreeModel> models;

public ObservableCollection<TreeModel> Models

{

get { return models; }

set { models = value; }

}

}

{% endhighlight %}

{% highlight VB %}

Public Class TreeModel
	
	Inherits NotificationObject

Public Sub New()


Models = New ObservableCollection(Of TreeModel)()

End Sub

Private header_Renamed As String

Public Property Header() As String


Get
	Return header_Renamed
End Get

Set(ByVal value As String)


header_Renamed = value

RaisePropertyChanged("Header")

End Set

End Property

Private models_Renamed As ObservableCollection(Of TreeModel)

Public Property Models() As ObservableCollection(Of TreeModel)


Get
	Return models_Renamed
End Get

Set(ByVal value As ObservableCollection(Of TreeModel))
	models_Renamed = value
End Set

End Property

End Class

{% endhighlight %}

{% endtabs %}

2.Create a collection of model

{% tabs %}

{% highlight C# %}

private List<TreeModel> models;

public List<TreeModel> Models

{

get { return models; }

set { models = value; }

}

{% endhighlight %}

{% highlight VB %}

Private models_Renamed As List(Of TreeModel)

Public Property Models() As List(Of TreeModel)


Get
	Return models_Renamed
End Get

Set(ByVal value As List(Of TreeModel))
	models_Renamed = value
End Set

End Property

{% endhighlight %}

{% endtabs %}

3.Populate the collection

{% tabs %}

{% highlight C# %}

public TreeViewModel()

{

Models = new List<TreeModel>();

TreeModel win = new TreeModel() { Header = "WinRT (XAML)" };

TreeModel metroStudio = new TreeModel() { Header = "Metro Studio" };

TreeModel win_chart = new TreeModel() { Header = "Chart" };

TreeModel win_tools = new TreeModel() { Header = "Tools" };

win.Models.Add(win_chart);

win.Models.Add(win_tools);

Models.Add(win);

Models.Add(metroStudio);

}

{% endhighlight %}

{% highlight VB %}

Public Sub New()

Models = New List(Of TreeModel)()

Dim win As New TreeModel() With {.Header = "WinRT (XAML)"}

Dim metroStudio As New TreeModel() With {.Header = "Metro Studio"}

Dim win_chart As New TreeModel() With {.Header = "Chart"}

Dim win_tools As New TreeModel() With {.Header = "Tools"}

win.Models.Add(win_chart)

win.Models.Add(win_tools)

Models.Add(win)

Models.Add(metroStudio)

End Sub

{% endhighlight %}

{% endtabs %}

4.Set the DataContext for control and bind the Models collection to `ItemsSource` property of `SfTreeNavigator` control

{% tabs %}

{% highlight XAML %}

<navigation:SfTreeNavigator ItemsSource="{Binding Models}"/>

{% endhighlight %}

{% endtabs %}

TreeNavigator items need a template to render so `SfTreeNavigator` control is populated as follows:

![Adding items using ItemsSource](Populating-Items-images/Populating-Items-img4.jpeg)

### Setting Header for items

Header can be displayed by setting ItemTemplate. Setting DataTemplate does not allow to navigate to sub items.

{% tabs %}

{% highlight XAML %}

<navigation:SfTreeNavigator ItemsSource="{Binding Models}">     

<navigation:SfTreeNavigator.ItemTemplate>

<DataTemplate>

<TextBlock Text="{Binding Header}"/>

</DataTemplate>

</navigation:SfTreeNavigator.ItemTemplate>

</navigation:SfTreeNavigator>

{% endhighlight %}

{% endtabs %}

![Setting Header for items](Populating-Items-images/Populating-Items-img5.jpeg)

### Adding SubItems

Sub-items can be viewed only if the item template is HierarchicalDataTemplate rather than DataTemplate. HierarchicalDataTemplate class is available in Syncfusion.UI.Xaml.Primitives namespace.

{% tabs %}

{% highlight XAML %}

<Page xmlns:primitives="using:Syncfusion.UI.Xaml.Primitives"

xmlns:navigation="using:Syncfusion.UI.Xaml.Controls.Navigation">

<Page.DataContext>

<local:TreeViewModel/>

</Page.DataContext>

<Grid>

<navigation:SfTreeNavigator ItemsSource="{Binding Models}">

<navigation:SfTreeNavigator.ItemTemplate>

<primitives:HierarchicalDataTemplate ItemsSource="{Binding Models}">

<DataTemplate>

<TextBlock Text="{Binding Header}"/>

</DataTemplate>

</primitives:HierarchicalDataTemplate>

</navigation:SfTreeNavigator.ItemTemplate>

</navigation:SfTreeNavigator>

</Grid>

</Page>

{% endhighlight %}

{% endtabs %}

![Hierarchical DataTemplate](Populating-Items-images/Populating-Items-img6.jpeg)


