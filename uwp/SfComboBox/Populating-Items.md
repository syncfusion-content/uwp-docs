---
layout: post
title: Populating Items of SfComboBox control for UWP
description: Populating Items of SfComboBox control for UWP
platform: uwp
control: SfComboBox
documentation: ug
---

# Populating Items

## Items Source

SfComboBoxItems can be populated with the business object collection. The below example is illustated to create a SfComboBox that display a list of employees. 

The Employee model is displayed as follows.

{% highlight c# %}

public class ProductList

  {

        public string Name { get; set; } 

 }

{% endhighlight %}

Create the employee collection as follows.

{% highlight c# %}

private List<ProductList> products;



     public List<ProductList> Products

     {

         get { return products; }



         set { products = value; }

     }

{% endhighlight %}



### Populate the items.



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

Bind the Employees collection to the ItemsSource property of the SfComboBox.

{% highlight XAML %}

<editors:SfComboBox ItemsSource="{Binding Products}" />

{% endhighlight %}


The above steps populate the SfComboBox as illustrated in the following screenshot.

![](Populating-Items_images/Populating-Items_img1.png)

## DisplayMemberPath

The DisplayMemberPath property of the SfComboBox is used to define the model’s property that is to be displayed inside the header of the tab items. 



{% highlight html %}

< editors:SfComboBox

DisplayMemberPath="Name" ItemsSource="{Binding Products}" />

{% endhighlight %}

This populates the SfComboBox as illustrated in the following screenshot. 

![](Populating-Items_images/Populating-Items_img2.png)



## Item Template

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

![](Populating-Items_images/Populating-Items_img3.png)