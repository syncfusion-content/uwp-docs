---
layout: post
title: Rendering PDF pages using PDFium renderer | Syncfusion
description: The Syncfusion Essential UWP PDF viewer provides option to render the PDF pages using PDFium rendering engine. 
platform: uwp
control: PDF viewer
documentation: ug
---

# Render PDF Pages using the PDFium renderer 

The [`SfPdfViewerControl`](https://help.syncfusion.com/cr/uwp/Syncfusion.Windows.PdfViewer.SfPdfViewerControl.html) allows the users to render the PDF pages using the PDFium rendering engine. The `IPdfRenderer` interface defines the methods and properties which provides the necessary values and perform the necessary operations to render the pages using the PDFium library. The user needs to add a class in their application which must implement this interface and assign an instance of this class to the Renderer property of the [`SfPdfViewerControl`](https://help.syncfusion.com/cr/uwp/Syncfusion.Windows.PdfViewer.SfPdfViewerControl.html). 

The PDF page rendering using the PDFium rendering engine is shown in detail 
as follows. 

## Loading the PDFium library

To render the PDF pages using PDFium, the pdfium.dll library for the corresponding platform configuration (x86 or x64) must be loaded in the application project. The library can be either loaded from a file path or it can be added as a content file in the application project.

### Loading the library from the file path

Load the library from file path using the LoadLibrary external method. 

{% tabs %}
{% highlight c# %}

	string path = Path.Combine(ApplicationData.Current.LocalFolder.Path, "pdfium.dll");
    LoadLibrary(path);

{% endhighlight %}
{% endtabs %}

### Adding the library as Content

Add the pdfium.dll file to the project with BuildAction as content. When added as content, it is not necessary to load the library programmatically. 

## Implementing the IPdfRenderer interface

Add a class to the application project and implement the `IPdfRenderer` interface in the class. 

### Add definitions of the external methods

In the class, define the external methods for the necessary operations such as initializing the PDFium library, rendering the PDF pages, obtaining the page size, and more. The pdfium.dll library provides implementations for these external methods. 

Each external method definition must be preceded by the DllImport attribute. 


{% tabs %}
{% highlight c# %}

    [DllImport("kernel32", SetLastError = true, CharSet = CharSet.Auto)]
    private static extern IntPtr LoadLibrary([MarshalAs(UnmanagedType.LPTStr)] string lpFileName);

    [DllImport("pdfium.dll", EntryPoint = "FPDF_InitLibrary")]
    public static extern void FPDF_InitLibrary();

    [DllImport("pdfium.dll")]
    public static extern int FPDF_GetPageCount(IntPtr document);

    [DllImport("Pdfium.dll")]
    public static extern int FPDF_GetPageSizeByIndex(IntPtr document, int page_index, out double width, out double height);

    [DllImport("Pdfium.dll")]
    public static extern IntPtr FPDFBitmap_CreateEx(int width, int height, int format, IntPtr first_scan, int stride);

    [DllImport("Pdfium.dll")]
    public static extern void FPDFBitmap_FillRect(IntPtr bitmapHandle, int left, int top, int width, int height, uint color);

    [DllImport("Pdfium.dll")]
    public static extern IntPtr FPDFBitmap_Destroy(IntPtr bitmapHandle);

    [DllImport("Pdfium.dll")]
    public static extern void FPDF_RenderPageBitmap(IntPtr bitmapHandle, IntPtr page, int start_x, int start_y, int size_x, int size_y, int rotate, FPDF flags);

    [DllImport("pdfium.dll")]
    public static extern IntPtr FPDF_LoadPage(IntPtr document, int page_index);

    [DllImport("Pdfium.dll")]
    public static extern int FPDF_GetPageWidth(IntPtr page);

    [DllImport("Pdfium.dll")]
    public static extern int FPDF_GetPageHeight(IntPtr page);

    [DllImport("Pdfium.dll", CharSet = CharSet.Ansi)]
    public static extern IntPtr FPDF_LoadCustomDocument([MarshalAs(UnmanagedType.LPStruct)]FPDF_FILEACCESS access, string password);

    [DllImport("Pdfium.dll")]
    public static extern void FPDF_CloseDocument(IntPtr page);

    [DllImport("Pdfium.dll")]
    public static extern IntPtr FPDF_ClosePage(IntPtr page);

{% endhighlight %}
{% endtabs %}

### Initialize the PDFium library

The following code sample shows initializing the PDFium library and loading the PDF document. The `Initialize` method will be called every time a PDF is called.

{% tabs %}
{% highlight c# %}

	public void Initialize(Stream stream, string password)
    {
        fileStream = stream;
        FPDF_InitLibrary();
        FPDF_FILEACCESS access = new FPDF_FILEACCESS
        {
            m_FileLen = (uint)fileStream.Length,
            m_GetBlock = Marshal.GetFunctionPointerForDelegate(_getBlockDelegate),
            m_Param = (IntPtr)2,
        };
        document = FPDF_LoadCustomDocument(access, password);
    }

{% endhighlight %}
{% endtabs %}

### Implement the PageCount property

The `PageCount` property must return the total page count by calling the external method defined earlier. When a new PDF is loaded, the previous PDF must be closed and the page count should be reset. 

{% tabs %}
{% highlight c# %}

	public int PageCount
    {
        get
        {
            if (pageCount == -1)
                pageCount = FPDF_GetPageCount(document);
            return pageCount;
        }
    }

{% endhighlight %}
{% endtabs %}

### Implement the GetPageSize method

The `GetPageSize` method must call the external method and return the size of the PDF page corresponding to the given index. 

{% tabs %}
{% highlight c# %}

	public Size GetPageSize(int pageIndex)
    {
        double height = 0, width = 0;
        FPDF_GetPageSizeByIndex(document, pageIndex, out width, out height);
        Size size;
        size.Width = (int)width;
        size.Height = (int)height;
        return size;
    }

{% endhighlight %}
{% endtabs %}

### Render the PDF page

The `RenderPageBitmap` method must call the external methods which render the PDF page and return the rendered SoftwareBitmap.

{% tabs %}
{% highlight c# %}

	public SoftwareBitmap RenderPageBitmap(int pageIndex, double pageWidth, double pageHeight)
    {
        var page = FPDF_LoadPage(document, pageIndex);

        int width = (int)pageWidth;
        int height = (int)pageHeight;
        byte[] buffer = new byte[width * height * 4];

        unsafe
        {
            fixed (byte* p = buffer)
            {
                IntPtr createdpages = FPDFBitmap_CreateEx(width, height, 4, (IntPtr)p, width * 4);
                uint background = 0xFFFFFFFF;
                FPDFBitmap_FillRect(createdpages, 0, 0, width, height, background);
                FPDF_RenderPageBitmap(createdpages, page, 0, 0, width, height, 0, FPDF.ANNOT);
                FPDFBitmap_Destroy(createdpages);
                FPDF_ClosePage(page);
            }
        }

        SoftwareBitmap softwareBitmap = new SoftwareBitmap(BitmapPixelFormat.Bgra8, width, height, BitmapAlphaMode.Premultiplied);
        softwareBitmap.CopyFromBuffer(buffer.AsBuffer());

        return softwareBitmap;
    }

{% endhighlight %}
{% endtabs %}

### Close the PDF document

When a new PDF is to be loaded, the previous PDF must be closed, and the page count should be reset. 

{% tabs %}
{% highlight c# %}

	public void Close()
    {
        if (document != IntPtr.Zero)
            FPDF_CloseDocument(document);
        pageCount = -1;
    }

{% endhighlight %}
{% endtabs %}


### Setting the Renderer property

Set the `Renderer` property to a new instance of the class created above. If the `Renderer` property is not set, the pages are rendered using the default rendering of a [`SfPdfViewerControl`](https://help.syncfusion.com/cr/uwp/Syncfusion.Windows.PdfViewer.SfPdfViewerControl.html). 

{% tabs %}
{% highlight c# %}

	sfPdfViewerControl.Renderer = new CustomerPDFRenderer();

{% endhighlight %}
{% endtabs %}

## PDFium renderer sample

The sample that illustrates loading a PDF using the Pdfium renderer can be downloaded from the link below. 
  
<https://www.syncfusion.com/downloads/support/directtrac/general/ze/PdfiumRenderer-36218231.zip> 

N> Please ensure that the proper file path for the pdfium.dll assembly is provided in the `Initialize` method of the `CustomerPdfRenderer` class before running the application. Also make sure that you are using the appropriate pdfium.dll assembly with respect to their architecture (x86 or x64).
