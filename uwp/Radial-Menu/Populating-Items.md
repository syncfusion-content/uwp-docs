---
layout: post
title: Populating Items in UWP Radial Menu control | Syncfusion
description: Learn here all about Populating Items support in Syncfusion UWP Radial Menu (SfRadialMenu) control and more.
platform: uwp
control: SfRadial Menu 
documentation: ug
---

# Populating Items in UWP Radial Menu (SfRadialMenu)

## Items Source  

Radial menu items can be populated with the business object collection. Let us create a SfRadialMenu which will show the list of Application commands.   

The Application command model look likes below.  

{% tabs %}

{% highlight c# %}  

  public class ApplicationCommand

    {

        public string Name { get; set; }



        public string ImagePath { get; set; }



        public ICommand Command { get; set; }

    }

{% endhighlight %}

{% highlight VB %}  

  Public Class ApplicationCommand


		Public Property Name() As String



		Public Property ImagePath() As String



		Public Property Command() As ICommand

End Class

{% endhighlight %}

{% endtabs %}


Create the Application command collection as follows. 

{% tabs %}

{% highlight c# %}

private List<ApplicationCommand> options;

public List<ApplicationCommand> Options

   {

            get { return options; }

            set { options = value; }

   }

{% endhighlight %}

{% highlight VB %}

Private options_Renamed As List(Of ApplicationCommand)

Public Property Options() As List(Of ApplicationCommand)


			Get
				Return options_Renamed
			End Get

			Set(ByVal value As List(Of ApplicationCommand))
				options_Renamed = value
			End Set

End Property

{% endhighlight %}

{% endtabs %}

Populate the Application command collection as follows. 

{% tabs %}

{% highlight c# %}

 Options = new List<ApplicationCommand>(); 

 Options.Add(new ApplicationCommand() { Name="Bold" , ImagePath="bold.png" });    			  
 
 Options.Add(new ApplicationCommand() { Name = "Cut" , ImagePath="cut.png"}); 

 Options.Add(new ApplicationCommand() { Name = "Copy" ,ImagePath="copy.png"}); 

 Options.Add(new ApplicationCommand() { Name = "Paste" ,ImagePath="paste.png"});

{% endhighlight %}

{% highlight VB %}

 Options = New List(Of ApplicationCommand)()

 Options.Add(New ApplicationCommand() With {
	 .Name="Bold",
	 .ImagePath="bold.png"
 })

 Options.Add(New ApplicationCommand() With {
	 .Name = "Cut",
	 .ImagePath="cut.png"
 })

 Options.Add(New ApplicationCommand() With {
	 .Name = "Copy",
	 .ImagePath="copy.png"
 })

 Options.Add(New ApplicationCommand() With {
	 .Name = "Paste",
	 .ImagePath="paste.png"
 })

{% endhighlight %}

{% endtabs %}

Bind the Application command collection to the ItemsSource property of the SfRadialMenu control. 

{% highlight xaml %}

<navigation:SfRadialMenu IsOpen="True" ItemsSource="{Binding Options}"/>

{% endhighlight %}

This will populate the SfRadialMenu as shown in the image below. 

![RadialMenu Initial view](Populating-Items_images/Populating-Items_img1.png)



### Display Member Path 

DisplayMemberPath property of the SfRadialMenu used to define which business model property needs to be displayed inside the header of the SfRadialMenu items.  

{% highlight xaml %}



<navigation:SfRadialMenu IsOpen="True" ItemsSource="{Binding Options}"

DisplayMemberPath="Name"/>



{% endhighlight %}
![RadialMenu Display Member Path view](Populating-Items_images/Populating-Items_img2.png)

### Command Path

CommandPath property of the SfRadialMenu can be used to bind the command in the business object to the SfRadialMenu item when items are populated using data binding. 

{% highlight xaml %}



<navigation:SfRadialMenu IsOpen="True" DisplayMemberPath="Name" CommandPath="Command"

                                 ItemsSource="{Binding Options}" />


{% endhighlight %}

### Item Template 

ItemTemplate property of the SfRadialMenu can be used to customize the header part of the SfRadialMenu items.  

{% highlight xaml %}   

<navigation:SfRadialMenu IsOpen="True" ItemsSource="{Binding Options}">

            <navigation:SfRadialMenu.ItemTemplate>

                <DataTemplate>

                    <StackPanel >

                        <Image Height="15" Width="15" Source="{Binding ImagePath}"/>

                        <TextBlock Margin="0,5,0,0" Text="{Binding Name}"/>

                    </StackPanel>

                </DataTemplate>

            </navigation:SfRadialMenu.ItemTemplate>

   </navigation:SfRadialMenu>

{% endhighlight %}


![RadialMenu Itemtemplate view](Populating-Items_images/Populating-Items_img3.png)







