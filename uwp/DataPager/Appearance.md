---
layout: post
title: Appearance in UWP DataPager control | Syncfusion
description: Learn here all about Appearance support in Syncfusion UWP DataPager (SfDataPager) control and more.
platform: uwp
control: SfDataPager
documentation: ug
---
# Appearance in UWP DataPager (SfDataPager)

## Display Modes

The [SfDataPager](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Controls.DataPager.SfDataPager.html) control allows you to customize the visual parts to be displayed using [DisplayMode](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Controls.DataPager.SfDataPager.html#Syncfusion_UI_Xaml_Controls_DataPager_SfDataPager_DisplayMode) property. The following table shows different `PageDisplayMode` options available.

<table>
<tr>
<th>
Enum Values</th><th>
Description</th></tr>
<tr>
<td>
FirstLastPreviousNextNumeric</td><td>
Displays all the navigation buttons and numeric page buttons.{{'![B:/Support/2015/April/24/Image/DataPager/1.png](Appearance_images/Appearance_img16.jpeg)'| markdownify }}
</td></tr>
<tr>
<td>
FirstLastNumeric</td><td>
Displays the first page, last page navigation button and numeric page buttons.{{'![B:/Support/2015/April/24/Image/DataPager/2.png](Appearance_images/Appearance_img1.jpeg)'| markdownify }}
</td></tr>
<tr>
<td>
PreviousNextNumeric</td><td>
Displays the previous, next page navigation buttons and numeric page buttons.{{'![B:/Support/2015/April/24/Image/DataPager/3.png](Appearance_images/Appearance_img2.jpeg)'| markdownify }}
</td></tr>
<tr>
<td>
FirstLastPreviousNext</td><td>
Displays only the page navigation buttons. Numeric page buttons are not displayed.{{'![B:/Support/2015/April/24/Image/DataPager/4.png](Appearance_images/Appearance_img3.jpeg)'| markdownify }}
</td></tr>
<tr>
<td>
FirstLast</td><td>
Displays only the first and last page navigation buttons.{{'![B:/Support/2015/April/24/Image/DataPager/5.png](Appearance_images/Appearance_img4.jpeg)'| markdownify }}
</td></tr>
<tr>
<td>
PreviousNext</td><td>
Displays only the previous and next page navigation buttons.{{'![B:/Support/2015/April/24/Image/DataPager/6.png](Appearance_images/Appearance_img5.jpeg)'| markdownify }}
</td></tr>
<tr>
<td>
Numeric</td><td>
Displays only the numeric page buttons.{{'![B:/Support/2015/April/24/Image/DataPager/7.png](Appearance_images/Appearance_img6.jpeg)'| markdownify }}
</td></tr>
<tr>
<td>
First</td><td>
Displays only the first page navigation button.{{'![B:/Support/2015/April/24/Image/DataPager/8.png](Appearance_images/Appearance_img7.jpeg)'| markdownify }}
</td></tr>
<tr>
<td>
Last</td><td>
Displays only the last page navigation button.{{'![B:/Support/2015/April/24/Image/DataPager/9.png](Appearance_images/Appearance_img8.jpeg)'| markdownify }}
</td></tr>
<tr>
<td>
Previous</td><td>
Displays only the previous page navigation button.{{'![B:/Support/2015/April/24/Image/DataPager/10.png](Appearance_images/Appearance_img9.jpeg)'| markdownify }}
</td></tr>
<tr>
<td>
Next</td><td>
Displays only the next page navigation button.{{'![B:/Support/2015/April/24/Image/DataPager/11.png](Appearance_images/Appearance_img10.jpeg)'| markdownify }}
</td></tr>
<tr>
<td>
None</td><td>
It does not display anything</td></tr>
</table>



## Numeric Buttons count

SfDataPager allows you to display the number of page buttons to be displayed in view by setting [NumericButtonCount](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Controls.DataPager.SfDataPager.html#Syncfusion_UI_Xaml_Controls_DataPager_SfDataPager_NumericButtonCount) property. 

{% tabs %}
{% highlight xaml %}
<datapager:SfDataPager x:Name="sfDataPager" 
                         PageSize="5" 
                         UseOnDemandPaging="True"
                         NumericButtonCount="10"
                         PageCount="10" /> 
{% endhighlight %}
{% endtabs %}
![Appearance_img11](Appearance_images/Appearance_img11.jpeg)


Now after changing `NumberButtonCount` as 5, only 5-page button will be displayed in view and remaining page buttons can be viewed by clicking the navigation buttons.

{% tabs%}
{% highlight xaml %}
<datapager:SfDataPager x:Name="sfDataPager" 
                         PageSize="5" 
                         UseOnDemandPaging="True"
                         NumericButtonCount="5"
                         PageCount="10" />
{% endhighlight %}
{% endtabs %}

![Appearance_img12](Appearance_images/Appearance_img12.jpeg)



## Orientation

SfDataPager allows you to change the orientation on the control through [Orientation](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Controls.DataPager.SfDataPager.html#Syncfusion_UI_Xaml_Controls_DataPager_SfDataPager_Orientation) property. 

<table>
<tr>
<th>
Enum Value</th><th>
Description</th></tr>
<tr>
<td>
Horizontal</td><td>
This is the default enum value for Orientation. Arranges all the Navigation Buttons and Numeric Buttons Horizontally.{{'![B:/Support/2015/April/24/Image/DataPager/3.png](Appearance_images/Appearance_img18.jpeg)'|markdownify}}
</td></tr>
<tr>
<td>
Vertical</td><td>
Arranges all the Navigation Buttons and Numeric Buttons Vertically.{{'![B:/Support/2015/April/24/Image/DataPager/figure12.png](Appearance_images/Appearance_img17.jpeg)'|markdownify}}
</td></tr>
</table>



## AutoEllipsisMode

The AutoEllipsis button is displayed when the page count is greater than numeric button count. The [SfDataPager](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Controls.DataPager.SfDataPager.html#) control allows you enable this by using [AutoEllipsisMode](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Controls.DataPager.SfDataPager.html#Syncfusion_UI_Xaml_Controls_DataPager_SfDataPager_AutoEllipsisMode) property which is the Enum type.

* [AutoEllipsisMode](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Controls.DataPager.SfDataPager.html#Syncfusion_UI_Xaml_Controls_DataPager_SfDataPager_AutoEllipsisMode) – This Property is used to set the `AutoEllipsisMode`. By default, it is set to None.
* [AutoEllipsisText](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Controls.DataPager.SfDataPager.html#Syncfusion_UI_Xaml_Controls_DataPager_SfDataPager_AutoEllipsisText)– This property is used to change the `AutoEllipsisButton` Text.

The following table explains the different `AutoEllipsisModes`.

<table>
<tr>
<th>
Enum Value</th><th>
Description</th></tr>
<tr>
<td>
After</td><td>
You can display the ellipsis button after numeric buttons.{{'![B:/Support/2015/April/24/Image/DataPager/AutoElipseafter.png](Appearance_images/Appearance_img19.jpeg)'|markdownify}}</td></tr>
<tr>
<td>
Before</td><td>
You can display the ellipsis button before numeric buttons.{{'![B:/Support/2015/April/24/Image/DataPager/before.png](Appearance_images/Appearance_img20.jpeg)'|markdownify}}</td></tr>
<tr>
<td>
Both</td><td>
You can display the ellipsis button before and after the numeric buttons.{{'![B:/Support/2015/April/24/Image/DataPager/both.png](Appearance_images/Appearance_img21.jpeg)'|markdownify}}</td></tr>
<tr>
<td>
None</td><td>
It does not display the AutoEllipsisButton.{{'![B:/Support/2015/April/24/Image/DataPager/none.png](Appearance_images/Appearance_img22.jpeg)'|markdownify}}
</td></tr>
</table>
The following code example explains how to change the `AutoEllipsisText`.

{% tabs %}
{% highlight xaml %}
<datapager:SfDataPager x:Name="sfDataPager" 
                         PageSize="2"
                         AutoEllipsisMode="After"
                         NumericButtonCount="4" PageCount="10"
                         AutoEllipsisText="…etc" 
                         UseOnDemandPaging="True"/>
{% endhighlight %}
{% endtabs %}

The following screenshot displays the output for `AutoEllipsisText` changed as `…etc`.

![Appearance_img13](Appearance_images/Appearance_img13.jpeg)



## AccentBrush

AccentBrush properties are used to decorate the SfDataPager control with a solid color. There are two AccentBrush properties in the `SfDataPager` control:

* [AccentBackground](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Controls.DataPager.SfDataPager.html#Syncfusion_UI_Xaml_Controls_DataPager_SfDataPager_AccentBackground) – Property that is applied to the background color for `NavigationButtons` and current selected numeric page button. By default, it set to DarkGray.
* [AccentForeground](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Controls.DataPager.SfDataPager.html#Syncfusion_UI_Xaml_Controls_DataPager_SfDataPager_AccentForeground) – Property that is applied to the foreground color for the current selected numeric page button. By default, it set to White.
* [NumericButtonStyle](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Controls.DataPager.SfDataPager.html#Syncfusion_UI_Xaml_Controls_DataPager_SfDataPager_NumericButtonStyleProperty) – Property that is applied to the Style of Numeric Button. This is the Style type property. By default, it set to Null.

The following code example explains how to apply the `AccentBackground` and `AccentForeground` properties for the `SfDataPager` control.

{% tabs %}
{% highlight xaml %}
<datapager:SfDataPager x:Name="sfDataPager" 
                         PageCount="2"
                         AccentBackground="#FF8CBF26"
                         AccentForeground="White"
                         UseOnDemandPaging="True" />
{% endhighlight %}
{% endtabs %}

The following screenshot displays the output for `AccentBackground` and `AccentForeGround` applied to the `SfDataPager`.

![Appearance_img14](Appearance_images/Appearance_img14.jpeg)


The following code example explains how to use `NumericButtonStyle` in SfDataPager.

{% tabs %}
{% highlight xaml %}
<Page.Resources>
    <Style TargetType="datapager:NumericButton">
        <Setter Property="BorderBrush" Value="Blue"/>
        <Setter Property="BorderThickness" Value="2"/>
    </Style>
</Page.Resources>
<datapager:SfDataPager x:Name="sfDataPager" 
                         PageCount="2"
                         AccentBackground="DodgerBlue"
                         UseOnDemandPaging="True" />
{% endhighlight %}
{% endtabs %}

The following screenshot displays the output of `NumericButtonStyle`.

![Appearance_img15](Appearance_images/Appearance_img15.jpeg)
