---
layout: post
title: Populating Data in UWP Domain UpDown control | Syncfusion®
description: Learn here all about Populating Data support in Syncfusion® UWP Domain UpDown (SfDomainUpDown) control and more.
platform: uwp
control: SfDomainUpDown
documentation: ug
---

# Populating Data in UWP Domain UpDown (SfDomainUpDown)

The DomainUpDown control can be populated with a predefined list of items. 

For example, in the following code, the SfDomainUpDown will populate a list of employees:

{% tabs %}

{% highlight c# %}

public class Employee

    {

        public string Name { get; set; }



        public string Email { get; set; }

    }

{% endhighlight %}

{% highlight VB %}

Public Class Employee


		Public Property Name() As String



		Public Property Email() As String

End Class

{% endhighlight %}

{% endtabs %}

Create a collection attribute:

{% tabs %}

{% highlight c# %}

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

Populate the collection with items:

{% tabs %}

{% highlight c# %}

Employees = new List<Employee>();

Employees.Add(new Employee{Name = "Lucas", Email = "lucas@syncfusion.com"});

Employees.Add(new Employee { Name = "James", Email = "james@syncfusion.com" });

Employees.Add(new Employee { Name = "Jacob", Email = "jacob@syncfusion.com" });

{% endhighlight %}

{% highlight VB %}

Employees = New List(Of Employee)()

Employees.Add(New Employee With {
	.Name = "Lucas",
	.Email = "lucas@syncfusion.com"
})

Employees.Add(New Employee With {
	.Name = "James",
	.Email = "james@syncfusion.com"
})

Employees.Add(New Employee With {
	.Name = "Jacob",
	.Email = "jacob@syncfusion.com"
})

{% endhighlight %}

{% endtabs %}

## ItemsSource

Bind the Employees collection to the ItemsSource property of DomainUpDown:

{% highlight XAML %}


    <Page xmlns:editors="using:Syncfusion.UI.Xaml.Controls.Input">

            <Grid Background="{StaticResource ApplicationPageBackgroundThemeBrush}">

                <editors:SfDomainUpDown x:Name="domainUpDown"

                               HorizontalAlignment="Center"

                               VerticalAlignment="Center"

                               Width="200"

ItemsSource="{Binding Employees}" >

                </editors:SfDomainUpDown>

            </Grid>

   </Page>
{% endhighlight %}

N>  If the ContentTemplate property of the SfDomainUpDown control is not set, Items will be displayed as business objects in the control.



## ContentTemplate

ContentTemplate helps the user decorate the content with visual elements. At this point, the control is populated with list of employees, and the Employee model contains two properties: Name and Email. In this example, the control is set to display content based on Name.

{% highlight xaml %}

<editors:SfDomainUpDown x:Name="domainUpDown"

                               HorizontalAlignment="Center"

                               VerticalAlignment="Center"

                               Width="200"

                              ItemsSource="{Binding Employees}">

<editors:SfDomainUpDown.ContentTemplate>

                <DataTemplate>

                    <StackPanel Orientation="Horizontal">

                        <Image Height="24" Width="24" Source="Image.png"/>

                        <TextBlock Text="{Binding Name}"/>

                    </StackPanel>

                </DataTemplate>

            </editors:SfDomainUpDown.ContentTemplate>

</editors:SfDomainUpDown>

{% endhighlight %}


![Features_img2](Features_images/Features_img2.png)
