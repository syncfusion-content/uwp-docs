---
title: Detect viewer scrolled to bottom UWP SfRichTextBoxAdv | Syncfusion
description: Learn here all about how to identify whether the viewer is scrolled to the bottom in Syncfusion UWP SfRichTextBoxAdv and more.
platform: uwp
control: SfRichTextBoxAdv
documentation: ug
keywords: scroll-to-bottom
---

# Detect viewer scrolled to bottom in UWP SfRichTextBoxAdv

This page explains how to identify whether the viewer is scrolled to the bottom in Syncfusion&reg; UWP SfRichTextBoxAdv.

SfRichTextBoxAdv scrollbars can be accessed through the [VerticalScrollBar](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.RichTextBoxAdv.SfRichTextBoxAdv.html#Syncfusion_UI_Xaml_RichTextBoxAdv_SfRichTextBoxAdv_VerticalScrollBar) and [HorizontalScrollBar](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.RichTextBoxAdv.SfRichTextBoxAdv.html#Syncfusion_UI_Xaml_RichTextBoxAdv_SfRichTextBoxAdv_HorizontalScrollBar) properties of [SfRichTextBoxAdv](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.RichTextBoxAdv.SfRichTextBoxAdv.html) class. Using these properties, we can identify when the document is scrolled to the bottom of the control. 

We can use the ValueChanged event of the [VerticalScrollBar](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.RichTextBoxAdv.SfRichTextBoxAdv.html#Syncfusion_UI_Xaml_RichTextBoxAdv_SfRichTextBoxAdv_VerticalScrollBar) for this purpose. Check if the scroll bar's value equals the [VerticalScrollBar](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.RichTextBoxAdv.SfRichTextBoxAdv.html#Syncfusion_UI_Xaml_RichTextBoxAdv_SfRichTextBoxAdv_VerticalScrollBar) Maximum property value, if these values are equal then the vertical scroll bar has been scrolled to the bottom of the control.

The following code example illustrates to identify whether the viewer is scrolled to the bottom of the SfRichTextBoxAdv.

{% tabs %}
{% highlight c# %}
/// <summary>
///  Occurs when the element is laid out, rendered, and ready for interaction.
/// </summary>
/// <param name="sender">The source of the event.</param>
/// <param name="e">The RoutedEventArgs instance containing the event data.</param>
 private void RichTextBoxAdv_Loaded(object sender, RoutedEventArgs e)
 {
     if (richTextBoxAdv.VerticalScrollBar != null)
     {
         richTextBoxAdv.VerticalScrollBar.ValueChanged += VerticalScrollBar_ValueChanged;
     }
 }      

/// <summary>
/// Occurs when vertical scrollbar value is changed.
/// </summary>
/// <param name="sender">The source of the event.</param>
/// <param name="e">The RangeBaseValueChangedEventArgs instance containing the event data.</param>
 private void VerticalScrollBar_ValueChanged(object sender, RangeBaseValueChangedEventArgs e)
 {
     if (e.NewValue == richTextBoxAdv.VerticalScrollBar.Maximum)
     {
             ///When the scroll bar value and its maximum value are same.
             ///Then scroll reached the bottom of the control.
     }
 }
{% endhighlight %}
{% endtabs %}	