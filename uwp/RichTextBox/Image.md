---
title: Image in UWP RichTextBox control | Syncfusion
description: Learn here all about Image support in Syncfusion UWP RichTextBox (SfRichTextBoxAdv) control and more.
platform: uwp
control: SfRichTextBoxAdv
documentation: ug
keywords: image
---
# Image in UWP RichTextBox (SfRichTextBoxAdv)

The SfRichTextBoxAdv allows you to insert images of various formats such as bitmap images (.bmp), JPEG (.jpg, .jpeg), PNG (.png) except Metafile images.
The following code example illustrates how to insert picture into the SfRichTextBoxAdv document through UI Command.
{% tabs %}
{% highlight xaml %}
<Button Content="Insert Picture" Command="{Binding ElementName=richTextBoxAdv,Path=InsertPictureCommand}"/>


{% endhighlight %}

{% endtabs %}

## Image Resizer
The SfRichTextBoxAdv also supports built-in image resizer to resize the images present in the document to your wish. The image resizer accepts both touch and mouse interactions.
![Image_img1](Image_images/Image_img1.jpeg)

