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

## ToolbarHeight Customization

You can customize `height of the toolbar` and also toolbar items `icon` and `text`.

### Customize Toolbar Height 

SfImageEditor control supports to customize the default height of `Header`, `Footer` and `Sub item` Toolbar by using following properties,
1.	HeaderToolbarHeight
2.	FooterToolbarHeight 
3.	SubItemToolbarHeight

Toolbar items will be resize based on the toolbar height. To change Height of the Toolbar as like below,

{% tabs %}

{% highlight XAML %}

         <imageeditor:SfImageEditor.ToolbarSettings>
                    <imageeditor:ToolbarSettings 
                        HeaderToolbarHeight="70"
                        FooterToolbarHeight="70"                          
                        SubItemToolbarHeight="70"/>
                </imageeditor:SfImageEditor.ToolbarSettings>

{% endhighlight %}

{% highlight C# %}

    editor.ToolbarSettings.HeaderToolbarHeight = 70;
    editor.ToolbarSettings.FooterToolbarHeight = 70;
    editor.ToolbarSettings.SubItemToolbarHeight = 70;

{% endhighlight %}

{% endtabs %}

![](toolbarCustomization_images/ToolbarHeightUWP.png)

### Individual Toolbar Item Height Customization

To arrange toolbar items aspect fit based on the toolbar height by using following properties  

1.  TextHeight
2.  IconHeight

To change the toolbar item Text and Icon height as like below,

{% tabs %}

{% highlight C# %}

    FooterToolbarItem footerItem = new FooterToolbarItem()
            {
                IconHeight=40,
                TextHeight=20,
                Icon = new BitmapImage(new Uri(this.BaseUri, "ImageEditor/share.png")),
                Text = "Share"
            };

            editor.ToolbarSettings.ToolbarItems.Add(footerItem);

{% endhighlight %}

{% endtabs %}

