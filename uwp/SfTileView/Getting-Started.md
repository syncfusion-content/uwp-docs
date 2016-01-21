---
layout: post
title: Getting Started with SfTileView control for UWP
description: Getting Started with SfTileView control for UWP
platform: uwp
control: SfTileView
documentation: ug
---

# Getting Started

This section explains how to create views as tiles using the `SfTileView` control.

## Adding SfTileView control

Create a Universal Windows project in Visual Studio and refer to the following assemblies.

* Syncfusion.SfTileView.UWP
* Syncfusion.SfShared.UWP

1.Include the namespace for Syncfusion.SfTileView.UWP assembly in MainPage.xaml

{% tabs %}

{% highlight XAML %}

<Page xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"

xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"

xmlns:layout="using:Syncfusion.UI.Xaml.Controls.Layout">

{% endhighlight %}

{% endtabs %}

2.Now add the `SfTileView` control with a required optimal name using the included namespace

{% tabs %}

{% highlight XAML %}

<layout:SfTileView x:Name="hubTile">

{% endhighlight %}

{% endtabs %}

### Implement the Model and ViewModel

Each tile view item, require Content and `MaximizedContent` property to be set. For coding simplicity, ItemsSource binding is used in this example.

1.Define the properties required in Model class:

{% tabs %}

{% highlight C# %}

public class Person
    {
        public string Name { get; set; }
        public string Image { get; set; }
        public TimeSpan Interval { get; set; }
        public string Position { get; set; }
        public string OrganizationUnit { get; set; }
        public string DateOfBirth { get; set; }
        public string Location { get; set; }
        public string Phone { get; set; }
        public string Email { get; set; }
        public string TileColor { get; set; }
        public string HeaderColor { get; set; }
        public Person(string name, string image, double seconds, string position, string organizationunit, string dateofbirth, string location, string phone, string email, string color, string headercolor)
        {
            Name = name;
            Image = image;
            Interval = TimeSpan.FromSeconds(seconds);
            Position = position;
            OrganizationUnit = organizationunit;
            DateOfBirth = dateofbirth;
            Location = location;
            Phone = phone;
            Email = email;
            TileColor = color;
            HeaderColor = headercolor;
        }
    }    


{% endhighlight %}

{% endtabs %}

2.Define and populate the collection in ViewModel class:

{% tabs %}

{% highlight C# %}

public class TileViewModel: NotificationObject

    {
        private Random rndm;
		
        private double GetInterval()
		
        {
			
            return rndm.Next(18, 25);
			
        }
		
        public TileViewModel()
		
        {
			
            rndm = new Random();
			
            TileViewItems = new ObservableCollection<Person>();
			
            TileViewItems.Add(new Person("Eric Joplin", "Assets/Emp_02.png", GetInterval(), "Chairman", "Management", "27/09/1973", "Boston", "+800 9899 9929", "ericjoplin@syncfusion.com", "#FFA400", "#E78E00"));
			
            TileViewItems.Add(new Person("Paul Vent", "Assets/Emp_04.png", GetInterval(), "Chief Executive Officer", "Management", "27/09/1975", "New York", "+800 9899 9930", "paulvent@syncfusion.com", "#6DA4A3", "#4E7F7D"));
			
            TileViewItems.Add(new Person("Clara Venus", "Assets/Emp_06.png", GetInterval(), "Chief Executive Assistant", "Management", "27/09/1978", "California", "+800 9899 9931", "claravenus@syncfusion.com", "#A45378", "#883F64"));
			
            TileViewItems.Add(new Person("Maria Even", "Assets/Emp_11.png", GetInterval(), "Executive Manager", "Operational Unit", "27/09/1970", "New York", "+800 9899 9932", "mariaeven@syncfusion.com", "#DA9545", "#BB7731"));
			
            TileViewItems.Add(new Person("Mark Zuen", "Assets/Emp_13.png", GetInterval(), "Senior Executive", "Operational Unit", "27/09/1983", "Boston", "+800 9899 9933", "markzuen@syncfusion.com", "#AC3832", "#8B2826"));
			
            TileViewItems.Add(new Person("Robin Rane", "Assets/Emp_16.png", GetInterval(), "Manager", "Customer Service", "27/09/1985", "New Jersey", "+800 9899 9934", "robinrane@syncfusion.com", "#31A1FF", "#2394E1"));
			
            TileViewItems.Add(new Person("Chris Marker", "Assets/Emp_21.png", GetInterval(), "Team Manager", "Customer Service", "27/09/1963", "California", "+800 9899 9935", "chrismarker@syncfusion.com", "#5B5BA9", "#484892"));
			
            TileViewItems.Add(new Person("Seria Sum", "Assets/Emp_23.png", GetInterval(), "Coordinator", "Customer Service", "27/09/1961", "New York", "+800 9899 9936", "seriasum@syncfusion.com", "#597C2A", "#46601D"));
			
            TileViewItems.Add(new Person("Mathew Fleming", "Assets/Emp_25.png", GetInterval(), "Recruitment Manager", "Human Resource", "27/09/1986", "Boston", "+800 9899 9937", "mathewfleming@syncfusion.com", "#BCCBD3", "#8BA0A9"));
			
        }

        private ObservableCollection<Person> items;
		
        public ObservableCollection<Person> TileViewItems
		
        {
			
            get { return items; }
			
            set { items = value; }
			
        } 
    }


{% endhighlight %}

{% endtabs %}

### Design view for content and maximized content

Bind the view model collection to `ItemSource` property and design the templates for content and maximized content as given below:

{% tabs %}

{% highlight XAML %}

<layout:SfTileView Width="880" Height="500"
                   x:Name="tileView" Margin="20 0"
				   HorizontalAlignment="Left"
				   VerticalAlignment="Top"
				   ItemsSource="{Binding TileViewItems}"
				   SelectedIndex="0"
				   ItemWidth="250" ItemHeight="160">
				   
<layout:SfTileView.MaximizedItemTemplate>

<DataTemplate>

<Border Background="{Binding TileColor}">

<Grid>

<Grid.RowDefinitions>

<RowDefinition Height="Auto"/>
<RowDefinition Height="Auto"/>
<RowDefinition Height="Auto"/>
<RowDefinition Height="Auto"/>

</Grid.RowDefinitions>

<Grid.ColumnDefinitions>

<ColumnDefinition Width="150"/>
<ColumnDefinition Width="*"/>

</Grid.ColumnDefinitions>

<Grid  Grid.ColumnSpan="2" Background="{Binding HeaderColor}"
                           Tapped="Restore">

<TextBlock Text="{Binding Name}" FontSize="25"
           Margin="20" Foreground="White"/>
		   
</Grid>

<Grid Width="100" Height="100" Background="White"
      Grid.Row="1" Margin="0 20 0 0" Grid.Column="0">
	  
<Image Source="{Binding Image}"  Width="100" Height="100"/>

</Grid>

<StackPanel Orientation="Horizontal"
            Margin="0 20 0 0"
			Grid.Row="1" Grid.Column="1">
			
<Grid VerticalAlignment="Top">

<Grid.Resources>

<Style TargetType="TextBlock">

<Setter Property="FontSize" Value="14"/>

<Setter Property="Foreground" Value="White"/>

</Style>

</Grid.Resources>

<Grid.RowDefinitions>
<RowDefinition Height="25"/>
<RowDefinition Height="25"/>
<RowDefinition Height="25"/>
<RowDefinition Height="25"/>
</Grid.RowDefinitions>

<Grid.ColumnDefinitions>
<ColumnDefinition Width="150"/>
<ColumnDefinition/>
</Grid.ColumnDefinitions>

<TextBlock Text="Position "/>
<TextBlock Text="{Binding Position}" Grid.Column="1"/>
<TextBlock Text="Organization " Grid.Row="1"/>
<TextBlock Text="{Binding OrganizationUnit}"
           Grid.Row="1" Grid.Column="1"/>
		   <TextBlock Text="Date Of Birth " Grid.Row="2"/>
<TextBlock Text="{Binding DateOfBirth}"
           Grid.Row="2" Grid.Column="1"/>
<TextBlock Text="Location " Grid.Row="3"/>
<TextBlock Text="{Binding Location}" Grid.Row="3" Grid.Column="1"/>

</Grid>

</StackPanel>

<RichTextBlock Grid.ColumnSpan="2" Grid.Row="2"
               VerticalAlignment="Top"
			   TextWrapping="Wrap"
			   Margin="20" FontSize="14"
			   FontWeight="Light" Foreground="White">
			   
<Paragraph LineHeight="30">

<Run>
Lorem ipsum dolor sit amet, lacus amet amet ultricies. Quisque mi venenatis morbi libero, orci dis, mi ut et class porta,
massa ligula magna enim, aliquam orci vestibulum tempus.Turpis facilisis vitae consequat, cum a a, turpis dui consequat massa in dolor per, felis non amet.
Auctor eleifend in omnis elit vestibulum, donec non elementum tellus est mauris, id aliquam, at lacus, arcu pretium proin lacus dolor et.
Eu tortor, vel ultrices amet dignissim mauris vehicula. Lorem tortor neque, purus taciti quis id. Elementum integer orci accumsan minim phasellus vel.
Vestibulum duis integer diam mi libero felis,  amet aliquam sapien per tortor luctus.
</Run>

</Paragraph>

</RichTextBlock>

<StackPanel VerticalAlignment="Center" Margin="20 0"
            Orientation="Horizontal" Grid.Row="3"
			Grid.ColumnSpan="2">
<Grid>
<Grid.Resources>
<Style TargetType="TextBlock">
<Setter Property="FontSize" Value="14"/>
<Setter Property="Foreground" Value="White"/>
</Style>
</Grid.Resources>
<Grid.ColumnDefinitions>
<ColumnDefinition/>
<ColumnDefinition/>
<ColumnDefinition/>
<ColumnDefinition/>
</Grid.ColumnDefinitions>
<Image Source="Assets/Contact.png" Margin="5 0" />
<TextBlock Text="{Binding Phone}" Grid.Column="1"
           Margin="5 0" VerticalAlignment="Center"/>
<Image Source="Assets/Mail.png" Grid.Column="2" Margin="5 0" />
<TextBlock Text="{Binding Email}" Grid.Column="3" Margin="5 0"
                                  VerticalAlignment="Center"/>
</Grid>
</StackPanel>

</Grid>
</Border>
</DataTemplate>
</layout:SfTileView.MaximizedItemTemplate>
<layout:SfTileView.ItemTemplate>
<DataTemplate>
<Grid>
<Notification:SfHubTile Width="250" Height="160"
                        Foreground="White"
						ScaleDepth="0.9"
						RotationDepth="10"
						Padding="2"
						Background="{Binding TileColor}">

<Notification:SfHubTile.Content>
<Grid>
<Grid.RowDefinitions>
<RowDefinition Height="*"/>
<RowDefinition Height="Auto"/>
</Grid.RowDefinitions>
<Image Source="{Binding Image}" Stretch="Uniform"
       Width="250"/>
<Grid Background="{Binding HeaderColor}" Grid.Row="1">
<TextBlock Text="{Binding Name}" FontSize="14"
           Margin="8" HorizontalAlignment="Stretch"/>
</Grid>
</Grid>
</Notification:SfHubTile.Content>

</Notification:SfHubTile>
</Grid>
</DataTemplate>
</layout:SfTileView.ItemTemplate>
</layout:SfTileView>

{% endhighlight %}

{% endtabs %}


{% tabs %}

{% highlight C# %}

void Restore(object sender, TappedRoutedEventArgs e)

{
	
      tileView.SelectedIndex = -1;
	  
}


{% endhighlight %}

{% endtabs %}

![](Overview-images/Overview-img1.jpeg)