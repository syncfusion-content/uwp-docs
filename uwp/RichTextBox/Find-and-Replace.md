---
title: Find and Replace in UWP RichTextBox control | Syncfusion
description: Learn here all about Find and Replace support in Syncfusion UWP RichTextBox (SfRichTextBoxAdv) control and more.
platform: uwp
control: SfRichTextBoxAdv
documentation: ug
keywords: search,find,replace-text
---
# Find and Replace in UWP RichTextBox (SfRichTextBoxAdv)

The SfRichTextBoxAdv control supports searching text contents in the document. This when used in combination with selection becomes a powerful tool enabling scenarios like highlighting specific parts of the document, applying formatting such as bold or replacing text. You can extend your search by using regular expression to find particular pattern of text in the document. 
The following code example explains how to find the first occurrence of a particular text in the document and apply bold formatting.
{% tabs %}
{% highlight c# %}
// Finds the first occurrence of specified text that matches case in RichTextBoxAdv document from current selection.
TextSearchResult textSearchResult = richTextBoxAdv.Find("Panda", FindOptions.CaseSensitive);
// Selects the text search result.
richTextBoxAdv.Selection.Select(textSearchResult.Start, textSearchResult.End);
// Applies Bold formatting for the current selection.
richTextBoxAdv.Selection.CharacterFormat.Bold = true;


{% endhighlight %}

{% endtabs %}

The following code example demonstrates how to find all occurrences of a particular pattern of text in the document and highlighting the result.
{% tabs %}
{% highlight c# %}
// Finds all the words that starts with ‘S’ in RichTextBoxAdv document.
TextSearchResults textSearchResults = richTextBoxAdv.FindAll(new Regex(@"\bS\S*"), FindOptions.None);

// If any text search results found.
if (textSearchResults != null)
{
    for (int j = 0; j < textSearchResults.Count; j++)
    {
    
        TextSearchResult textSearchResult = textSearchResults[j];

        // Adds the search result text positions to the selection.
        richTextBoxAdv.Selection.SelectionRanges.Add(textSearchResult.Start, textSearchResult.End);
    }
    
// Apply highlight color for the selection.
    richTextBoxAdv.Selection.CharacterFormat.HighlightColor = HighlightColor.Yellow;
}



{% endhighlight %}

{% endtabs %}

## Replacing existing text

You can replace a single occurrence or all occurrences of a particular text or pattern of text in a document with another text by performing search operation. This helps you to modify the contents easily.
The following code example demonstrates how to replace a single occurrence of a text with another text in SfRichTextBoxAdv.
{% tabs %}
{% highlight c# %}
// Finds the text "flat" that matches whole word in the document.
TextSearchResult textSearchResult = richTextBoxAdv.Find("flat", FindOptions.WholeWord);

// If any text search result found, replace it with the text "apartment".
if (textSearchResult != null)
    textSearchResult.Replace("apartment");


{% endhighlight %}

{% endtabs %}

The following code example demonstrates how to replace all occurrences of a particular text with another text in SfRichTextBoxAdv.
{% tabs %}
{% highlight c# %}
// Finds the text "lift" that matches whole word in the document.
TextSearchResults textSearchResults = richTextBoxAdv.FindAll("lift", FindOptions.WholeWord);

// If any text search results found, replace all occurrences with the text "elevator".
if(textSearchResults != null)
    textSearchResults.ReplaceAll("elevator");


{% endhighlight %}

{% endtabs %}

## Options Pane

The SfRichTextBoxAdv provides the built-in options pane support to find the text and navigate to text results similar to Microsoft Word application. It also provides separate pane for advanced find and replace options.
The following code example demonstrates how to show the default search pane in SfRichTextBoxAdv through command binding.
{% tabs %}
{% highlight xaml %}
<!-- Binding Button to UI Command that shows the default search pane  -->
<Button Content="Show Search Pane" Command="{Binding ElementName=richTextBoxAdv, Path=ShowOptionsPaneCommand}" />


{% endhighlight %}

{% endtabs %}

![http://help.syncfusion.com/winrt/richtextboxadv/Find-and-Replace-text_images/Find-and-Replace-text_img1.png](Find-and-Replace_images/Find-and-Replace_img1.jpeg)

The following code example demonstrates how to show the advance find pane in SfRichTextBoxAdv through command binding.
{% tabs %}
{% highlight xaml %}
<!-- Binding Button to UI Command that shows the advanced find pane  -->
<Button Content="Show Advanced Find Pane" Command="{Binding ElementName=richTextBoxAdv, Path=ShowOptionsPaneCommand}" CommandParameter="Find"/>


{% endhighlight %}
{% endtabs %}

![http://help.syncfusion.com/winrt/richtextboxadv/Find-and-Replace-text_images/Find-and-Replace-text_img2.png](Find-and-Replace_images/Find-and-Replace_img2.jpeg)

The following code example demonstrates how to show the advance replace pane in SfRichTextBoxAdv through command binding.
{% tabs %}
{% highlight xaml %}
<!-- Binding Button to UI Command that shows the advanced replace pane  -->
<Button Content="Show Advanced Replace Pane" Command="{Binding ElementName=richTextBoxAdv, Path=ShowOptionsPaneCommand}" CommandParameter="Replace"/>


{% endhighlight %}

{% endtabs %}

![http://help.syncfusion.com/winrt/richtextboxadv/Find-and-Replace-text_images/Find-and-Replace-text_img2.png](Find-and-Replace_images/Find-and-Replace_img3.jpeg)

N> Currently, the SfRichTextBoxAdv does not support options pane in Phone device.
