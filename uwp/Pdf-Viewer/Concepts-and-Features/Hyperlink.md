---
layout: post
title: Hyperlink in UWP PDF Viewer control | Syncfusion
description: Learn here all about the Hyperlink support in the Syncfusion<sup>®</sup> UWP PDF Viewer (SfPdfViewer) control and more.
platform: uwp
control: SfPdfViewerControl
documentation: ug
---

# Hyperlink in UWP PDF Viewer (SfPdfViewer)

PDF Viewer supports hyperlink navigation which detects document link and web link present in the pages of the PDF document. Tapping on the TOC and hyperlink will behave in the following manner.

1) If the tapped text contains web link, then the URI associated with the hyperlink will be opened in the default browser.

2) If the tapped text contains document link, then the PDF Viewer navigates to the destination page index which is associated with it.

## How to disable hyperlink navigation in PDF document using PDF Viewer control?

You can disable the hyperlink navigation by setting the “AllowHyperlinkNavigation” property of PDF Viewer to false. By default, hyperlink navigation will be enabled in PDF Viewer.

{% tabs %}
{% highlight xaml %}

<syncfusion:SfPdfViewerControl x:Name="pdfViewerControl" AllowHyperlinkNavigation="False"/>

{% endhighlight %}
{% endtabs %}

## How to acquire the properties of clicked URI from PDF Viewer?

You can acquire the details of the hyperlink that is tapped in the PDF Viewer control from the HyperlinkEventArgs of HyperlinkPointerPressed event. Refer to the following code example for more details.

{% tabs %}
{% highlight xaml %}

<syncfusion:SfPdfViewerControl x:Name="pdfViewerControl" HyperlinkPointerPressed="pdfViewerControl_HyperlinkPointerPressed"/>

{% endhighlight %}
{% endtabs %}

{% tabs %}
{% highlight c# %}

        public void pdfViewerControl_HyperlinkPointerPressed(object sender,HyperlinkEventArgs args)
        {
			// Gets or sets a value indicating whether the hyperlink navigation was handled.
            args.Handled = false;

            // Gets the hyperlink being clicked.
            string uri = args.URI;

            // Gets the current page index of the hyperlink.
            int pageIndex = args.PageIndex;

            //Gets the destination page index of the hyperlink.
            int destinationPageIndex = args.DestinationPageIndex;

            //Gets the bounds of the hyperlink is being clicked.
            RectangleF hyperlinkBound = args.Bounds;

            //Gets the whether the tapped hyper link is a Web Link or Document Link.
            HyperlinkType linkType = args.HyperlinkType

        }


{% endhighlight %}
{% endtabs %}

## How to detect whether the mouse pointer is over the hyperlink text?

The event `HyperlinkPointerMoved` will be raised when the mouse pointer is moved over the hyperlink text. Refer to the following code example for more details.

{% tabs %}
{% highlight xaml %}

<syncfusion:SfPdfViewerControl x:Name="pdfViewerControl" HyperlinkPointerMoved="pdfViewerControl_HyperlinkPointerMoved"/>

{% endhighlight %}
{% endtabs %}

{% tabs %}
{% highlight c# %}

        public void pdfViewerControl_HyperlinkPointerMoved(object sender,HyperlinkEventArgs args)
        {
			// Gets or sets a value indicating whether the hyperlink navigation was handled.
            args.Handled = false;

            // Gets the hyperlink being clicked.
            string uri = args.URI;

            // Gets the current page index of the hyperlink.
            int pageIndex = args.PageIndex;

            //Gets the destination page index of the hyperlink.
            int destinationPageIndex = args.DestinationPageIndex;

            //Gets the bounds of the hyperlink is being clicked.
            RectangleF hyperlinkBound = args.Bounds;

            //Gets the whether the tapped hyper link is a Web Link or Document Link.
            HyperlinkType linkType = args.HyperlinkType

        }

{% endhighlight %}
{% endtabs %}

## How to restrict the URI navigation from the PDF Viewer?

By default, web link or document link navigation is performed on tapping the hyperlink text. This navigation can be restricted using the property 'Handled' of the `HyperlinkEventArgs`. Refer to the following code snippet for more details.

{% tabs %}
{% highlight c# %}

        public void pdfViewerControl_HyperlinkPointerPressed(object sender,HyperlinkEventArgs args)
        {
			// Setting the property to true will restrict the URI navigation inside the PDF Viewer control. In default, the value is false.
            args.Handled = false;
        }

{% endhighlight %}
{% endtabs %}
