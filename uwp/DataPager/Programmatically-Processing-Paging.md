---
layout: post
title: Programmatically Processing Paging in UWP DataPager control | Syncfusion
description: Learn here all about Programmatically Processing Paging support in Syncfusion UWP DataPager (SfDataPager) control and more.
platform: uwp
control: SfDataPager
documentation: ug
---
# Programmatically Processing Paging in UWP DataPager (SfDataPager)


## Changing PageIndex at runtime
[SfDataPager](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Controls.DataPager.SfDataPager.html#) exposes the [PageIndex](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Controls.DataPager.SfDataPager.html#Syncfusion_UI_Xaml_Controls_DataPager_SfDataPager_PageIndex) property, which denotes the index of currently selected page. You can use this property to set or get the current page of the `SfDataPager`.

<table>
<tr>
<th>
Event</th><th>
Description</th></tr>
<tr>
<td>
{{'[PageIndexChanging](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Controls.DataPager.SfDataPager.html)'| markdownify }}</td><td>
Event triggered before the current page index changed. By using this event, you can cancel the current page changing operation by setting `Cancel` to `true`.</td></tr>
<tr>
<td>
{{'[PageIndexChanged](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Controls.DataPager.SfDataPager.html)'| markdownify }}</td><td>
Event triggered after the current page index changed.</td></tr>
</table>


## Programmatically changing PageCount

[SfDataPager](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Controls.DataPager.SfDataPager.html) allows you to change the current page using [PageCount](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Controls.DataPager.SfDataPager.html#Syncfusion_UI_Xaml_Controls_DataPager_SfDataPager_PageCount) property. you can change the `PageCount` during the run time. 


## Changing PageIndex using method

[SfDataPager](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Controls.DataPager.SfDataPager.html) allows you to change the current page using built-in methods. For example, you can change the `PageIndex` to last page by calling [MoveToLastPage](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Controls.DataPager.SfDataPager.html#Syncfusion_UI_Xaml_Controls_DataPager_SfDataPager_MoveToLastPage)() method. 

`SfDataPager` provides the following methods for changing current page.

<table>
<tr>
<th>
Method</th><th>
Prototype</th><th>
Description</th></tr>
<tr>
<td>
{{'[MoveToFirstPage](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Controls.DataPager.SfDataPager.html#Syncfusion_UI_Xaml_Controls_DataPager_SfDataPager_MoveToFirstPage)'| markdownify }}</td><td>
MoveToFirstPage()</td><td>
This method moves the current page index to the first page and displays the first page data.</td></tr>
<tr>
<td>
{{'[MoveToLastPage](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Controls.DataPager.SfDataPager.html#Syncfusion_UI_Xaml_Controls_DataPager_SfDataPager_MoveToLastPage)'| markdownify }}</td><td>
MoveToLastPage()</td><td>
This method moves the current page index to the last page and displays the last page data.</td></tr>
<tr>
<td>
{{'[MoveToNextPage](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Controls.DataPager.SfDataPager.html#Syncfusion_UI_Xaml_Controls_DataPager_SfDataPager_MoveToNextPage)'| markdownify }}</td><td>
MoveToNextPage()</td><td>
This method moves the current page index to the next page and displays the next page data.</td></tr>
<tr>
<td>
{{'[MoveToPreviousPage](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Controls.DataPager.SfDataPager.html#Syncfusion_UI_Xaml_Controls_DataPager_SfDataPager_MoveToPreviousPage)'| markdownify }}</td><td>
MoveToPreviousPage()</td><td>
This method moves the current page index to the previous page and displays the previous page data.</td></tr>
<tr>
<td>
{{'[MoveToPage](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Controls.DataPager.SfDataPager.html#Syncfusion_UI_Xaml_Controls_DataPager_SfDataPager_MoveToPage_System_Int32_)'| markdownify }}</td><td>
MoveToPage(int pageIndex)</td><td>
This method moves the current page index to the corresponding page index that is passed as an argument.</td></tr>
</table>

## Handling current page changing using event

You can cancel the current page changing operation by handling [PageIndexChanging](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Controls.DataPager.SfDataPager.html) event.

The following example displays the `MessageDialog` when end-user tries to change the page.

{% tabs %}
{% highlight xaml %}
<datapager:SfDataPager x:Name="sfDataPager" 
                         PageSize="5" 
                         NumericButtonCount="5"
                         PageCount="10"
                         PageIndexChanging="sfDataPager_PageIndexChanging"
                         UseOnDemandPaging="True"/>                    
{% endhighlight %}
{% highlight c# %}
this.sfDataPager.PageIndexChanging += SfDataPager_PageIndexChanging;

private async void sfDataPager_PageIndexChanging(object sender, PageIndexChangingEventArgs args)
{
    MessageDialog messageDialog = new MessageDialog("Do you want to change the page?");
    messageDialog.Commands.Clear();
    messageDialog.Commands.Add(new UICommand { Label = "Yes", Id = 0 });
    messageDialog.Commands.Add(new UICommand { Label = "No", Id = 1 });
    var result = await messageDialog.ShowAsync();

    if ((int)result.Id == 1 )
    {
        args.Cancel = true;
    }
}
{% endhighlight %}
{% endtabs %}

![Programmatically-Processing-Paging_img1](Programmatically-Processing-Paging_images/Programmatically-Processing-Paging_img1.jpeg)
