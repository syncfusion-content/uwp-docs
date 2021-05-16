---
layout: post
title: Cards in UWP Kanban Board control | Syncfusion
description: Learn here all about Cards support in Syncfusion UWP Kanban Board (SfKanban) control and more.
platform: uwp
control: SfKanban
documentation: ug
---

# Cards in UWP Kanban Board (SfKanban)

The default elements of a card can be customized using the below properties of [`KanbanModel`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Kanban.KanbanModel.html).

* [`Title`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Kanban.KanbanModel.html#Syncfusion_UI_Xaml_Kanban_KanbanModel_Title)         - Used to set the title of a card.
* [`ImageURL`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Kanban.KanbanModel.html#Syncfusion_UI_Xaml_Kanban_KanbanModel_ImageURL)      - Used to set the image URL of a card. The image will be displayed at right side in default card template.
* [`Category`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Kanban.KanbanModel.html#Syncfusion_UI_Xaml_Kanban_KanbanModel_Category)      - Used to set the category of a card. Based on the category the cards will be added to the respective columns. 
* [`Description`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Kanban.KanbanModel.html#Syncfusion_UI_Xaml_Kanban_KanbanModel_Description)   - Used to set the description text of a card.
* [`ColorKey`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Kanban.KanbanModel.html#Syncfusion_UI_Xaml_Kanban_KanbanModel_ColorKey)      - Used to specify the indicator [`ColorKey`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Kanban.IKanbanModel.html#Syncfusion_UI_Xaml_Kanban_IKanbanModel_ColorKey). The [`Color`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Kanban.ColorMapping.html#Syncfusion_UI_Xaml_Kanban_ColorMapping_Color) value of the corresponding [`Key`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Kanban.ColorMapping.html#Syncfusion_UI_Xaml_Kanban_ColorMapping_Key) should be added in [`IndicatorColorPalette`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Kanban.SfKanban.html#Syncfusion_UI_Xaml_Kanban_SfKanban_IndicatorColorPalette) collection of [`SfKanban`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Kanban.SfKanban.html).
* [`Tags`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Kanban.KanbanModel.html#Syncfusion_UI_Xaml_Kanban_KanbanModel_Tags)     - Used to specify the tags of a card. The tags will be displayed at bottom in default card template.
* [`ID`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Kanban.KanbanModel.html#Syncfusion_UI_Xaml_Kanban_KanbanModel_ID)     - Used to set the ID of a card.

{% highlight C# %}

new KanbanModel()
{

    Title = "Universal App",

    ID = "27654",

    Description = "Incorporate feedback into functional specifications",

    Category = "Open",

    ColorKey = "Low",

    Tags = new string[] { "Deployment" },

    ImageURL = new Uri("ms-appx:///images/icon.jpg")
};


{% endhighlight %}

Following code snippet is used to define the colors for each key.

{% tabs %}

{% highlight xaml %}

<kanban:SfKanban.IndicatorColorPalette>

    <kanban:ColorMapping Key="Low" Color="Blue"/>

    <kanban:ColorMapping Key="Normal" Color="Green" />

    <kanban:ColorMapping Key="High" Color="Red" />

</kanban:SfKanban.IndicatorColorPalette>

{% endhighlight %}

{% highlight C# %}

IndicatorColorPalette indicatorColorPalette = new IndicatorColorPalette();

indicatorColorPalette.Add(new ColorMapping() { Key = "Low", Color = Colors.Blue });

indicatorColorPalette.Add(new ColorMapping() { Key = "High", Color = Colors.Red });

indicatorColorPalette.Add(new ColorMapping() { Key = "Normal", Color = Colors.Green });

sfKanban.IndicatorColorPalette = indicatorColorPalette;

{% endhighlight %}

{% endtabs %}

![Card customization in UWP SfKanban](SfKanban_images/CardCustomization.png)

## Customizing kanban cards

The [`CardStyle`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Kanban.SfKanban.html#Syncfusion_UI_Xaml_Kanban_SfKanban_CardStyle) property customizes the kanban cards. The following properties of [`CardStyle`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Kanban.SfKanban.html#Syncfusion_UI_Xaml_Kanban_SfKanban_CardStyle) are used to customize its appearance:

* [`Background`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Kanban.KanbanCardStyle.html#Syncfusion_UI_Xaml_Kanban_KanbanCardStyle_Background) - Changes the background color of a card.
* [`BorderBrush`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Kanban.KanbanCardStyle.html#Syncfusion_UI_Xaml_Kanban_KanbanCardStyle_BorderBrush) - Changes the border brush of a card.
* [`BorderThickness`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Kanban.KanbanCardStyle.html#Syncfusion_UI_Xaml_Kanban_KanbanCardStyle_BorderThickness) - Changes the border thickness of a card.
* [`CornerRadius`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Kanban.KanbanCardStyle.html#Syncfusion_UI_Xaml_Kanban_KanbanCardStyle_CornerRadius) - Adds rounded corners to a card.
* [`IconVisibility`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Kanban.KanbanCardStyle.html#Syncfusion_UI_Xaml_Kanban_KanbanCardStyle_IconVisibility) - Changes the icon visibility of a card.
* [`IndicatorVisibility`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Kanban.KanbanCardStyle.html#Syncfusion_UI_Xaml_Kanban_KanbanCardStyle_IndicatorVisibility) - Changes the indicator visibility of a card.
* [`TagVisibility`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Kanban.KanbanCardStyle.html#Syncfusion_UI_Xaml_Kanban_KanbanCardStyle_TagVisibility) -  Changes the tag panel visibility of a card.
* [`TitleColor`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Kanban.KanbanCardStyle.html#Syncfusion_UI_Xaml_Kanban_KanbanCardStyle_TitleColor) - Changes the header color of a kanban card item.
* [`TitleFontSize`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Kanban.KanbanCardStyle.html#Syncfusion_UI_Xaml_Kanban_KanbanCardStyle_TitleFontSize) - Changes the font size of a card title.
* [`TitleHorizontalAlignment`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Kanban.KanbanCardStyle.html#Syncfusion_UI_Xaml_Kanban_KanbanCardStyle_TitleHorizontalAlignment) - Changes the horizontal alignment of a card title.
* [`FontSize`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Kanban.KanbanCardStyle.html#Syncfusion_UI_Xaml_Kanban_KanbanCardStyle_FontSize) - Changes the font size of a card description.
* [`Foreground`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Kanban.KanbanCardStyle.html#Syncfusion_UI_Xaml_Kanban_KanbanCardStyle_Foreground) - Changes the foreground color of a card description.
* [`TagBackground`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Kanban.KanbanCardStyle.html#Syncfusion_UI_Xaml_Kanban_KanbanCardStyle_TagBackground) -  Changes the tag's background color.
* [`TagForeground`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Kanban.KanbanCardStyle.html#Syncfusion_UI_Xaml_Kanban_KanbanCardStyle_TagForeground) - Changes the tag's foreground color.

## Template

You can replace the entire card template with your own design using [`SfKanban.CardTemplate`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Kanban.SfKanban.html#Syncfusion_UI_Xaml_Kanban_SfKanban_CardTemplate) property. The following code snippet and screenshot illustrates this.

{% highlight xaml %}

<kanban:SfKanban.CardTemplate>
    
    <DataTemplate>
        
        <StackPanel Margin="0,10,0,10" Orientation="Vertical"
                    Background="Gray" Padding="10,10,10,10">

            <StackPanel Orientation="Horizontal">

                <TextBlock Text="{Binding Path=Title}" Foreground="Silver"/>

            </StackPanel>

            <StackPanel  Orientation="Horizontal">

                <TextBlock Text="{Binding Description}" Width="150"
                       FontSize="14" Foreground="Silver" TextWrapping="WrapWholeWords"/>
                
                <Image Source="{Binding ImageURL}" Margin="30,0,0,10"
                       Height="50" Width="50"/>

            </StackPanel>

        </StackPanel>
        
    </DataTemplate>
    
</kanban:SfKanban.CardTemplate>


{% endhighlight %}


![Template support for card in UWP SfKanban](SfKanban_images/CardTemplate.png)
