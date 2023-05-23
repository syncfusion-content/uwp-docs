---
layout: post
title: Getting Started with UWP ComboBox control | Syncfusion
description: Learn here about getting started with Syncfusion UWP ComboBox (SfComboBox) control, its elements and more.
platform: uwp
control: SfComboBox  
documentation: ug
---

# Getting Started with UWP ComboBox (SfComboBox)

The SfComboBox control allows the user to select an item from a list of suggestions.

![Overview of the control](populating-items_images/sfcombobox.png)

## Adding SfComboBox control

Create a Universal Windows Platform project in Visual Studio and refer to the following assemblies.

* Syncfusion.SfInput.UWP

* Syncfusion.SfShared.UWP

1.Include the namespace for Syncfusion.SfInput.UWP assembly in MainPage.xaml

{% tabs %}

{% highlight XAML %}

<Page xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"

xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"

xmlns:input="using:Syncfusion.UI.Xaml.Controls.Input">

{% endhighlight %}

{% endtabs %}

2.Now add the `SfComboBox` control with a required optimal name using the included namespace

{% tabs %}

{% highlight XAML %}

<input:SfComboBox x:Name="combobox">

{% endhighlight %}

{% highlight C# %}

SfComboBox combobox = new SfComboBox();

{% endhighlight %}

{% highlight VB %}

Dim combobox As New SfComboBox()

{% endhighlight %}

{% endtabs %}


## Populating Items

### Items Source

SfComboBoxItems can be populated with the business object collection. The below example is illustrated to create a SfComboBox that display a list of employees. 

The Employee model is displayed as follows.

{% tabs %}

{% highlight c# %}

public class ProductList

  {

        public string Name { get; set; } 

 }

{% endhighlight %}

{% highlight VB %}

Public Class ProductList

    Public Property Name() As String

End Class

{% endhighlight %}

{% endtabs %}

Create the employee collection as follows.


{% tabs %}

{% highlight c# %}

private List<ProductList> products;



     public List<ProductList> Products

     {

         get { return products; }



         set { products = value; }

     }

{% endhighlight %}

{% highlight VB %}

Private products_Renamed As List(Of ProductList)

Public Property Products() As List(Of ProductList)


		 Get
			 Return products_Renamed
		 End Get



		 Set(ByVal value As List(Of ProductList))
			 products_Renamed = value
		 End Set

End Property

{% endhighlight %}

{% endtabs %}

### Populate the items.


{% tabs %}

{% highlight c# %}

  Products = new List<ProductList>();

 Products.Add(new ProductList() { Name = "Tools" });
            
 Products.Add(new ProductList() {  Name = "Grid" });
            
 Products.Add(new ProductList(){ Name = "Chart" });
            
 Products.Add(new ProductList(){ Name = "Gauge" }); 
            
 Products.Add(new ProductList(){ Name = "Olap" });
            
 Products.Add(new ProductList(){ Name = "Pivot" });
            
 Products.Add(new ProductList(){ Name = "SpreadSheet" });
   

{% endhighlight %}

{% highlight VB %}

 Products = New List(Of ProductList)()

 Products.Add(New ProductList() With {.Name = "Tools"})

 Products.Add(New ProductList() With {.Name = "Grid"})

 Products.Add(New ProductList() With {.Name = "Chart"})

 Products.Add(New ProductList() With {.Name = "Gauge"})

 Products.Add(New ProductList() With {.Name = "Olap"})

 Products.Add(New ProductList() With {.Name = "Pivot"})

 Products.Add(New ProductList() With {.Name = "SpreadSheet"})
   

{% endhighlight %}

{% endtabs %}

Bind the Employees collection to the ItemsSource property of the SfComboBox.

{% highlight XAML %}

<editors:SfComboBox ItemsSource="{Binding Products}" />

{% endhighlight %}


The above steps populate the SfComboBox as illustrated in the following screenshot.

![Showing itemsource property of UWP sfcombobox](populating-items_images/populating-items_img1.png)

### DisplayMemberPath

The DisplayMemberPath property of the SfComboBox is used to define the model’s property that is to be displayed inside the header of the tab items. 



{% highlight html %}

< editors:SfComboBox

DisplayMemberPath="Name" ItemsSource="{Binding Products}" />

{% endhighlight %}

This populates the SfComboBox as illustrated in the following screenshot. 

![Showing product name of the UWP sfcombobox](populating-items_images/populating-items_img2.png)



### Item Template

The ItemTemplate property of the SfComboBox can be used to customize the content part of the SfComboBoxItems.

{% highlight html %}

< editors:SfComboBox

            ItemsSource="{Binding Products}" >          <editors:SfComboBox.ItemTemplate>

                <DataTemplate>

                    <Grid>

                        <StackPanel>

             <TextBlock Text="{Binding Name}" FontSize="17"/>

             <TextBlock Text="{Binding Email}" FontSize="10" Opacity="0.5"/>

                        </StackPanel>

                    </Grid>

                </DataTemplate>

            </editors:SfComboBox.ItemTemplate>

</editors:SfComboBox>

{% endhighlight %}

This populates the SfComboBox as illustrated in the following screenshot.

![Showing employee name of the UWP sfcombobox](populating-items_images/populating-items_img3.png)