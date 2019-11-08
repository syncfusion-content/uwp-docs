---
layout: post
title: Working with page navigation in Syncfusion Essential UWP PDF viewer.
description: Working with page navigation in Syncfusion Essential UWP PDF viewer.
platform: uwp
control: PDF viewer
documentation: ug
---

## Working with page navigation

Navigation between the pages of the PDF document can be achieved using the GotoPage method or using the commands.

The following code snippet explains the page navigation using the GotoPage Method.

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

The following commands can also be used for page navigation:

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
Goes to the first page.
</td>
</tr>
<tr>
<td>
LastPageCommand
</td>
<td>
Goes to the last page.
</td>
</tr>
<tr>
<td>
PreviousPageCommand
</td>
<td>
Goes to the previous page.
</td>
</tr>
<tr>
<td>
NextPageCommand
</td>
<td>
Goes to the next page.
</td>
</tr>
<tr>
<td>
GoToPageCommand
</td>
<td>
Goes to the specified page.
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

NextPageCommand displays the page next to the currently displayed page in the PDF Viewer. 

{% tabs %}
{% highlight xaml %}
<Button Command="{Binding NextPageCommand}" />
{% endhighlight %}
{% endtabs %}

**PreviousPageCommand**

PreviousPageCommand displays the page previous to the currently displayed page in the PDF Viewer. 

{% tabs %}
{% highlight xaml %}
<Butston Command="{Binding PreviousPageCommand}" />
{% endhighlight %}
{% endtabs %}

**GoToPageCommand**

This predefined command displays the specified page. 

{% tabs %}
{% highlight xaml %}
<Button Command="{Binding GoToPageCommand}" CommandParameter="{Binding Path=Text, ElementName=PageNumberTextBox}" />
{% endhighlight %}
{% endtabs %}

Events associated with the Page Navigation:

<table>
<tr>
<td>
Name
</td>
<td>
Description
</td>
<td>
Arguments
</td>
<td>
Type
</td>
</tr>
<tr>
<td>
PageChanged
</td>
<td>
Triggers when the specified page is rendered.
</td>
<td>
PageChangedEventArgs
</td>
<td>
EventHandler
</td>
</tr>
</table>

**PageChanged Event**

This event is triggered when there is a change in the page being displayed in the PDF Viewer.

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
