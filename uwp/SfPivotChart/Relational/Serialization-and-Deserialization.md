---
layout: post
title: Serialization and Deserialization | SfPivotChart | UWP | Syncfusion
description: Serialization and Deserialization
platform: UWP
control: SfPivotChart
documentation: ug
---

# Serialization and Deserialization

SfPivotChart provides support to save and load the entire report and control setting using DataContractSerializer.The Serialization and de-serialization can be done using any one of the below formats.

## Serialization 

It allows the user to serialize SfPivotChart by using [Serialize] method which exports the current PivotChart control properties to an XML file.The Serialization can be done using any one of the below formats.

### Serialize using Stream 

It allows the user to save the SfPivotChart control properties using Serialize method by passing the Stream.Please refer the below code snippet.

{% tabs %}

{% highlight C# %}

 var folder = ApplicationData.Current.LocalFolder;
 var storageFile = await folder.CreateFileAsync("PivotChart.xml", CreationCollisionOption.ReplaceExisting);
 var stream = await storageFile.OpenStreamForWriteAsync();
 this.PivotChart.Serialize(stream);

{% endhighlight %}

{% highlight vb %}

Dim folder As var = ApplicationData.Current.LocalFolder
Dim storageFile As var = folder.CreateFileAsync("PivotChart.xml", CreationCollisionOption.ReplaceExisting)
Dim stream As var = storageFile.OpenStreamForWriteAsync
Me.PivotChart.Serialize(stream)

{% endhighlight %}

{% endtabs %}

### Serialize using FileSavePicker 

It Allows the user to save the properties and control settings of the SfPivotChart control to the desired location in *.xml format using Serialize method.Please refer the below code snippet.

{% tabs %}

{% highlight C# %}

this.PivotChart.Serialize();

{% endhighlight %}

{% highlight vb %}

Me.PivotChart.Serialize()

{% endhighlight %}

{% endtabs %}

### Serialize as String Format

It allows the user to save the properties and control settings of the SfPivotChart control into a XML String format using the SerializeToXml method.Please refer the below code snippet.

{% tabs %}

{% highlight C# %}

this.PivotChart.SerializeToXml();

{% endhighlight %}

{% highlight vb %}

Me.PivotChart.SerializeToXml()

{% endhighlight %}

{% endtabs %}

### Serialize using Storage File 

It allows the user to save the SfPivotChart control properties using Serialize method by passing the storage file.Please refer the below code snippet.

{% tabs %}

{% highlight C# %}

var folder = ApplicationData.Current.LocalFolder;         
var storageFile = await folder.CreateFileAsync("PivotChart.xml", CreationCollisionOption.ReplaceExisting);
this.PivotChart.Serialize(storageFile);

{% endhighlight %}

{% highlight vb %}

Dim folder As var = ApplicationData.Current.LocalFolder
Dim storageFile As var = folder.CreateFileAsync("PivotChart.xml", CreationCollisionOption.ReplaceExisting)
Me.PivotChart.Serialize(storageFile)

{% endhighlight %}

{% endtabs %}

## Deserialization

It allows the user to deserialize the SfPivotChart setting by using Deserialize method which reconstructs the SfPivotChart based on the setting in the stored XML file.The Deserialization can be done using any one of the below formats.

### Deserialize using Stream 

It allows the user to deserialize the SfPivotChart control properties using Deserialize method by passing the Stream.Please refer the below code snippet.

{% tabs %}

{% highlight C# %}

var folder = ApplicationData.Current.LocalFolder;
var storageFile = await folder.GetFileAsync("PivotChart.xml");
var stream = await storageFile.OpenStreamForReadAsync();
this.PivotChart.Deserialize(stream);

{% endhighlight %}

{% highlight vb %}

Dim folder As var = ApplicationData.Current.LocalFolder
Dim storageFile As var = folder.GetFileAsync("PivotChart.xml")
Dim stream As var = storageFile.OpenStreamForReadAsync
Me.PivotChart.Deserialize(stream)

{% endhighlight %}

{% endtabs %}

### Deserialize using FileSavePicker 

It Allows the user to deserialize the properties and control settings of the SfPivotChart control from the specified *.xml file using the Deserialize method.Please refer the below code snippet.

{% tabs %}

{% highlight C# %}

this.PivotChart.Deserialize();

{% endhighlight %}

{% highlight vb %}

Me.PivotChart.Deserialize()

{% endhighlight %}

{% endtabs %}

### Deserialize as String Format

It allows the user to deserialize the properties and control settings of the SfPivotChart control using the Deserialize method by passing the XML string.
{% tabs %}

{% highlight C# %}

this.PivotChart.Deserialize(this.PivotChart.SerializeToXml());

{% endhighlight %}

{% highlight vb %}

Me.PivotChart.Deserialize(Me.PivotChart.SerializeToXml())

{% endhighlight %}

{% endtabs %}

### Deserialize using Storage File 

It allows the user to deserialize the SfPivotChart control properties using Deserialize method by passing the storage file.Please refer the below code snippet.

{% tabs %}

{% highlight C# %}

var folder = ApplicationData.Current.LocalFolder;
var storageFile = await folder.GetFileAsync("PivotChart.xml");
this.PivotChart.Deserialize(storageFile);

{% endhighlight %}

{% highlight vb %}

Dim folder As var = ApplicationData.Current.LocalFolder
Dim storageFile As var = folder.GetFileAsync("PivotChart.xml")
Me.PivotChart.Deserialize(storageFile)

{% endhighlight %}

{% endtabs %}

![](Serialization_images/Serialized-PivotChart.png)

A demo sample is available at the following location.

{system drive}:\User3s\&lt;User Name&gt;\AppData\Local\Syncfusion\EssentialStudio\&lt;Version Number&gt;\Samples\UWP\SampleBrowser\PivotChart\PivotChart\View\Serialization.xaml