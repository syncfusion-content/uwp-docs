---
layout: post
title: Explore the How To Do Options for ReportWriter
description: how to do the various operations with reportwriter?
platform: UWP
control: ReportWriter
documentation: ug
---

# How to

## Save a Report as a Stream?

You can save a report as a stream using Save(Stream,WriterFormat) (overloaded method). This method is useful when generating the report on the server side and sending it to a client-side application. The following code explains how to save a report as a stream.

~~~csharp
//Step 1: create the report data source
ReportDataSourceCollection dataSources = new ReportDataSourceCollection();

dataSources.Add(new ReportDataSource() { Name = "Sales", Value = GetDataSource() });

//Step 2: Instantiate the reportwriter with the parameter "ReportPath" and ReportDataSource Collection
ReportWriter reportWriter = new ReportWriter(reportPath, dataSources);

MemoryStream stream = new MemoryStream();

//Step 3: Save the report as PDF, Word, HTML, PPT or Excel document in the form of stream contents
reportWriter.Save(stream, WriterFormat.PDF);

~~~
