---
layout: post
title: Ribbon Customization in UWP Spreadsheet control | Syncfusion®
description: Learn here all about Ribbon Customization support in Syncfusion® UWP Spreadsheet (SfSpreadsheet) control and more.
platform: UWP
control: SfSpreadsheet
documentation: ug
---

# Ribbon Customization in UWP Spreadsheet (SfSpreadsheet)

Ribbon Customization can be done in two ways,

## Using Control Template:

User can customize the ribbon items by overriding the template of `SfSpreadsheetRibbon`.

## Using Event

By invoking SfSpreadsheetRibbon Loaded Event, User can add/delete the ribbon menu items.

### Adding a RibbonTab

To create a custom Ribbon tab with user defined menu options in `SfSpreadsheetRibbon`,

{% tabs %}
{% highlight xaml %}

    <syncfusion:SfSpreadsheetRibbon x:Name="ribbon" DataContext="{Binding ElementName=spreadsheet}" />

{% endhighlight %}
{% endtabs %}

{% tabs %}
{% highlight c# %}

ribbon.Loaded += ribbon_Loaded;

void ribbon_Loaded(object sender, RoutedEventArgs e)
{
    var ribbon1 = GridUtil.GetVisualChild<SfRibbon>(sender as FrameworkElement);         

    if (ribbon1 != null)
    {
        SfRibbonTab ribbonTab = new SfRibbonTab();
        ribbonTab.Caption = "OTHER";
        SfRibbonButton Button1 = new SfRibbonButton();
        Button1.Label = "PRINT";              
        Button1.SizeMode = SizeMode.Large;                
        Button1.Click += Button1_Click;

        SfRibbonButton Button2 = new SfRibbonButton();
        Button2.Label = "PRINT PREVIEW";
        Button2.SizeMode = SizeMode.Large; 
        Button2.Click += Button2_Click;

        var customRibbonBar = new SfRibbonBar();
        customRibbonBar.Header = "Printing Options";
        customRibbonBar.Items.Add(Button1);
        customRibbonBar.Items.Add(Button2);               
        ribbonTab.Items.Add(customRibbonBar);
       ribbon1.Items.Add(ribbonTab);
    }

}

{% endhighlight %}
{% endtabs %}

### Adding a Ribbon Items in Existing Tab

To add a ribbon items in already existing tab,

{% tabs %}
{% highlight xaml %}

    <syncfusion:SfSpreadsheetRibbon x:Name="ribbon" DataContext="{Binding ElementName=spreadsheet}" />

{% endhighlight %}
{% endtabs %}

{% tabs %}
{% highlight c# %}

ribbon.Loaded += ribbon_Loaded;
    
void ribbon_Loaded(object sender, RoutedEventArgs e)
{
    var ribbon1 = GridUtil.GetVisualChild<SfRibbon>(sender as FrameworkElement);
    
    // To add the ribbon button in View tab,
    
    if (ribbon1 != null)
    {
        var ribbonTab = ribbon1.Items[2] as RibbonTab;
        RibbonButton Button1 = new RibbonButton();
        Button1.Label = "PRINT";
        Button1.SmallIcon = new BitmapImage(new Uri("/../Icon/Icons_Print.png", UriKind.Relative));
        Button1.Click += Button1_Click;
        ribbonTab.Items.Add(Button1);
    }
}

{% endhighlight %}
{% endtabs %}

### Removing a RibbonTab

To remove the ribbon tab in the SfSpreadsheetRibbon,

{% tabs %}
{% highlight xaml %}

    <syncfusion:SfSpreadsheetRibbon x:Name="ribbon" DataContext="{Binding ElementName=spreadsheet}" />

{% endhighlight %}
{% endtabs %}

{% tabs %}
{% highlight c# %}

ribbon.Loaded += ribbon_Loaded;
    
void ribbon_Loaded(object sender, RoutedEventArgs e)
{
    var ribbon1 = GridUtil.GetVisualChild<SfRibbon>(sender as FrameworkElement);
    
    //To remove the Data tab from the ribbon,

    if (ribbon1 != null)
    {
        var item = ribbon1.Items[1];
        ribbon1.Items.Remove(item);
    }
}

{% endhighlight %}
{% endtabs %}


### Removing a Ribbon Items in a RibbonTab

To remove the ribbon menu items in the ribbon tab of SfSpreadsheetRibbon,

{% tabs %}
{% highlight xaml %}

    <syncfusion:SfSpreadsheetRibbon x:Name="ribbon" DataContext="{Binding ElementName=spreadsheet}" />

{% endhighlight %}
{% endtabs %}

{% tabs %}
{% highlight c# %}

ribbon.Loaded += ribbon_Loaded;
    
void ribbon_Loaded(object sender, RoutedEventArgs e)
{
    var ribbon1 = GridUtil.GetVisualChild<SfRibbon>(sender as FrameworkElement);
    
    // To remove the Freeze panes menu group in View tab,
    
    if (ribbon1 != null)
    {
        var ribbonTab = ribbon1.Items[2] as RibbonTab;
        ribbonTab.Items.Remove(ribbonTab.Items[1]);
    }
}

{% endhighlight %}
{% endtabs %}
