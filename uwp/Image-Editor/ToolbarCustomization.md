---
layout: post
title: ToolbarCustomization | SfImageEditor | uwp | Syncfusion
description: ToolbarCustomization
platform: uwp
control: SfImageEditor
documentation: ug
---

# Toolbar Customization

You can change the default colors of the ColorPalette and visibility of the toolbar.

## To customize the ColorPalette

The following code explains to change the colors of the ColorPalette.

{% tabs %}

{% highlight XAML %}

    <control:SfImageEditor.ColorPalette>

        <SolidColorBrush>Yellow</SolidColorBrush>
        <SolidColorBrush>Pink</SolidColorBrush>
        <SolidColorBrush>Violet</SolidColorBrush>

    </control:SfImageEditor.ColorPalette>    

{% endhighlight %}

{% highlight C# %}

    List<SolidColorBrush> CustomColorPalette = new List<SolidColorBrush>()
    {
            new SolidColorBrush(Colors.Yellow),
            new SolidColorBrush(Colors.Pink),
            new SolidColorBrush(Colors.Violet)
    };
     
    imageEditor.ColorPalette = CustomColorPalette;

{% endhighlight %}

{% endtabs %}


## To Hide/Visible the Toolbar

You can customize the toolbar as shown below,

{% tabs %}

{% highlight XAML %}

    <control:SfImageEditor.ToolbarSettings>
        <control:ToolbarSettings IsToolbarVisiblity="False"/>
    </control:SfImageEditor.ToolbarSettings>

{% endhighlight %}            

{% highlight C# %}

    imageEditor.ToolbarSettings.IsToolbarVisiblity = false;

{% endhighlight %}

{% endtabs %}

![Toolbar visibility](toolbarCustomization_images/ToolbarVisibility.png)


## To Hide/Visible the toolbar Item

You can customize the toolbar items namely, text, path, shapes, transform, rectangle, circle, arrow, flip, crop, rotate, reset, undo, Redo and save as shown below,

{% highlight C# %}

    imageEditor.SetToolbarItemVisibility("text, save", false); 

{% endhighlight %}

![Toolbar item visibility](toolbarCustomization_images/ToolbarItemVisibility.png)

## To hide or show the delete button

You can show or hide the delete button, which employed in deleting the selected shapes added in image editor with the help of [`ShowDeleteButton`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.ImageEditor.ToolbarSettings.html#Syncfusion_UI_Xaml_ImageEditor_ToolbarSettings_ShowDeleteButton) property in [`ToolbarSettings`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.ImageEditor.ToolbarSettings.html).

Setting false for this property will never show the delete button. On setting true, delete button will get enabled by selecting the shapes.

{% tabs %}

{% highlight XAML %}

            <syncfusion:SfImageEditor.ToolbarSettings>
                <syncfusion:ToolbarSettings ShowDeleteButton="False"></syncfusion:ToolbarSettings>
            </syncfusion:SfImageEditor.ToolbarSettings>

{% endhighlight %}            

{% highlight C# %}

            ToolbarSettings settings = new ToolbarSettings();
            settings.ShowDeleteButton = false;
            editor.ToolbarSettings = settings;

{% endhighlight %}

{% endtabs %}

![Delete button](toolbarCustomization_images/DeleteButton.png)

## Toolbar color customization

Border color of the toolbar can be customized with the help of [`BorderColor`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.ImageEditor.ToolbarSettings.html#Syncfusion_UI_Xaml_ImageEditor_ToolbarSettings_BorderColor) property in ToolbarSettings.

{% tabs %}

{% highlight XAML %}

            <syncfusion:SfImageEditor.ToolbarSettings>
                <syncfusion:ToolbarSettings BorderColor="Red"></syncfusion:ToolbarSettings>
            </syncfusion:SfImageEditor.ToolbarSettings>

{% endhighlight %}            

{% highlight C# %}

            ToolbarSettings settings = new ToolbarSettings();
            settings.BorderColor = new SolidColorBrush(Colors.Red);
            editor.ToolbarSettings = settings;

{% endhighlight %}

{% endtabs %}

![Border color](toolbarCustomization_images/BorderColor.png)