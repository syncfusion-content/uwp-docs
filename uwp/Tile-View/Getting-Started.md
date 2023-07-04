---
layout: post
title: Getting Started with UWP Tile View control | Syncfusion
description: Learn here about getting started with Syncfusion UWP Tile View (SfTileView) control, its elements and more.
platform: uwp
control: SfTileView
documentation: ug
---

# Getting Started with UWP Tile View (SfTileView)

This section explains how to create views as tiles using the `SfTileView` control.

## Adding SfTileView control

Create a Universal Windows Platform project in Visual Studio and refer to the following assemblies.

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

<layout:SfTileView x:Name="tileView">

{% endhighlight %}

{% highlight C# %}

SfTileView tileView = new SfTileView();

{% endhighlight %}

{% highlight VB %}

Dim tileView As New SfTileView()

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
        public Person(string name, string image, double seconds, string position, string organizationUnit, string dateOfBirth, string location, string phone, string email, string color, string headerColor)
        {
            Name = name;
            Image = image;
            Interval = TimeSpan.FromSeconds(seconds);
            Position = position;
            OrganizationUnit = organizationUnit;
            DateOfBirth = dateOfBirth;
            Location = location;
            Phone = phone;
            Email = email;
            TileColor = color;
            HeaderColor = headerColor;
        }
    }    


{% endhighlight %}

{% highlight VB %}

Public Class Person
		Public Property Name() As String
		Public Property Image() As String
		Public Property Interval() As TimeSpan
		Public Property Position() As String
		Public Property OrganizationUnit() As String
		Public Property DateOfBirth() As String
		Public Property Location() As String
		Public Property Phone() As String
		Public Property Email() As String
		Public Property TileColor() As String
		Public Property HeaderColor() As String
		Public Sub New(ByVal name As String, ByVal image As String, ByVal seconds As Double, ByVal position As String, ByVal organizationUnit As String, ByVal dateOfBirth As String, ByVal location As String, ByVal phone As String, ByVal email As String, ByVal color As String, ByVal headerColor As String)
			Me.Name = name
			Me.Image = image
			Interval = TimeSpan.FromSeconds(seconds)
			Me.Position = position
			Me.OrganizationUnit = organizationUnit
			Me.DateOfBirth = dateOfBirth
			Me.Location = location
			Me.Phone = phone
			Me.Email = email
			TileColor = color
			Me.HeaderColor = headerColor
		End Sub
End Class

{% endhighlight %}

{% endtabs %}

2.Define and populate the collection in ViewModel class:

{% tabs %}

{% highlight C# %}

public class TileViewModel: NotificationObject

    {
        private Random random;
		
        private double GetInterval()
		
        {
			
            return random.Next(18, 25);
			
        }
		
        public TileViewModel()
		
        {
			
            random = new Random();
			
            TileViewItems = new ObservableCollection<Person>();
			
            TileViewItems.Add(new Person("Eric Joplin", "Assets/Employee2.png", GetInterval(), "Chairman", "Management", "27/09/1973", "Boston", "+800 9899 9929", "EricJoplin@syncfusion.com", "#FFA400", "#E78E00"));
			
            TileViewItems.Add(new Person("Paul Vent", "Assets/Employee4.png", GetInterval(), "Chief Executive Officer", "Management", "27/09/1975", "New York", "+800 9899 9930", "PaulVent@syncfusion.com", "#6DA4A3", "#4E7F7D"));
			
            TileViewItems.Add(new Person("Clara Venus", "Assets/Employee6.png", GetInterval(), "Chief Executive Assistant", "Management", "27/09/1978", "California", "+800 9899 9931", "ClaraVenus@syncfusion.com", "#A45378", "#883F64"));
			
            TileViewItems.Add(new Person("Maria Even", "Assets/Employee11.png", GetInterval(), "Executive Manager", "Operational Unit", "27/09/1970", "New York", "+800 9899 9932", "MariaEven@syncfusion.com", "#DA9545", "#BB7731"));
			
            TileViewItems.Add(new Person("Mark", "Assets/Employee13.png", GetInterval(), "Senior Executive", "Operational Unit", "27/09/1983", "Boston", "+800 9899 9933", "Mark@syncfusion.com", "#AC3832", "#8B2826"));
			
            TileViewItems.Add(new Person("Robin", "Assets/Employee16.png", GetInterval(), "Manager", "Customer Service", "27/09/1985", "New Jersey", "+800 9899 9934", "Robin@syncfusion.com", "#31A1FF", "#2394E1"));
			
            TileViewItems.Add(new Person("Chris Marker", "Assets/Employee21.png", GetInterval(), "Team Manager", "Customer Service", "27/09/1963", "California", "+800 9899 9935", "ChrisMarker@syncfusion.com", "#5B5BA9", "#484892"));
			
            TileViewItems.Add(new Person("James Michael", "Assets/Employee23.png", GetInterval(), "Coordinator", "Customer Service", "27/09/1961", "New York", "+800 9899 9936", "JamesMichael@syncfusion.com", "#597C2A", "#46601D"));
			
            TileViewItems.Add(new Person("Mathew Fleming", "Assets/Employee25.png", GetInterval(), "Recruitment Manager", "Human Resource", "27/09/1986", "Boston", "+800 9899 9937", "MathewFleming@syncfusion.com", "#BCCBD3", "#8BA0A9"));
			
        }

        private ObservableCollection<Person> items;
		
        public ObservableCollection<Person> TileViewItems
		
        {
			
            get { return items; }
			
            set { items = value; }
			
        } 
    }


{% endhighlight %}

{% highlight VB %}

Public Class TileViewModel

	Inherits NotificationObject

		Private random As Random

		Private Function GetInterval() As Double


			Return random.Next(18, 25)

		End Function

		Public Sub New()


			random = New Random()

			TileViewItems = New ObservableCollection(Of Person)()

			TileViewItems.Add(New Person("Eric Joplin", "Assets/Employee2.png", GetInterval(), "Chairman", "Management", "27/09/1973", "Boston", "+800 9899 9929", "EricJoplin@syncfusion.com", "#FFA400", "#E78E00"))

			TileViewItems.Add(New Person("Paul Vent", "Assets/Employee4.png", GetInterval(), "Chief Executive Officer", "Management", "27/09/1975", "New York", "+800 9899 9930", "PaulVent@syncfusion.com", "#6DA4A3", "#4E7F7D"))

			TileViewItems.Add(New Person("Clara Venus", "Assets/Employee6.png", GetInterval(), "Chief Executive Assistant", "Management", "27/09/1978", "California", "+800 9899 9931", "ClaraVenus@syncfusion.com", "#A45378", "#883F64"))

			TileViewItems.Add(New Person("Maria Even", "Assets/Employee11.png", GetInterval(), "Executive Manager", "Operational Unit", "27/09/1970", "New York", "+800 9899 9932", "MariaEven@syncfusion.com", "#DA9545", "#BB7731"))

			TileViewItems.Add(New Person("Mark", "Assets/Employee13.png", GetInterval(), "Senior Executive", "Operational Unit", "27/09/1983", "Boston", "+800 9899 9933", "Mark@syncfusion.com", "#AC3832", "#8B2826"))

			TileViewItems.Add(New Person("Robin", "Assets/Employee16.png", GetInterval(), "Manager", "Customer Service", "27/09/1985", "New Jersey", "+800 9899 9934", "Robin@syncfusion.com", "#31A1FF", "#2394E1"))

			TileViewItems.Add(New Person("Chris Marker", "Assets/Employee21.png", GetInterval(), "Team Manager", "Customer Service", "27/09/1963", "California", "+800 9899 9935", "ChrisMarker@syncfusion.com", "#5B5BA9", "#484892"))

			TileViewItems.Add(New Person("James Michael", "Assets/Employee23.png", GetInterval(), "Coordinator", "Customer Service", "27/09/1961", "New York", "+800 9899 9936", "JamesMichael@syncfusion.com", "#597C2A", "#46601D"))

			TileViewItems.Add(New Person("Mathew Fleming", "Assets/Employee25.png", GetInterval(), "Recruitment Manager", "Human Resource", "27/09/1986", "Boston", "+800 9899 9937", "MathewFleming@syncfusion.com", "#BCCBD3", "#8BA0A9"))

		End Sub

		Private items As ObservableCollection(Of Person)

		Public Property TileViewItems() As ObservableCollection(Of Person)


			Get
				Return items
			End Get

			Set(ByVal value As ObservableCollection(Of Person))
				items = value
			End Set

		End Property
End Class

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
  TileViewItem contains the details about the Employee like Name, DateOfBirth, Phone Number, Email, Organization details etc.
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

![Adding UWP TileView control](overview-images/uwp-adding-tile-view-control.jpeg)