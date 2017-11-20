---
layout: post
title: Define and add the frequently used Nodes/Connectors to the Stencil.
description: How to add Symbol to the Stencil and drag and drop them over the drawing area?
platform: uwp
control: SfDiagram
documentation: ug
---

# Stencil

Stencil has a collection of Symbols. Stencil is used to clone the desired symbol by dragging it from the Stencil and dropping it into the SfDiagram. Each symbol can be grouped together by using the SymbolGroupProvider and filters by using the SymbolFilterProvider through delegates.

{% highlight xaml %}

xmlns:stencil="using:Syncfusion.UI.Xaml.Diagram.Stencil"

{% endhighlight %}

![](Stencil_images/Stencil_img1.jpeg)

Key Terms Table

| Key Terms | Description |
|---|---|
| Symbol | To visualize the items in Stencil. |

Properties Table

| Properties | Description |
|---|---|
| SymbolGroups | Collection of SymbolGroupProvider To Group the Symbols based on the MappingName Property. |
| SymbolFilters | Collection of SymbolFilterProvider To filter/Hide the Symbols based on MappingName Property. |
| SymbolSource | ItemSource for Stencil to populate the SymbolGroups with symbol. | 

## Symbol

Symbol is used to implement the ISymbol interface. The ISymbol interface consists of two properties to visualize symbols in Stencil.

### Adding style to symbol and symbol group

The following example illustrates how to add the Symbol and symbol groups style
 
{% highlight xaml %}
<!--Style for Symbol-->
<Style TargetType="stencil:Symbol">
    <Setter Property="Width" Value="100" />
    <Setter Property="Height" Value="100" />
    <Setter Property="Padding" Value="8" />
    <Setter Property="BorderThickness" Value="1" />
    <Setter Property="Foreground" Value="Black"/>
    <Setter Property="Background" Value="Transparent" />
    <Setter Property="BorderBrush" Value="Transparent" />
    <Setter Property="Margin" Value="3"/>
</Style>

<!--Style for Symbol Group-->
<Style TargetType="stencil:SymbolGroup">
    <Setter Property="FontFamily" Value="Regular"/>
    <Setter Property="Background" Value="#ffffff"/>
    <Setter Property="Foreground" Value="#222222"/>
    <Setter Property="FontSize" Value="14"/>
    <Setter Property="HeaderTemplate">
        <Setter.Value>
            <DataTemplate>
                <stencil:Header>
                    <stencil:Header.Template>
                        <ControlTemplate TargetType="stencil:Header">
                            <Grid>
                                <Border x:Name="header" Background="#f5f5f5" BorderBrush="#dfdfdf" 
                                                BorderThickness="1">
                                    <ContentPresenter Margin="10" Content="{Binding}"/>
                                </Border>
                            </Grid>
                        </ControlTemplate>
                    </stencil:Header.Template>
                </stencil:Header>
            </DataTemplate>
        </Setter.Value>
    </Setter>
</Style>
 
 {% endhighlight %}
 
#### Create the Node into a collection
 
 {% highlight xaml %}

<!--Style for Node-->
<Style x:Key="shapeStyle" TargetType="Path">
    <Setter Property="Fill" Value="LightGray"/>
    <Setter Property="Stroke" Value="#727272"/>
    <Setter Property="StrokeThickness" Value="2"/>
    <Setter Property="Stretch" Value="Fill"/>
</Style>
 {% endhighlight %}

 {% highlight xaml %}

<!--Initializes a Node-->
<syncfusion:NodeViewModel UnitHeight="60" UnitWidth="60" OffsetX="30" OffsetY="30" Shape="{StaticResource Rectangle}"
                                              ShapeStyle="{StaticResource shapeStyle}"
                                              Key="Nodes">
</syncfusion:NodeViewModel>
 
 {% endhighlight %}

#### Add the object into the Collection.
 
 {% highlight C# %}
 
 // SymbolSource to Stencil
public class SymbolCollection : ObservableCollection<object>
{
 
}

{% endhighlight %}

{% highlight xaml %}

<local:SymbolCollection x:Key="collection">
    <!--Add a Node-->
    <syncfusion:NodeViewModel UnitHeight="60" UnitWidth="60" OffsetX="30" OffsetY="30" Shape="{StaticResource Rectangle}"
                                              ShapeStyle="{StaticResource shapeStyle}"
                                              Key="Nodes">
    </syncfusion:NodeViewModel>
</local:SymbolCollection>
 
 {% endhighlight %}
 
![](Stencil_images/Stencil_img5.jpeg)
 
 This Collection will be the SymbolSource to the Stencil. Based on the SymbolSource, the Stencil will populate the Symbols.

### Add Node and Connector to Stencil
 
#### Create a Node and Connector to SymbolCollection.
 
 {% highlight xaml %}
 
 <!--Collection of Symbols-->
<local:SymbolCollection x:Name="collection">
    <!--Initializes Nodes-->
    <syncfusion:NodeViewModel UnitHeight="60" UnitWidth="60" OffsetX="30" OffsetY="30" Shape="{StaticResource Rectangle}"
                                              ShapeStyle="{StaticResource shapeStyle}"
                                              Key="Nodes">
    </syncfusion:NodeViewModel>
    <syncfusion:NodeViewModel UnitHeight="60" UnitWidth="60" OffsetX="30" OffsetY="30"  Shape="{StaticResource Ellipse}"
                                              ShapeStyle="{StaticResource shapeStyle}"
                                              Key="Nodes">
    </syncfusion:NodeViewModel>
    <!--Add a Connector-->
    <syncfusion:ConnectorViewModel  SourcePoint="0,0" TargetPoint="60,60" Key="Connectors"/>
</local:SymbolCollection>
 
 {% endhighlight %}

![](Stencil_images/Stencil_img6.jpeg)

## SymbolGroups

The SymbolGroupProvider groups the symbols into SymbolGroup based on the MappingName property.

| Name | Description |
|---|---|
| MappingName | Used to group the symbols by mapping this property to the custom property of Symbols. |

The following code example illustrates how to create a SymbolGroup.

{% highlight xaml %}

<!--Adding symbol-->
<stencil:Stencil x:Name="stencil" SymbolSource="{StaticResource collection}" Grid.Column="0" Grid.Row="1" 
                                 ExpandMode="All" BorderBrush="#dfdfdf"
                             BorderThickness="0,0,1,0">
    <!--SymbolGroup-->
    <stencil:Stencil.SymbolGroups>
        <stencil:SymbolGroups>
            <stencil:SymbolGroupProvider MappingName="Key"/>
        </stencil:SymbolGroups>
   </stencil:Stencil.SymbolGroups>
</stencil:Stencil>

{% endhighlight %}

![](Stencil_images/Stencil_img3.jpeg)

### Expand or Collapse SymbolGroup

Expand and Collapse can be performed on SymbolGroup (updating the Visibility of the Symbols) based on the ExpandMode property. It includes the following options. The default option is One.

| Expand Mode | Description | Images |
|---|---|---|
| One | Always one SymbolGroup is in expanded state. | ![](Stencil_images/Stencil_img4.jpeg) |
| OneOrMore | At least one SymbolGroup is in expanded state. | ![](Stencil_images/Stencil_img5.jpeg) | ![](Stencil_images/Stencil_img6.jpeg) |
| ZeroOrOne | Not more than a single SymbolGroup is in expanded state. All ‘SymbolGroup’ can be in collapsed state. | ![](Stencil_images/Stencil_img7.jpeg) | ![](Stencil_images/Stencil_img8.jpeg) |
| ZeroOrMore | Any number of SymbolGroup can be in the expanded state. All ‘SymbolGroup’ can be in collapsed state. | ![](Stencil_images/Stencil_img9.jpeg) | ![](Stencil_images/Stencil_img10.jpeg) |
| All | All the SymbolGroup is in expanded state. | ![](Stencil_images/Stencil_img11.jpeg) |

## SymbolFilters

`SymbolFilterProvider` is used to filter or hide the symbols by using delegates. SymbolFilters are the collection of SymbolFilterProvider.

The following code example shows how to create and add the SymbolFilter. Based on the return Boolean value of the SymbolFilter delegate, the corresponding item is removed from Stencil. When a SymbolGroup does not have any Symbols, the corresponding SymbolGroup is also removed.

{% highlight C# %}

stencil.SelectedFilter = new SymbolFilterProvider() { SymbolFilter = SymbolFilter };        
 
{% endhighlight %}
 
{% highlight C# %}

//Filter event
private bool SymbolFilter(SymbolFilterProvider sender, object symbol)
{
   return true;
}

{% endhighlight %}

![](Stencil_images/Stencil_img12.jpeg)

### SelectedFilter

There can be multiple SymbolFilters, but only one filter can be selected at a time. These SymbolFilters are visually represented in a combo box. When the selected item is changed in the combo box, SelectedFilter is updated accordingly.

![](Stencil_images/Stencil_img13.jpeg)

## Preview for Drag and Drop

SfDiagram provides preview support for Stencil. When you drag an item from Stencil to Diagram, a preview of the dragged item will be displayed. You can enable or disable the preview support. You can also customize the preview.

#### Use Case Scenario

This feature displays a preview of the item you drag from Stencil, enabling you to identify the item you are dragging from the Stencil to the SfDiagram control. It also it gives a preview of the size and appearance of the item before it is dropped.

#### Enabling preview

To enable preview for the dragged item from Stencil, set the Constraints property of Stencil to ShowPreview. To disable preview, remove ShowPreview from Constraints property. By default, preview for drag and drop is enabled.

The following code example illustrates how to enable preview support.

{% highlight C# %}

//Enables the drag and drop preview.
stencil.Constraints = stencil.Constraints | StencilConstraints.ShowPreview;

//Disables the drag and drop preview.
stencil.Constraints = stencil.Constraints & ~StencilConstraints.ShowPreview;

{% endhighlight %}

Here, Stencil is an instance of Stencil.

#### Preview of the dragging Symbol

![](Stencil_images/Stencil_img14.jpeg)

#### Dragged Symbol

![](Stencil_images/Stencil_img15.jpeg)

#### Customization of Preview for Drag and Drop

You can customize the preview content by overriding the PrepareDragDropPreview method of the Stencil feature. The following code example illustrates how to customize preview content.

{% highlight C# %}

public class CustomStencil : Stencil
{
	//Virtual method to customize the preview of dragging the symbol from Stencil.
    protected override void PrepareDragDropPreview()
    {
		this.SymbolPreview = new ContentPresenter()
        {
        	Content = new Rectangle()
            {
            	Width = 50,
				Height = 50,
				Fill = new SolidColorBrush(Colors.SteelBlue)
			}
		};
	}
}

{% endhighlight %}

![](Stencil_images/Stencil_img16.jpeg)