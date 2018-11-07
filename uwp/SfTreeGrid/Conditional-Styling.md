---
layout: post
title: Conditional Styling | TreeGrid | UWP | Syncfusion
description: This section explains about style the TreeGrid cells/rows based on conditions.
platform: uwp
control: SfTreeGrid
documentation: ug
---
# Conditional styling

You can style the treegrid and its inner elements conditionally based on data in three ways,

1. Using Converter
2. Using Data Triggers
3. Using StyleSelector

<table>
<tr>
<td>
{{'**Styling ways**'| markdownify }}
</td>
<td>
{{'**Performance details**'| markdownify }}
</td>
</tr>
<tr>
<td>
Converter
</td>
<td>
Provide good performance when compared other two ways.
</td>
</tr>
<tr>
<td>
Trigger
</td>
<td>
When compared to converter, performance is slow while styling more number of columns or rows.
</td>
</tr>
<tr>
<td>
StyleSelector
</td>
<td>
It affects scrolling performance while styling more number of columns based on number of columns visible.
</td>
</tr>
</table>

# Cells

## Style cells using converter

The record cells ([TreeGridCell](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfGrid.UWP~Syncfusion.UI.Xaml.TreeGrid.TreeGridCell.html)) can be customized conditionally by changing its property value based on cell value or data object using converter.

Here, grid cell background is changed using converter, where converter returns the value based on ID property of underlying record.


<table>
<tr>
<td>
xmlns:utils="using:Syncfusion.UI.Xaml.Utils"
&lt;Page.Resources&gt;
   &lt;local:StyleConverter x:Key="converter"/&gt;
&lt;/Page.Resources&gt;
&lt;syncfusion:TreeGridTextColumn MappingName="Id" TextAlignment="Left" &gt;
         &lt;syncfusion:TreeGridTextColumn.CellStyle&gt;
                &lt;Style TargetType="syncfusion:TreeGridCell"&gt;
                     &lt;Setter Property="utils:SetterValueBindingHelper.PropertyBinding"&gt;
                          &lt;Setter.Value&gt;
                                    &lt;utils:SetterValueBindingHelper Property="Background" Binding="{Binding Id,Converter={StaticResource converter}}"/&gt;
                          &lt;/Setter.Value&gt;
                      &lt;/Setter&gt;
                &lt;/Style&gt;
        &lt;/syncfusion:TreeGridTextColumn.CellStyle&gt;
&lt;/syncfusion:TreeGridTextColumn&gt;
</td>
</tr>
</table>
<table>
<tr>
<td>
internal class StyleConverter : IValueConverter
{
    public object Convert(object value, Type targetType, object parameter, string language)
    {
        int input = (int)value;
        //custom condition is checked based on data.
        if (input < 300)
            return new SolidColorBrush(Colors.LightBlue);
        else if (input > 300 && input < 2000)
            return new SolidColorBrush(Colors.Bisque);
        else
            return DependencyProperty.UnsetValue;
    }
    public object ConvertBack(object value, Type targetType, object parameter, string language)
    {
        throw new NotImplementedException();
    }
}
</td>
</tr>
</table>

![Styling cells using converter in UWP treegrid](Conditional-Styling_images/Conditional-Styling_img1.jpeg)

## Style cells based on record using converter

You can also style the cells based on record instead of passing single property to converter, where converter returns the value based on underlying record. This can be assigned to GridColumn.CellStyle to style the column based on other column properties.

<table>
<tr>
<td>
xmlns:utils="using:Syncfusion.UI.Xaml.Utils"
&lt;Page.Resources&gt;
  &lt;local:StyleConverter x:Key="converter"/&gt;
    &lt;Style TargetType="syncfusion:TreeGridCell"&gt;
        &lt;Setter Property="utils:SetterValueBindingHelper.PropertyBinding"&gt;
            &lt;Setter.Value&gt;
                &lt;utils:SetterValueBindingHelper Property="Background" Binding="{Binding Converter={StaticResource converter}}"/&gt;
            &lt;/Setter.Value&gt;
        &lt;/Setter&gt;
   &lt;/Style&gt;
&lt;/Page.Resources&gt;
</td>
</tr>
</table>
<table>
<tr>
<td>
internal class StyleConverter : IValueConverter
    {
        public object Convert(object value, Type targetType, object parameter, string language)
        {
            var input = value as PersonInfo;
            //custom condition is checked based on data.
            if (input.Id < 300)
                return new SolidColorBrush(Colors.LightBlue);
            else if (input.Id > 300 && input.Id < 2000)
                return new SolidColorBrush(Colors.Bisque);
            else
                return DependencyProperty.UnsetValue;
        }
        public object ConvertBack(object value, Type targetType, object parameter, string language)
        {
            throw new NotImplementedException();
        }
   }
</td>
</tr>
</table>

![Styling cells based on record in UWP treegrid](Conditional-Styling_images/Conditional-Styling_img2.jpeg)

## Style cells using style selector

The record cells ([TreeGridCell](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfGrid.UWP~Syncfusion.UI.Xaml.TreeGrid.TreeGridCell.html)) can be customized conditionally based on data by setting [SfTreeGrid.CellStyleSelector ](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfGrid.UWP~Syncfusion.UI.Xaml.TreeGrid.SfTreeGrid~CellStyleSelectorProperty.html)property and the particular column record cells can be customized by setting [GridColumn.CellStyleSelector ](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfGrid.UWP~Syncfusion.UI.Xaml.TreeGrid.SfTreeGrid~CellStyleSelectorProperty.html)property and you can get the container as TreeGridCell in the StyleSelector.

<table>
<tr>
<td>
&lt;Application.Resources&gt;
       &lt;Style x:Key="redCellStyle" TargetType="syncfusion:TreeGridCell"&gt;
            &lt;Setter Property="Foreground" Value="Red" /&gt;
        &lt;/Style&gt;
        &lt;Style x:Key="blueCellStyle" TargetType="syncfusion:TreeGridCell"&gt;
            &lt;Setter Property="Foreground" Value="DarkBlue" /&gt;
        &lt;/Style&gt;
&lt;/Application.Resources&gt;
</td>
</tr>
</table>
<table>
<tr>
<td>
public class SelectorClass : StyleSelector
{
    protected override Style SelectStyleCore(object item, DependencyObject container)
    {
        var data = item as PersonInfo;
        if (data != null && ((container as TreeGridCell).ColumnBase.TreeGridColumn.MappingName == "Id"))
        {
            //custom condition is checked based on data.
            if (data.Id < 300)
                return App.Current.Resources["redCellStyle"] as Style;
            return App.Current.Resources["blueCellStyle"] as Style;
        }
        return base.SelectStyleCore(item, container);
    }
}
</td>
</tr>
</table>

![Styling cells using style selector in UWP treegrid](Conditional-Styling_images/Conditional-Styling_img3.jpeg)

## Add image to cell

You can add image to cell by using TreeGridTemplateColumn,

<table>
<tr>
<td>
&lt;syncfusion:TreeGridTemplateColumn HeaderText="Country" MappingName="ImageLink"&gt;
       &lt;syncfusion:TreeGridTemplateColumn.CellTemplate&gt;
            &lt;DataTemplate&gt;
                   &lt;Grid&gt;
                      <Image Width="30"
                             Height="20"
                             Source="{Binding ImageLink,
                                                        Converter={StaticResource converter}}" />
                   &lt;/Grid&gt;
           &lt;/DataTemplate&gt;
     &lt;/syncfusion:TreeGridTemplateColumn.CellTemplate&gt;
 &lt;/syncfusion:TreeGridTemplateColumn&gt;
</td>
</tr>
</table>
<table>
<tr>
<td>
public object Convert(object value, Type targetType, object parameter, string language)
{
    string imageName = value.ToString();
    if (imageName=="US.jpg")
    {
        Uri uri = new Uri("ms-appx:///Images/US.jpg");
        BitmapImage image = new BitmapImage(uri);
        return image;
    }
    else if(imageName=="UK.jpg")
    {
        Uri uri1 = new Uri("ms-appx:///Images/UK.jpg");
        BitmapImage image = new BitmapImage(uri1);
        return image;
    }
    else
    {
        Uri uri1 = new Uri("ms-appx:///Images/Japan.jpg");
        BitmapImage image = new BitmapImage(uri1);
        return image;
    }
}
public object ConvertBack(object value, Type targetType, object parameter, string language)
{
    throw new NotImplementedException();
}
</td>
</tr>
</table>

![Adding images in a cell in UWP treegrid](Conditional-Styling_images/Conditional-Styling_img4.jpeg)

You can download the sample [here](https://github.com/SyncfusionExamples/how-to-load-images-in-a-cell-in-wpf-and-uwp-treegrid/tree/master/UWP).

# Rows

## Style rows using converter

The record rows ([TreeGridRowControl ](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfGrid.UWP~Syncfusion.UI.Xaml.TreeGrid.TreeGridRowControl.html)) can be customized conditionally by changing its property value based on ‘cell value’ or ‘data object’ by using converter, where converter returns the value based on underlying record.

<table>
<tr>
<td>
&lt;Page.Resources&gt;
        &lt;local:StyleConverter x:Key="converter"/&gt;

        &lt;Style TargetType="syncfusion:TreeGridRowControl"&gt;
            &lt;Setter Property="utils:SetterValueBindingHelper.PropertyBinding"&gt;
                &lt;Setter.Value&gt;
                    &lt;utils:SetterValueBindingHelper Property="Background" Binding="{Binding Converter={StaticResource converter}}"/&gt;
                &lt;/Setter.Value&gt;
            &lt;/Setter&gt;
        &lt;/Style&gt;
&lt;/Page.Resources&gt;
</td>
</tr>
</table>
<table>
<tr>
<td>
internal class StyleConverter : IValueConverter
{
    public object Convert(object value, Type targetType, object parameter, string language)
    {
        var input = value as PersonInfo;
        //custom condition is checked based on data.
        if (input.Id < 300)
            return new SolidColorBrush(Colors.LightBlue);
        else if (input.Id > 300 && input.Id < 2000)
            return new SolidColorBrush(Colors.Bisque);
        else
            return DependencyProperty.UnsetValue;
    }
    public object ConvertBack(object value, Type targetType, object parameter, string language)
    {
        throw new NotImplementedException();
    }
}
</td>
</tr>
</table>

![Styling rows using converter in UWP treegrid](Conditional-Styling_images/Conditional-Styling_img5.jpeg)

## Style rows using style selector

The record rows ([TreeGridRowControl](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfGrid.UWP~Syncfusion.UI.Xaml.TreeGrid.TreeGridRowControl.html)) can be customized conditionally based on data by setting [SfTreeGrid.RowStyleSelector ](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfGrid.UWP~Syncfusion.UI.Xaml.TreeGrid.SfTreeGrid~RowStyleSelectorProperty.html)property and you can get the container as TreeGridRowControl in StyleSelector.

<table>
<tr>
<td>
&lt;Application.Resources&gt;
        &lt;local:SelectorClass x:Key="rowStyleSelector" /&gt;
        &lt;Style x:Key="rowStyle1" TargetType="syncfusion:TreeGridRowControl"&gt;
            &lt;Setter Property="Background" Value="Red" /&gt;
        &lt;/Style&gt;
        &lt;Style x:Key="rowStyle2" TargetType="syncfusion:TreeGridRowControl"&gt;
            &lt;Setter Property="Background" Value="DarkBlue" /&gt;
        &lt;/Style&gt;
&lt;/Application.Resources&gt;
</td>
</tr>
</table>
<table>
<tr>
<td>
public class SelectorClass : StyleSelector
{
    protected override Style SelectStyleCore(object item, DependencyObject container)
    {
        var row = (item as TreeDataRowBase).RowData;
        var data = row as PersonInfo;
        if (data.Id < 300)
            return App.Current.Resources["rowStyle1"] as Style;
        return App.Current.Resources["rowStyle2"] as Style;
        return base.SelectStyleCore(item, container);
    }
}
</td>
</tr>
</table>

![Styling rows using style selector in UWP treegrid](Conditional-Styling_images/Conditional-Styling_img6.jpeg)

# Row Header

The appearance of row header ([TreeGridRowHeaderCell](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfGrid.UWP~Syncfusion.UI.Xaml.TreeGrid.TreeGridHeaderCell.html)) can be customized conditionally by changing its property value based on ‘cell value’ or ‘data object’ by using converter,where converter returns the value based on Underlying record.

<table>
<tr>
<td>
&lt;syncfusion:ChromelessWindow.Resources&gt;
        &lt;local:StyleConverter x:Key="converter"/&gt;
        &lt;Style TargetType="syncfusion:TreeGridRowHeaderCell"&gt;
            &lt;Setter Property="Background" Value="{Binding Converter={StaticResource converter}}" /&gt;
        &lt;/Style&gt;
&lt;/syncfusion:ChromelessWindow.Resources&gt;
</td>
</tr>
</table>
<table>
<tr>
<td>
internal class StyleConverter : IValueConverter
{
    public object Convert(object value, Type targetType, object parameter, string language)
    {
        var data = value as PersonInfo;
        //custom condition is checked.
        if (data.Id < 300)
            return new SolidColorBrush(Colors.Green);
        else
            return new SolidColorBrush(Colors.Red);
    }
    public object ConvertBack(object value, Type targetType, object parameter, string language)
    {
        throw new NotImplementedException();
    }
}
</td>
</tr>
</table>

![Styling row header in UWP treegrid](Conditional-Styling_images/Conditional-Styling_img7.jpeg)

