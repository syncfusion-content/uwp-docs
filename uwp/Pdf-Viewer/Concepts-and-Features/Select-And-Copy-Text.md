---
layout: post
title: Working with text selection in UWP Pdf Viewer | Syncfusion
description: Learn here all about Working with text selection support in Syncfusion UWP Pdf Viewer (SfPdfViewer) control, its elements, and more.
platform: UWP
control: SfPdfViewerControl
documentation: ug
---

# Working with text selection in UWP PDF Viewer (SfPdfViewer)

The PDF Viewer supports text selection and copy feature, which allows user to select the text in the PDF document and copy it to the clipboard. This section illustrates about how to use this feature.

<table>

<tr>
<th>Property</th>
<th>Action</th>
</tr>

<tr>
<td>IsTextSelectionEnabled</td>
<td>Gets or sets the value that enables or disables the text selection feature in the PDF Viewer. This property when set to true enables text selection and vice versa. By default, this property is set to true.</td>
</tr>

</table>

{% tabs %}
{% highlight xaml %}

<syncfusion:SfPdfViewerControl x:Name="pdfViewerControl" IsTextSelectionEnabled="False"/>

{% endhighlight %}
{% endtabs %}

{% tabs %}
{% highlight c# %}

//Text selection feature in the PDF Viewer is disabled.
pdfViewerControl.IsTextSelectionEnabled = false;

{% endhighlight %}
{% endtabs %}

## How to select text?

Follow below steps to select text in the PDF file. 

### Using touch gestures

1) Tap over the texts in the page, the tapped word will be selected and two bubbles will be displayed on each end.

2) Tap and drag the left bubble to select the text at the left and top, and the right bubble to select the text at the right and bottom directions. 

### Using mouse

1) To mouse pointer will be changed to the text selection pointer when pointed over the text region.

2) Place the mouse pointer on the text area and click the mouse left button and drag the mouse pointer over the text to select the text in any direction.

## How to modify the selection color?

The color used for text selection and the color of the handle can be customized. The property SelectionColor in the TextSelectionSettings class of PdfViewerControl can be used to customize them. The below code snippet illustrates the same.

{% tabs %}
{% highlight c# %}

//Customizing the color being displayed while selecting the text from PDF document.
pdfViewerControl.TextSelectionSettings.SelectionColor = global::Windows.UI.Color.FromArgb(150, 150, 207, 226);

{% endhighlight %}
{% endtabs %}

## How to enable/disable copy button in text selection?

We can enable/disable the visibility of the copy button while performing text selection. The below code example illustrates the same.

{% tabs %}
{% highlight c# %}

//Disables the copy button during text selection
pdfViewerControl.TextSelectionMenu.CopyButton.Visibility = Visibility.Collapsed;

{% endhighlight %}
{% endtabs %}

By default, the visibility of the copy button is Visible.
