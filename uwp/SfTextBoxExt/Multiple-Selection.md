---
layout: post
title: Multi Selection in Syncfusion SfTextBoxExt control
description: Learn how to give Multi Selection to the AutoComplete in the SfTextBoxExt control.
platform: uwp
control: SfTextBoxExt
documentation: ug
---
# Multiple Selection

Select multiple items from a suggestion list. There are two ways to perform multi selection in autocomplete.

* Token Representation

*  Delimiter

## Token Representation

Selected items will be displayed with a customizable token representation and the users can remove each tokenized item with the close button.

{% tabs %}

{% highlight xaml %}

<Page
    x:Class="TextBoxExtSample.MainPage"
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
    xmlns:local="using:TextBoxExtSample"
    xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
    xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
    xmlns:editors="using:Syncfusion.UI.Xaml.Controls.Input"
    mc:Ignorable="d"
    xmlns:ListCollection="using:System.Collections.Generic"
    Background="{ThemeResource ApplicationPageBackgroundThemeBrush}">
    <Grid Background="{StaticResource ApplicationPageBackgroundThemeBrush}">

        <editors:SfTextBoxExt x:Name="textBoxExt" 
                              HorizontalAlignment="Center" 
                              VerticalAlignment="Center" 
                              AutoCompleteMode="Suggest"
                              Width="200"
                              MultiSelectMode="Token"
                              TokensWrapMode="Wrap">
        </editors:SfTextBoxExt>
    </Grid>
</Page>

{% endhighlight %}

{% highlight c# %}

using Syncfusion.UI.Xaml.Controls.Input;
using System.Collections.Generic;
using Windows.UI.Xaml;
using Windows.UI.Xaml.Controls;

// The Blank Page item template is documented at https://go.microsoft.com/fwlink/?LinkId=402352&clcid=0x409

namespace TextBoxExtSample
{
    /// <summary>
    /// An empty page that can be used on its own or navigated to within a Frame.
    /// </summary>
    public sealed partial class MainPage : Page
    {
        //TextBlock SearchLabel;
        public MainPage()
        {
            this.InitializeComponent();
            SfTextBoxExt textBoxExt = new SfTextBoxExt()
            {
                HorizontalAlignment = HorizontalAlignment.Center,
                VerticalAlignment = VerticalAlignment.Center,
                Width = 200,
                AutoCompleteMode = AutoCompleteMode.Suggest,
                MultiSelectMode = MultiSelectMode.Token,
                TokensWrapMode = TokensWrapMode.Wrap
            };

            List<string> list = new List<string>()
            {
                "India",
                "Ukanda",
                "Ukraine",
                "Canada",
                "United Arab Emirates"
            };

            textBoxExt.AutoCompleteSource = list;
            this.Content = textBoxExt;
        }
    }
}

{% endhighlight %}

{% endtabs %}

### Wrap Mode of Token

The selected item can be displayed as token inside AutoComplete in two ways. They are

* `Wrap` - When `TokensWrapMode` is set to `Wrap` the selected items will be wrap to the next line of the AutoComplete.

* `None` - When `TokensWrapMode` is set to `None` the selected item will be wrap in horizontal orientation.

{% tabs %}

{% highlight xaml %}

<Page
    x:Class="TextBoxExtSample.MainPage"
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
    xmlns:local="using:TextBoxExtSample"
    xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
    xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
    xmlns:editors="using:Syncfusion.UI.Xaml.Controls.Input"
    mc:Ignorable="d"
    Background="{ThemeResource ApplicationPageBackgroundThemeBrush}">
    <Page.DataContext>
        <local:EmployeeViewModel/>
    </Page.DataContext>
    <Grid Background="{StaticResource ApplicationPageBackgroundThemeBrush}">

        <editors:SfTextBoxExt x:Name="textBoxExt" 
                              HorizontalAlignment="Center" 
                              VerticalAlignment="Center" 
                              AutoCompleteMode="Suggest"
                              Width="200"
                              SearchItemPath="Name"
                              MultiSelectMode="Token"
                              TokensWrapMode="Wrap"
                              AutoCompleteSource="{Binding EmployeeCollection}">
        </editors:SfTextBoxExt>
    </Grid>
</Page>

{% endhighlight %}

{% highlight c# %}

using Syncfusion.UI.Xaml.Controls.Input;
using System.Collections.Generic;
using System.Collections.ObjectModel;
using Windows.UI;
using Windows.UI.Xaml;
using Windows.UI.Xaml.Controls;
using Windows.UI.Xaml.Media;

// The Blank Page item template is documented at https://go.microsoft.com/fwlink/?LinkId=402352&clcid=0x409

namespace TextBoxExtSample
{
    /// <summary>
    /// An empty page that can be used on its own or navigated to within a Frame.
    /// </summary>
    public sealed partial class MainPage : Page
    {
        public MainPage()
        {
            this.InitializeComponent();
            EmployeeViewModel employeeCollection = new EmployeeViewModel();
            this.DataContext = employeeCollection;
            SfTextBoxExt textBoxExt = new SfTextBoxExt()
            {
                HorizontalAlignment = HorizontalAlignment.Center,
                VerticalAlignment = VerticalAlignment.Center,
                Width = 200,
                AutoCompleteMode = AutoCompleteMode.Suggest,
                SearchItemPath = "Name",
                MultiSelectMode = MultiSelectMode.Token,
                TokensWrapMode = TokensWrapMode.Wrap
            };

            textBoxExt.AutoCompleteSource = employeeCollection.EmployeeCollection;

            this.Content = textBoxExt;
        }
    }

    public class Employee
    {
        private string image;

        private string name;

        public string Image
        {
            get
            {
                return image;
            }

            set
            {
                image = value;
            }
        }

        public string Name
        {
            get
            {
                return name;
            }

            set
            {
                name = value;
            }
        }
    }

    public class EmployeeViewModel
    {
        private ObservableCollection<Employee> employeeCollection;

        public ObservableCollection<Employee> EmployeeCollection
        {
            get
            {
                return employeeCollection;
            }

            set
            {
                employeeCollection = value;
            }
        }
        public EmployeeViewModel()
        {
            EmployeeCollection = new ObservableCollection<Employee>();
            EmployeeCollection.Add(new Employee() { Image = "John.png", Name = "John" });
            EmployeeCollection.Add(new Employee() { Image = "James.png", Name = "James" });
            EmployeeCollection.Add(new Employee() { Image = "Jacob.png", Name = "Jacob" });
            EmployeeCollection.Add(new Employee() { Image = "Joy.png", Name = "Joy" });
            EmployeeCollection.Add(new Employee() { Image = "Justin.png", Name = "Justin" });
            EmployeeCollection.Add(new Employee() { Image = "Jerome.png", Name = "Jerome" });
            EmployeeCollection.Add(new Employee() { Image = "Jessica.png", Name = "Jessica" });
            EmployeeCollection.Add(new Employee() { Image = "Victoria.png", Name = "Victoria" });
        }
    }
}

{% endhighlight %}

{% endtabs %}


![token represents with image and text with wrap mode](images/MultiSelect/TokenRepresentation_Wrap.png)
 
### Token Customization

Customization can be done for Token. There are various ways to customize the tokens. They are as follows.

* `Foreground` - sets the color of the text inside the token.

* `FontSize` - sets the size of the Font inside the token.

* `FontFamily` - sets the Font family for the text inside the token.

* `Background` - sets the background color of the token.

* `ShowDeleteButton` - Enables and disables the close button inside AutoComplete.

* `DeleteButtonColor` - sets the color of the close button inside AutoComplete.

* `DeleteButtonAlignment` - sets the placement of delete button. `Left` and `Right` are the placement options. By default, it is set placed at right side of the token. 

N> SelectedBackgroundColor and CornerRadius support has enhanced only on iOS and Android platform.

{% tabs %}

{% highlight xaml %}

<Page
    x:Class="TextBoxExtSample.MainPage"
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
    xmlns:local="using:TextBoxExtSample"
    xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
    xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
    xmlns:editors="using:Syncfusion.UI.Xaml.Controls.Input"
    mc:Ignorable="d"
    Background="{ThemeResource ApplicationPageBackgroundThemeBrush}">
    <Page.DataContext>
        <local:EmployeeViewModel/>
    </Page.DataContext>
    <Grid Background="{StaticResource ApplicationPageBackgroundThemeBrush}">

        <editors:SfTextBoxExt x:Name="textBoxExt" 
                              HorizontalAlignment="Center" 
                              VerticalAlignment="Center" 
                              AutoCompleteMode="Suggest"
                              Width="200"
                              SearchItemPath="Name"
                              MultiSelectMode="Token"
                              TokensWrapMode="Wrap"
                              AutoCompleteSource="{Binding EmployeeCollection}">
            <editors:SfTextBoxExt.TokenSettings>
                <editors:TokenSettings  
                    FontSize="16"
                    Background="SkyBlue"
                    Foreground="White" 
                    DeleteButtonColor="Brown"
                    FontFamily="Times New Roman"
                    DeleteButtonAlignment="Right"
                    ShowDeleteButton="true"/>
            </editors:SfTextBoxExt.TokenSettings>
        </editors:SfTextBoxExt>
    </Grid>
</Page>

{% endhighlight %}

{% highlight c# %}

using Syncfusion.UI.Xaml.Controls.Input;
using System.Collections.Generic;
using System.Collections.ObjectModel;
using Windows.UI;
using Windows.UI.Xaml;
using Windows.UI.Xaml.Controls;
using Windows.UI.Xaml.Media;

// The Blank Page item template is documented at https://go.microsoft.com/fwlink/?LinkId=402352&clcid=0x409

namespace TextBoxExtSample
{
    /// <summary>
    /// An empty page that can be used on its own or navigated to within a Frame.
    /// </summary>
    public sealed partial class MainPage : Page
    {
        public MainPage()
        {
            this.InitializeComponent();
            EmployeeViewModel employeeCollection = new EmployeeViewModel();
            this.DataContext = employeeCollection;
            SfTextBoxExt textBoxExt = new SfTextBoxExt()
            {
                HorizontalAlignment = HorizontalAlignment.Center,
                VerticalAlignment = VerticalAlignment.Center,
                Width = 200,
                AutoCompleteMode = AutoCompleteMode.Suggest,
                SearchItemPath = "Name",
                MultiSelectMode = MultiSelectMode.Token,
                TokensWrapMode = TokensWrapMode.Wrap
            };

            TokenSettings tokenSettings = new TokenSettings()
            {
                FontSize = 16,
                Background = new SolidColorBrush(Colors.SkyBlue),
                Foreground = new SolidColorBrush(Colors.White),
                DeleteButtonColor = new SolidColorBrush(Colors.Brown),
                FontFamily = new FontFamily("Times New Roman"),
                DeleteButtonAlignment = DeleteButtonAlignment.Right,
                ShowDeleteButton = true
            };

            textBoxExt.TokenSettings = tokenSettings;
            textBoxExt.AutoCompleteSource = employeeCollection.EmployeeCollection;

            this.Content = textBoxExt;
        }
    }

    public class Employee
    {
        private string image;

        private string name;

        public string Image
        {
            get
            {
                return image;
            }

            set
            {
                image = value;
            }
        }

        public string Name
        {
            get
            {
                return name;
            }

            set
            {
                name = value;
            }
        }
    }

    public class EmployeeViewModel
    {
        private ObservableCollection<Employee> employeeCollection;

        public ObservableCollection<Employee> EmployeeCollection
        {
            get
            {
                return employeeCollection;
            }

            set
            {
                employeeCollection = value;
            }
        }
        public EmployeeViewModel()
        {
            EmployeeCollection = new ObservableCollection<Employee>();
            EmployeeCollection.Add(new Employee() { Image = "John.png", Name = "John" });
            EmployeeCollection.Add(new Employee() { Image = "James.png", Name = "James" });
            EmployeeCollection.Add(new Employee() { Image = "Jacob.png", Name = "Jacob" });
            EmployeeCollection.Add(new Employee() { Image = "Joy.png", Name = "Joy" });
            EmployeeCollection.Add(new Employee() { Image = "Justin.png", Name = "Justin" });
            EmployeeCollection.Add(new Employee() { Image = "Jerome.png", Name = "Jerome" });
            EmployeeCollection.Add(new Employee() { Image = "Jessica.png", Name = "Jessica" });
            EmployeeCollection.Add(new Employee() { Image = "Victoria.png", Name = "Victoria" });
        }
    }
}

{% endhighlight %}

![token represents the image and text with closebutton](images/MultiSelect/TokenRepresentation.png)

## Delimiter

When selecting the multiple items, the selected items can be divided with a desired character given for a delimiter. We can set delimiter character with the `Delimiter` property.

using Syncfusion.UI.Xaml.Controls.Input;
using System.Collections.Generic;
using Windows.UI.Xaml;
using Windows.UI.Xaml.Controls;

// The Blank Page item template is documented at https://go.microsoft.com/fwlink/?LinkId=402352&clcid=0x409

namespace TextBoxExtSample
{
    /// <summary>
    /// An empty page that can be used on its own or navigated to within a Frame.
    /// </summary>
    public sealed partial class MainPage : Page
    {
        //TextBlock SearchLabel;
        public MainPage()
        {
            this.InitializeComponent();
            SfTextBoxExt textBoxExt = new SfTextBoxExt()
            {
                HorizontalAlignment = HorizontalAlignment.Center,
                VerticalAlignment = VerticalAlignment.Center,
                Width = 200,
                AutoCompleteMode = AutoCompleteMode.Suggest,
                MultiSelectMode = MultiSelectMode.Delimiter,
                Delimiter = ","
            };

            List<string> list = new List<string>()
            {
                "India",
                "Ukanda",
                "Ukraine",
                "Canada",
                "United Arab Emirates"
            };

            textBoxExt.AutoCompleteSource = list;
            this.Content = textBoxExt;
        }
    }
}

{% endhighlight %}

{% endtabs %}

![delimiter supports to separate the items with delimiter text](images/MultiSelect/Delimiter.png)

{% endhighlight %}

{% endtabs %}



