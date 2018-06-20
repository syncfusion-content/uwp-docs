---
layout: post
title: Text | SfImageEditor | uwp | Syncfusion
description: Text
platform: uwp
control: SfImageEditor
documentation: ug
---
# Text

To add the desired text elements over the image, use the following two ways:

* From Toolbar
* Using Code

## From Toolbar

To add text from the toolbar, click on the `Text` icon in the toolbar. When the Text icon is tapped, a pop-up will appear. To add the text over the image, Type the desired text and click OK. To close the pop-up, click CANCEL button. By dragging, the text can be moved to the desired place.

### To Change Color of the selected Text

Select the desired text and click on the color palette available in the sub menu.

## Using Code

programmatically, the desired text elements also can be added over the image. The `AddText` method in the SfImageEditor control is used to add text based on the string value and [`TextSettings`](https://help.syncfusion.com/cr/uwp/sfimageeditor).

### TextSettings

TextSettings is defined to set the values for Color and FontSize.

{% highlight C# %}

    imageEditor.AddText("CustomTextView", new TextSettings() { Color = new SolidColorBrush(Colors.Orange) });

{% endhighlight %}

![](text_images/AddedText.png)