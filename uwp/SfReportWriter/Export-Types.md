---
layout: post
title: Exporting a Report as Various Documents formats
description: How To save a report as PDF, Word, Excel, PPT and HTML documents?
platform: UWP
control: ReportWriter
documentation: ug
---

## Exporting Reports

The ReportWriter provides support for exporting report as PDF, Word, Excel, PPT and HTML documents with the help of the ReportWriter class.

### Exporting Report as PDF

The report used in ReportWriter can be exported as PDF document using the following code.

~~~ csharp
ReportWriter writer = new ReportWriter(reportStream, datas);
writer.Save("Sample.pdf", WriterFormat.PDF);
~~~
![](UWP_Images/RDLExportPdf.png) 

### Exporting Report as Word

The report used in ReportWriter can be exported as Word document using the following code.

~~~ csharp
ReportWriter writer = new ReportWriter(reportStream, datas);
writer.Save("Sample.doc", WriterFormat.Word);
~~~
![](UWP_Images/RDLExportWord.png)

### Exporting Report as Excel

The report used in ReportWriter can be exported as Excel document using the following code.

~~~ csharp
ReportWriter writer = new ReportWriter(reportStream, datas);
writer.Save("Sample.xls", WriterFormat.Excel);
~~~
![](UWP_Images/RDLExportExcel.png) 

### Exporting Report as HTML

The report used in ReportWriter can be exported as HTML document using the following code.

~~~ csharp
ReportWriter writer = new ReportWriter(reportStream, datas);
writer.Save("Sample.html", WriterFormat.HTML);
~~~
![](UWP_Images/RDLExportHtml.png) 

### Exporting Report as PPT

The report used in ReportWriter can be exported as PPT document using the following code.

~~~ csharp
ReportWriter writer = new ReportWriter(reportStream, datas);
writer.Save("Sample.ppt", WriterFormat.PPT);
~~~
![](UWP_Images/RDLExportPPT.png) 