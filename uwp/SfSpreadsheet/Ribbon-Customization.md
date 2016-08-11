---
layout: post
title: Ribbon Customization in SfSpreadsheet
description: How to customize the SfSpreadsheetRibbon
platform: UWP
control: SfSpreadsheet
documentation: ug
---

# Ribbon Customization

Ribbon Customization can be done in two ways,

## Using Control Template:

User can customize the ribbon items by overriding the template of `SfSpreadsheetRibbon`.

## Using Event:

By invoking SfSpreadsheetRibbon Loaded Event, User can add/delete the ribbon menu items.

### Adding a Ribbon Item

To create a custom Ribbon tab with user defined menu options in SfSpreadsheet,

{% tabs %}
{% highlight xaml %}

    <syncfusion:SfSpreadsheetRibbon x:Name="ribbon" DataContext="{Binding ElementName=spreadsheet}" />

{% endhighlight %}
{% endtabs %}

{% tabs %}
{% highlight c# %}

SfRibbonBar CustomRibbonBar;
ribbon.Loaded += ribbon_Loaded;

void ribbon_Loaded(object sender, RoutedEventArgs e)
{
    var sfribbon = GridUtil.GetVisualChild<SfRibbon>(sender as FrameworkElement);         

    if (sfribbon != null)
    {
      SfRibbonTab rb = new SfRibbonTab();
      rb.Caption = "OTHER";
      SfRibbonButton Button1 = new SfRibbonButton();
      Button1.Label = "PRINT";              
      Button1.SizeMode = SizeMode.Large;                
      Button1.Click += Button1_Click;

      SfRibbonButton Button2 = new SfRibbonButton();
      Button2.Label = "PRINT PREVIEW";
      Button2.SizeMode = SizeMode.Large; 
      Button2.Click += Button2_Click;

      CustomRibbonBar = new SfRibbonBar();
      CustomRibbonBar.Header = "Printing Options";
      CustomRibbonBar.Items.Add(Button1);
      CustomRibbonBar.Items.Add(Button2);               
      rb.Items.Add(CustomRibbonBar);
      sfribbon.Items.Add(rb);
    }

}

{% endhighlight %}
{% endtabs %}

### Removing a Ribbon Item

To remove the ribbon menu items in the SfSpreadsheetRibbon,

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
    var sfribbon = GridUtil.GetVisualChild<SfRibbon>(sender as FrameworkElement);

    if (sfribbon != null)
    {
      var item = sfribbon.Items[2];
      sfribbon.Items.Remove(item);
    }
}

{% endhighlight %}
{% endtabs %}