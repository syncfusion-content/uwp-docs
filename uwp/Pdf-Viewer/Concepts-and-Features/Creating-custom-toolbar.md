---
layout: post
title: Creating a custom toolbar in UWP Pdf Viewer | Syncfusion
description: Learn here all about Creating a custom toolbar support in Syncfusion UWP Pdf Viewer (SfPdfViewer) control, its elements, and more.
platform: uwp
control: PDF viewer
documentation: ug
---

# Creating a custom toolbar in UWP PDF Viewer (SfPdfViewer)

PdfViewer does not have a toolbar by default. But a custom toolbar can be designed at the sample with its buttons wired to the PdfViewer APIs. 

## Creating separate UIs for desktop and mobile

Create a new UWP project (the name &#34;PdfViewerCustomToolbar&#34; is used here). It will by default have a MainPage.xaml file, a MainPage.xaml.cs file. Create a new folder in the project with name &#34;DeviceFamily-Mobile&#34; and create another XAML file with the same name MainPage.xaml in this folder.  Open this file and set the class property to MainPage.xaml.cs. 

{% tabs %}
{% highlight xaml %}

x:Class="PdfViewerCustomToolbar.MainPage";

{% endhighlight %}
{% endtabs %}

Make sure that both the xaml files are in the same namespace &#34;PdfViewerCustomToolbar&#34;

{%tabs%}
{%highlight xaml%}

xmlns:local="using:PdfViewerCustomToolbar";

{%endhighlight%}
{%endtabs%}

The reason for two XAML files is that same UI design cannot be used for both desktop and mobile. So, one XAML file is used for desktop UI and the other is for mobile UI. The MainPage.xaml.cs file serve as the common code behind for both XAML pages. 

In the constructor of MainPage set the DataContext to PdfViewer. 

{%tabs%}
{%highlight c#%}

this.DataContext = pdfViewer;

{%endhighlight%}
{%endtabs%}

The UI design of the application for desktop and mobile is illustrated in the following documentation pages. The link to the common sample can be found at the ends of both the documentation pages.  

1.	[Desktop design](https://help.syncfusion.com/uwp/pdf-viewer/concepts-and-features/ui-design-for-desktop)
2.	[Mobile design](https://help.syncfusion.com/uwp/pdf-viewer/concepts-and-features/ui-design-for-mobile)
