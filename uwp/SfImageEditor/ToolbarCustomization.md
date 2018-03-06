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

![](toolbarCustomization_images/ToolbarVisibility.png)


## To Hide/Visible the toolbar Item

You can customize the toolbar items namely, text, path, shapes, transform, rectangle, circle, arrow, flip, crop, rotate, reset, undo, Redo and save as shown below,

{% highlight C# %}

    imageEditor.SetToolbarItemVisibility("text, save", false); 

{% endhighlight %}

![](toolbarCustomization_images/ToolbarItemVisibility.png)