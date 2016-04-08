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

__Using__ __Control__ __Template__:

You can customize the Ribbon items by overriding the template of `SfSpreadsheetRibbon`. 

__Using__ __Event__:

You can create a custom Ribbon tab with user defined meu options in SfSpreadsheet. To achieve this customization, invoke the SfSpreadsheetRibbon Loaded Event and create a custom tab with menu options. Add this custom tab to SfSpreadsheet Ribbon.

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
