---
title: Layout Types in UWP RichTextBox control | Syncfusion
description: Learn here all about Layout Types support in Syncfusion UWP RichTextBox (SfRichTextBoxAdv) control and more.
platform: uwp
control: SfRichTextBoxAdv
documentation: ug
keywords: layout-types
---
# Layout Types in UWP RichTextBox (SfRichTextBoxAdv)

The SfRichTextBoxAdv control allows you to choose between the following layout types.

* Pages

* Continuous

* Block


## Pages

When using Pages layout type, the rich text document content is rendered sequentially in several pages, similar to the Print layout view of Microsoft Word. The size and margin of each page are defined by Section format properties. 
The following code example demonstrates how to define layout type of SfRichTextBoxAdv control as Pages.
{% tabs %}
{% highlight xaml %}
<RichTextBoxAdv:SfRichTextBoxAdv x:Name="richTextBoxAdv" ManipulationMode="All" LayoutType="Pages"  xmlns:RichTextBoxAdv="using:Syncfusion.UI.Xaml.RichTextBoxAdv"/>

{% endhighlight %}

{% highlight c# %}
// Initializes a new instance of SfRichTextBoxAdv.
SfRichTextBoxAdv richTextBoxAdv = new SfRichTextBoxAdv();
richTextBoxAdv.ManipulationMode = ManipulationModes.All;
// Defines the layout type as Pages.
richTextBoxAdv.LayoutType = LayoutType.Pages;

{% endhighlight %}

{% endtabs %}

![Layout-Types_img1](Layout-Types_images/Layout-Types_img1.jpeg)

## Continuous

When using Continuous layout type, the entire rich text document content is rendered continuously in a single page, similar to the Web layout view of Microsoft Word. This layout looks like a simple text box with rich-text content and can be used for applications such as forums and blogs.
The following code example demonstrates how to define layout type of SfRichTextBoxAdv control as Continuous.
{% tabs %}
{% highlight xaml %}
<RichTextBoxAdv:SfRichTextBoxAdv x:Name="richTextBoxAdv" ManipulationMode="All" LayoutType="Continuous"  xmlns:RichTextBoxAdv="using:Syncfusion.UI.Xaml.RichTextBoxAdv"/>

{% endhighlight %}

{% highlight c# %}
// Initializes a new instance of SfRichTextBoxAdv.
SfRichTextBoxAdv richTextBoxAdv = new SfRichTextBoxAdv();
richTextBoxAdv.ManipulationMode = ManipulationModes.All;
// Defines the layout type as Continuous.
richTextBoxAdv.LayoutType = LayoutType.Continuous;

{% endhighlight %}

{% endtabs %}

![Layout-Types_img2](Layout-Types_images/Layout-Types_img2.jpeg)

## Block

When using Block layout type, the rich text content is rendered continuously in a single page as read only. This layout looks like a simple text block with rich text content such as texts, images, and tables. Block Layout also supports copying contents to the clipboard. This can be used for applications such as forums and blogs in order to display the rich-text contents with same look and feel as in the continuous layout type.
The following code example demonstrates how to define layout type of SfRichTextBoxAdv control as Block.
{% tabs %}
{% highlight xaml %}
<RichTextBoxAdv:SfRichTextBoxAdv x:Name="richTextBoxAdv" ManipulationMode="All" LayoutType="Block"  xmlns:RichTextBoxAdv="using:Syncfusion.UI.Xaml.RichTextBoxAdv"/>

{% endhighlight %}

{% highlight c# %}
// Initializes a new instance of SfRichTextBoxAdv.
SfRichTextBoxAdv richTextBoxAdv = new SfRichTextBoxAdv();
richTextBoxAdv.ManipulationMode = ManipulationModes.All;
// Defines the layout type as Block.
richTextBoxAdv.LayoutType = LayoutType.Block;

{% endhighlight %}

{% endtabs %}

![Layout-Types_img3](Layout-Types_images/Layout-Types_img3.jpeg)

N> In Windows Phone device, the entire rich text content is rendered continuously in a single page as continuous layout type and there is no effect on setting other layout types.
