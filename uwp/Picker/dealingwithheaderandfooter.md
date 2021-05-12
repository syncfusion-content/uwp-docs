---
layout: post
title: Dealing with Header and Footer in UWP Picker control | Syncfusion
description: Learn here all about Dealing with Header and Footer support in Syncfusion UWP Picker (SfPicker) control and more.
platform: Xamarin
control: Picker
documentation: ug
---

# Dealing with Header and Footer in UWP Picker (SfPicker)

This section explains about the header and footer customization of SfPicker.

## Enable or Disable Header 

SfPicker allows enabling or disabling the header section by setting `SfPicker.ShowHeader` property to True or False. Default value of `SfPicker.ShowHeader` property is True.

{% tabs %}

{% highlight xaml %}
 
    <Page
        x:Class="DealingHeaderFooter.MainPage"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:local="using:DealingHeaderFooter"
        xmlns:syncfusion="using:Syncfusion.UI.Xaml.Controls.Input">
       
        <Grid>

             <syncfusion:SfPicker x:Name="picker" ShowHeader="False"  />
        
        </Grid>
    
    </Page>      

{% endhighlight %}

{% highlight c# %}

    using Syncfusion.UI.Xaml.Controls.Input;
    using Windows.UI.Xaml;

    namespace DealingHeaderFooter

     {

      public sealed partial class MainPage : Page

       {
           
        public MainPage()

        {

            this.InitializeComponent();

            SfPicker picker = new SfPicker();

            picker.ShowHeader = False;

            this.Content = picker;

        }

      }

    }

{% endhighlight %}

{% endtabs %}

## Set Custom Header 

SfPicker allows providing custom text to Header of SfPicker by setting `SfPicker.Header` property. Default value of `SfPicker.Header` property is Null.

{% tabs %}

{% highlight xaml %}
 
     <Page
        x:Class="DealingHeaderFooter.MainPage"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:local="using:DealingHeaderFooter"
        xmlns:syncfusion="using:Syncfusion.UI.Xaml.Controls.Input"
           
        <Grid>
           
            <syncfusion:SfPicker x:Name="picker" Header="Select a Date" />
        
        </Grid>
    
    </Page>      
      
{% endhighlight %}

{% highlight c# %}

    using Syncfusion.UI.Xaml.Controls.Input;
    using Windows.UI.Xaml;

    namespace DealingHeaderFooter

     { 

       public sealed partial class MainPage : Page

        {

        public MainPage()

        {

            this.InitializeComponent();

            SfPicker picker = new SfPicker();

            picker.Header = "Select a Color";

            this.Content = picker;

        }

       }

      }

{% endhighlight %}

{% endtabs %}

## Header Customization

SfPicker allows customizing Background, TextColor and Fonts.

### Background

Header background color can be customized  by setting `SfPicker.HeaderBackground` property of SfPicker.

{% tabs %}

{% highlight xaml %}

    <Page
        x:Class="DealingHeaderFooter.MainPage"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:local="using:DealingHeaderFooter"
        xmlns:syncfusion="using:Syncfusion.UI.Xaml.Controls.Input">
            
        <Grid>
           
             <syncfusion:SfPicker x:Name="picker" HeaderBackground="SkyBlue" />
        
        </Grid>
    
    </Page>      
      
{% endhighlight %}

{% highlight c# %}

    using Syncfusion.UI.Xaml.Controls.Input;
    using Windows.UI.Xaml;

    namespace DealingHeaderFooter

     { 

      public sealed partial class MainPage : Page

       {

        public MainPage()

        {

            this.InitializeComponent();

            SfPicker picker = new SfPicker();

            picker.HeaderBackground = new SolidColorBrush(Windows.UI.Colors.SkyBlue);

            this.Content = picker;

        }

       }

      }

{% endhighlight %}

{% endtabs %}

### Text Color 

Header text color can be customized by setting `SfPicker.HeaderForeground` property of SfPicker.

{% tabs %}

{% highlight xaml %}

    <Page
        x:Class="DealingHeaderFooter.MainPage"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:local="using:DealingHeaderFooter"
        xmlns:syncfusion="using:Syncfusion.UI.Xaml.Controls.Input">
            
        <Grid>
            
             <syncfusion:SfPicker x:Name="picker" HeaderForeground="Red" />
        
        </Grid>
    
    </Page>      
      
{% endhighlight %}


{% highlight c# %}

    using Syncfusion.UI.Xaml.Controls.Input;
    using Windows.UI.Xaml;

    namespace DealingHeaderFooter
 
     { 

      public sealed partial class MainPage : Page
 
       {

        public MainPage()

        {

            this.InitializeComponent();

            SfPicker picker = new SfPicker();

            picker.HeaderForeground = new SolidColorBrush(Windows.UI.Colors.Red);

            this.Content = picker;
      
        }

       }

      }

{% endhighlight %}

{% endtabs %}

### Font 

This section explains about the customization of Header text of Font.

#### 	FontFamily

Header text FontFamily can be customized by setting `SfPicker.HeaderFontFamily` property of SfPicker.

{% tabs %}

{% highlight xaml %}

    <Page
        x:Class="DealingHeaderFooter.MainPage"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:local="using:DealingHeaderFooter"
        xmlns:syncfusion="using:Syncfusion.UI.Xaml.Controls.Input"
           
        <Grid>
          
             <syncfusion:SfPicker x:Name="picker" HeaderFontFamily="Arial"/>
        
        </Grid>
    
    </Page>      
      
{% endhighlight %}

{% highlight c# %}

    using Syncfusion.UI.Xaml.Controls.Input;
    using Windows.UI.Xaml;

    namespace DealingHeaderFooter
 
     {

      public sealed partial class MainPage : Page
 
       {

        public MainPage()
 
        {

            this.InitializeComponent();
 
            SfPicker picker = new SfPicker();
 
            picker.HeaderFontFamily = new FontFamily("Arial");
 
            this.Content = picker;
        
        }
 
       }
 
      }

{% endhighlight %}

{% endtabs %}

#### 	FontSize

Header text FontSize can be customized by setting `SfPicker.HeaderFontSize` property of SfPicker.

{% tabs %}

{% highlight xaml %}

    <Page
        x:Class="DealingHeaderFooter.MainPage"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:local="using:DealingHeaderFooter"
        xmlns:syncfusion="using:Syncfusion.UI.Xaml.Controls.Input">
    
        <Grid>
           
            <syncfusion:SfPicker x:Name="picker" HeaderFontSize="20"/>
        
        </Grid>
    
    </Page>      
      
{% endhighlight %}

{% highlight c# %}

    using Syncfusion.UI.Xaml.Controls.Input;
    using Windows.UI.Xaml;

    namespace DealingHeaderFooter
 
     { 

      public sealed partial class MainPage : Page

       {

        public MainPage()

        {

            this.InitializeComponent();

            SfPicker picker = new SfPicker();

            picker.HeaderFontSize = 20;

            this.Content = picker;
        
        }

       }

      }

{% endhighlight %}

{% endtabs %}   

#### 	FontAttribute

Header text FontAttribute can be customized by setting `SfPicker.HeaderFontStyle` property of SfPicker.

{% tabs %}

{% highlight xaml %}

    <Page
        x:Class="DealingHeaderFooter.MainPage"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:local="using:DealingHeaderFooter"
        xmlns:syncfusion="using:Syncfusion.UI.Xaml.Controls.Input"
          
        <Grid>
           
            <syncfusion:SfPicker x:Name="picker" HeaderFontStyle="Italic"/>
        
        </Grid>
    
    </Page>    
	
{% endhighlight %}  
      
  
{% highlight c# %}

    using Syncfusion.UI.Xaml.Controls.Input;
    using Windows.UI.Xaml;

    namespace DealingHeaderFooter
 
     { 

      public sealed partial class MainPage : Page
 
       {

        public MainPage()
 
        {

            this.InitializeComponent();
 
            SfPicker picker = new SfPicker();
 
            picker.HeaderFontStyle= Windows.UI.Text.FontStyle.Italic;
 
            this.Content = picker;
      
        }
 
       }
 
      }

{% endhighlight %}

{% endtabs %}

## Enable or Disable Footer 

SfPicker allows enabling or disabling the footer section by setting `SfPicker.ShowFooter` property to True or False. Default value of `SfPicker.ShowFooter` property is False.

{% tabs %}

{% highlight xaml %}

    <Page
        x:Class="DealingHeaderFooter.MainPage"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:local="using:DealingHeaderFooter"
        xmlns:syncfusion="using:Syncfusion.UI.Xaml.Controls.Input">
          
        <Grid>
      
            <syncfusion:SfPicker x:Name="picker" ShowFooter="True"/>
      
        </Grid>
    
    </Page>      
      
{% endhighlight %}

{% highlight c# %}

    using Syncfusion.UI.Xaml.Controls.Input;
    using Windows.UI.Xaml;

    namespace DealingHeaderFooter
 
     {

      public sealed partial class MainPage : Page
 
       {

        public MainPage()
 
        {

            this.InitializeComponent();
 
            SfPicker picker = new SfPicker();
 
            picker.ShowFooter = true ;
 
            this.Content = picker;
        
        }
 
       }
 
      }
    
{% endhighlight %}

{% endtabs %}

## Set Custom Footer

SfPicker allows providing custom view to Footer of SfPicker by setting `SfPicker.Footer` property. Default value of `SfPicker.Footer` property is Null.

{% tabs %}

{% highlight xaml %}

    <Page
        x:Class="DealingHeaderFooter.MainPage"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:local="using:DealingHeaderFooter"
        xmlns:syncfusion="using:Syncfusion.UI.Xaml.Controls.Input"

            <syncfusion:SfPicker.Footer>

                <Grid>
                    <StackPanel Orientation="Horizontal">
                        <Button Content="Ok" Foreground="Red" Height="50" HorizontalAlignment="Left" Margin="10"/>
                        <Button Content="Cancel" Foreground="Red" Height="50" HorizontalAlignment="Right" Margin="10"/>
                    </StackPanel>
                </Grid>

            </syncfusion:SfPicker.Footer>

{% endhighlight %}

{% highlight c# %}

    using Syncfusion.UI.Xaml.Controls.Input;
    using Windows.UI.Xaml;

    namespace DealingHeaderFooter
 
     {
            this.InitializeComponent();
 
            SfPicker picker = new SfPicker();
 
            picker.ShowFooter = true;
 
            Grid layout = new Grid();
 
            layout.Children.Add(new Button() { HorizontalAlignment = HorizontalAlignment.Right, Content = "ok", Foreground = new SolidColorBrush(Windows.UI.Colors.Red) });
 
            picker.Footer = layout;

     }

{% endhighlight %}

{% endtabs %}

## Perform validation with default validation Button

SfPicker allows performing validation based on OK or Cancel button by hooking `SfPicker.OkButtonClicked` and `SfPicker.CancelButtonClicked`. In this event from the `SelectionChangedEvent` Argument current selected items can be obtained.


{% tabs %}

{% highlight xaml %}
  
       <Page
        x:Class="DealingHeaderFooter.MainPage"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:local="using:DealingHeaderFooter"
        xmlns:syncfusion="using:Syncfusion.UI.Xaml.Controls.Input">
          
        <Grid>
      
            <syncfusion:SfPicker x:Name="picker" CancelButtonClicked="picker_CancelButtonClicked" OkButtonClicked="picker_OkButtonClicked" ShowFooter="True"/>
      
        </Grid>
    
    </Page>      

{% endhighlight %}

{% highlight c# %}
  
    using Syncfusion.UI.Xaml.Controls.Input;
    using Windows.UI.Xaml;

    namespace DealingHeaderFooter
 
     {

      public sealed partial class MainPage : Page
 
       {

        public MainPage()
 
        {

            this.InitializeComponent();
 
            SfPicker picker = new SfPicker();
 
            picker.OkButtonClicked += picker_OkButtonClicked;
 
            picker.CancelButtonClicked += picker_CancelButtonClicked;
 
            this.Content = picker;
      
        }
 
       }
 
      }

{% endhighlight %}

{% endtabs %}
