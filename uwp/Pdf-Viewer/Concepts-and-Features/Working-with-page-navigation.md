---
layout: post
title: Working with page navigation in UWP PDF Viewer | Syncfusion
description: Learn here all about Working with page navigation support in Syncfusion UWP PDF Viewer (SfPdfViewer) control and more.
platform: uwp
control: PDF viewer
documentation: ug
---

# Working with page navigation in UWP PDF Viewer (SfPdfViewer)

The PdfViewer allows navigation through the pages of PDF documents. The navigation from one page to other can be done by using “GoToPage” method.

The following code snippet illustrates page navigation using the GotoPage method.

{% tabs %}
{% highlight c# %}
// Navigates to the page 5 in the PDF document.
pdfViewer.GotoPage(5);
{% endhighlight %}
{% highlight vbnet %}
‘Navigates to the page 5 in the PDF document.
pdfViewer.GotoPage(5)
{% endhighlight %}
{% endtabs %}

There are also commands in PdfViewer, which could make the page navigation simpler:

<table>
<tr>
<td>
Names
</td>
<td>
Description
</td>
</tr>
<tr>
<td>
FirstPageCommand
</td>
<td>
Navigates to the first page of the PDF document.
</td>
</tr>
<tr>
<td>
LastPageCommand
</td>
<td>
Navigates to the last page of the PDF document.
</td>
</tr>
<tr>
<td>
PreviousPageCommand
</td>
<td>
Navigates to the previous page of the PDF document.
</td>
</tr>
<tr>
<td>
NextPageCommand
</td>
<td>
Navigates to the next page of the PDF document.
</td>
</tr>
<tr>
<td>
GoToPageCommand
</td>
<td>
Navigates to the specified page of the PDF document.
</td>
</tr>
</table>

**FirstPageCommand**

Navigation to the first page can be achieved by using the FirstPageCommand as shown below.

{% tabs %}
{% highlight xaml %}
<Button Command="{Binding FirstPageCommand}" />
{% endhighlight %}
{% endtabs %}

**LastPageCommand**

Navigation to the last page can be achieved by using the LastPageCommand as shown below. 

{% tabs %}
{% highlight xaml %}
<Button Command="{Binding LastPageCommand}" />
{% endhighlight %}
{% endtabs %}

**NextPageCommand**

NextPageCommand navigates to the page next to the currently displayed page in the PDF Viewer. 

{% tabs %}
{% highlight xaml %}
<Button Command="{Binding NextPageCommand}" />
{% endhighlight %}
{% endtabs %}

**PreviousPageCommand**

PreviousPageCommand navigates to the page previous to the currently displayed page in the PDF Viewer. 

{% tabs %}
{% highlight xaml %}
<Butston Command="{Binding PreviousPageCommand}" />
{% endhighlight %}
{% endtabs %}

**GoToPageCommand**

This command navigates to the specified page. 

{% tabs %}
{% highlight xaml %}
<Button Command="{Binding GoToPageCommand}" CommandParameter="{Binding Path=Text, ElementName=PageNumberTextBox}" />
{% endhighlight %}
{% endtabs %}

In the above snippet, the PageNumberTextBox refers to a text box instance that gets the page number input. 

**Tracking the change of pages in PDF document**


The PageChanged event is triggered when there is a change in the page being displayed in the PDF Viewer.

The following code snippet updates the current page number in a text block, whenever the page is changed.

{% tabs %}
{% highlight c# %}
private void PdfViewer_PageChanged(object sender, PageChangedEventArgs e)
{
    pageNumberTextBlock.Text = e.NewPageNumber.ToString();
}
{% endhighlight %}
{% highlight vbnet %}
Private Sub PdfViewer_PageChanged(sender As Object, e As PageChangedEventArgs) Handles pdfViewer.PageChanged
    pageNumberTextBlock.Text = e.NewPageNumber.ToString()
End Sub
{% endhighlight %}
{% endtabs %}
