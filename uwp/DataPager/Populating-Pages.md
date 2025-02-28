---
layout: post
title: Populating Pages in UWP DataPager control | Syncfusion®
description: Learn here all about Populating Pages support in Syncfusion® UWP DataPager (SfDataPager) control and more.
platform: uwp
control: SfDataPager
documentation: ug
---

# Populating Pages in UWP DataPager (SfDataPager)

## Binding with data

You can use [Source](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Controls.DataPager.SfDataPager.html#Syncfusion_UI_Xaml_Controls_DataPager_SfDataPager_Source) property to bind collection of data with [SfDataPager](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Controls.DataPager.SfDataPager.html#). Based on number of items in collection and [PageSize](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Controls.DataPager.SfDataPager.html#Syncfusion_UI_Xaml_Controls_DataPager_SfDataPager_PageSize), the [PageCount](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Controls.DataPager.SfDataPager.html#Syncfusion_UI_Xaml_Controls_DataPager_SfDataPager_PageCount) will be calculated. 

Below code snippet shows, how to bind `SfDataPager` with data. 

{% tabs %}
{% highlight xaml %}
<Page>
    <Page.DataContext>
        <local:ViewModel />
    </Page.DataContext>
    <Grid>
        <Grid.RowDefinitions>
            <RowDefinition Height="300"/>
            <RowDefinition Height="*"/>
        </Grid.RowDefinitions>
        <syncfusion:SfDataGrid x:Name="sfGrid"
                                Grid.Row="0" 
                                ItemsSource="{Binding
                                ElementName=sfDataPager,Path=PagedSource}"/>
                                <datapager:SfDataPager x:Name="sfDataPager" 
                                                        Grid.Row="1" 
                                                        PageSize="5" 
                                                        NumericButtonCount="5"
                                                        Source="{Binding Orders}" />    
    </Grid>
</Page>
{% endhighlight %}
{% endtabs %}

Based on number of items in the collection and `PageSize` and the `PageCount` is calculated for `SfDataPager`.

![Populating-Pages_img1](Populating-Pages_images/Populating-Pages_img1.jpeg)

## Unbound Mode

You can define the [PageCount](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Controls.DataPager.SfDataPager.html#Syncfusion_UI_Xaml_Controls_DataPager_SfDataPager_PageCount) of `SfDataPager` by setting [UseOnDemandPaging](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Controls.DataPager.SfDataPager.html#Syncfusion_UI_Xaml_Controls_DataPager_SfDataPager_UseOnDemandPagingProperty) to `true` and `PageCount` property.

{% tabs %}
{% highlight xaml %}
<datapager:SfDataPager x:Name="sfDataPager" 
                         PageCount="2"
                         UseOnDemandPaging="True"/>
{% endhighlight %}
{% endtabs %}

![Populating-Pages_img2](Populating-Pages_images/Populating-Pages_img2.jpeg)
