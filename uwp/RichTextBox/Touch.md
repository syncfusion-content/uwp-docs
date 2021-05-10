---
title: Touch in UWP RichTextBox control | Syncfusion
description: Learn here all about Touch support in Syncfusion UWP RichTextBox (SfRichTextBoxAdv) control and more.
platform: uwp
control: SfRichTextBoxAdv
documentation: ug
keywords: Touch
---
# Touch in UWP RichTextBox (SfRichTextBoxAdv)

In UWP application, you should specify the **ManipulationMode** property for the controls in order to enable touch manipulations such as pan/scroll and zoom. Similarly, you should specify the **ManipulationMode** property for the SfRichTextBoxAdv control.
The following code example demonstrates how to configure all the touch manipulations in SfRichTextBoxAdv control.
{% tabs %}
{% highlight xaml %}
<RichTextBoxAdv:SfRichTextBoxAdv x:Name="richTextBoxAdv" ManipulationMode="All" xmlns:RichTextBoxAdv="using:Syncfusion.UI.Xaml.RichTextBoxAdv"/>


{% endhighlight %}

{% highlight c# %}
// Initializes a new instance of SfRichTextBoxAdv control.
SfRichTextBoxAdv richTextBoxAdv = new SfRichTextBoxAdv();
// Specifies the manipulation mode for the control.
richTextBoxAdv.ManipulationMode = ManipulationModes.All;


{% endhighlight %}

{% endtabs %}

You can configure the specific touch manipulations for an UIElement by setting appropriate combinations of Manipulation modes. The following table demonstrates the Manipulation modes for enabling specific touch manipulations.
<table>
<tr>
<td>
{{'**Touch Manipulation**'| markdownify }}
</td>
<td>
{{'**ManipulationMode**'| markdownify }}
</td>
</tr>
<tr>
<td>
Vertical scrolling only
</td>
<td>
TranslateY, TranslateInertia
</td>
</tr>
<tr>
<td>
Horizontal scrolling only
</td>
<td>
TranslateX, TranslateInertia
</td>
</tr>
<tr>
<td>
Vertical and horizontal scrolling only
</td>
<td>
TranslateX, TranslateY, TranslateInertia
</td>
</tr>
<tr>
<td>
Scaling only
</td>
<td>
Scale, ScaleInertia
</td>
</tr>
<tr>
<td>
Scrolling and scaling only
</td>
<td>
Scale, ScaleInertia, TranslateX, TranslateY, TranslateInertia
</td>
</tr>
</table>

The following code example demonstrates how to configure the touch manipulations for scrolling and scaling alone in SfRichTextBoxAdv control.
{% tabs %}
{% highlight xaml %}
<RichTextBoxAdv:SfRichTextBoxAdv x:Name="richTextBoxAdv" ManipulationMode="Scale, ScaleInertia, TranslateX, TranslateY, TranslateInertia" xmlns:RichTextBoxAdv="using:Syncfusion.UI.Xaml.RichTextBoxAdv"/>


{% endhighlight %}

{% highlight c# %}
// Initializes a new instance of SfRichTextBoxAdv control.
SfRichTextBoxAdv richTextBoxAdv = new SfRichTextBoxAdv();
// Specifies the manipulation mode for the control.
richTextBoxAdv.ManipulationMode = ManipulationModes.Scale | ManipulationModes.ScaleInertia | ManipulationModes.TranslateX | ManipulationModes.TranslateY | ManipulationModes.TranslateInertia;


{% endhighlight %}

{% endtabs %}

