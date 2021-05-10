---
layout: post
title: Watermark in UWP AutoComplete control | Syncfusion
description: Learn here all about Watermark support in Syncfusion UWP AutoComplete (SfTextBoxExt) control and more.
platform: uwp
control: SfTextBoxExt
documentation: ug
---

# Watermark in UWP AutoComplete (SfTextBoxExt)

The control will prompt the user with some information, when it is not in focus and contains an empty string.

### Using the Watermark

Watermark property allows the users to specify some information, when the text is empty. For illustration let us create a simple SfTextBoxExt, where the user is asked to enter names separated by a comma,


{% highlight xaml %}

<editors:SfTextBoxExt HorizontalAlignment="Center" 

                            VerticalAlignment="Center" 

                            Width="400"

Watermark="Enter names separated by comma (Ex : John, Kate)"/>

{% endhighlight %}

![Watermark](Watermark_images/Watermark_img1.png)

N>  The Watermark property is of the object type so any Framework elements can be hosted as Watermark content. Below example shows how to host an image and text as Watermark content.

{% highlight xaml %}

<editors:SfTextBoxExt HorizontalAlignment="Center" 

                            VerticalAlignment="Center" 

                            Width="400">

<editors:SfTextBoxExt.Watermark>

                <StackPanel Orientation="Horizontal">

                    <Image Source="Windows 8.png" Stretch="None" Margin="2"/>

                    <TextBlock Text="Search Windows" Opacity="0.5" Margin="5 2"/>

                </StackPanel>

            </editors:SfTextBoxExt.Watermark>

</editors:SfTextBoxExt>

{% endhighlight %}


![Watermark](Watermark_images/Watermark_img3.png)


### Using the Watermark template

Any business object can be bound to the Watermark property and that object can be decorated by applying the WatermarkTemplate property.

{% highlight xaml %}

<editors:SfTextBoxExt HorizontalAlignment="Center" 

                            VerticalAlignment="Center" 

                            Width="400"

                            Watermark="{Binding Person}">

<editors:SfTextBoxExt.WatermarkTemplate>

                <DataTemplate>

                    <TextBlock Text="{Binding}" Opacity="0.5"/>

                </DataTemplate>

            </editors:SfTextBoxExt.WatermarkTemplate>

</editors:SfTextBoxExt>

{% endhighlight %}

