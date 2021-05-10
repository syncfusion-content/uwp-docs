---
layout: post
title: Serialization and Deserialization in UWP Pivot Grid control | Syncfusion
description: Learn here all about Serialization and Deserialization support in Syncfusion UWP Pivot Grid (SfPivotGrid) control and more.
platform: UWP
control: SfPivotGrid
documentation: ug
---

# Serialization and Deserialization in UWP Pivot Grid (SfPivotGrid)

This support allows you to serialize and deserialize the settings of SfPivotGrid control using [DataContractSerializer](https://msdn.microsoft.com/en-in/library/system.runtime.serialization.datacontractserializer.aspx).

## Serialization

Serialization allows you to save the settings of SfPivotGrid by using the `Serialize` method of the SfPivotGrid. It exports the current SfPivotGrid control settings to an XML file and it can be done with the help of one of the following methods.

### Serialize using FileSavePicker

It allows you to save the settings of SfPivotGrid control to the desired location in _*.xml_ format by using the `Serialize` method. Refer to the following code snippet.

{% tabs %}

{% highlight C# %}

this.pivotGrid.Serialize();

{% endhighlight %}

{% highlight vb %}

Me.pivotGrid.Serialize()

{% endhighlight %}

{% endtabs %}

Now, the SfPivotGrid control will be serialized in XML file as follows.

![Serialized-PivotGrid](Serialization-and-Deserialization_images/Serialized-PivotGrid.png)

### Serialize using stream

It allows you to save the SfPivotGrid control's settings with the help of `Serialize` method by passing the stream as parameter.

{% tabs %}

{% highlight C# %}

var folder = ApplicationData.Current.LocalFolder;
var storageFile = await folder.CreateFileAsync("PivotGrid.xml", CreationCollisionOption.ReplaceExisting);
var stream = await storageFile.OpenStreamForWriteAsync();
this.pivotGrid.Serialize(stream);

{% endhighlight %}

{% highlight vb %}

Dim folder As var = ApplicationData.Current.LocalFolder
Dim storageFile As var = folder.CreateFileAsync("PivotGrid.xml", CreationCollisionOption.ReplaceExisting)
Dim stream As var = storageFile.OpenStreamForWriteAsync
Me.pivotGrid.Serialize(stream)

{% endhighlight %}

{% endtabs %}

### Serialize using storage file

It allows you to save the SfPivotGrid control's settings with the help of `Serialize` method by passing the storage file as parameter.

{% tabs %}

{% highlight C# %}

var folder = ApplicationData.Current.LocalFolder;
var storageFile = await folder.CreateFileAsync("PivotGrid.xml", CreationCollisionOption.ReplaceExisting);
this.pivotGrid.Serialize(storageFile);

{% endhighlight %}

{% highlight vb %}

Dim folder As var = ApplicationData.Current.LocalFolder
Dim storageFile As var = folder.CreateFileAsync("PivotGrid.xml", CreationCollisionOption.ReplaceExisting)
Me.pivotGrid.Serialize(storageFile)

{% endhighlight %}

{% endtabs %}

### Serialize to XML string

It allows you to save the settings of SfPivotGrid control into an XML string using the `SerializeToXml` method.

{% tabs %}

{% highlight C# %}

string serializedPivotGrid = this.pivotGrid.SerializeToXml();

{% endhighlight %}

{% highlight vb %}

Me.pivotGrid.SerializeToXml()

{% endhighlight %}

Private serializedPivotGrid As String = Me.pivotGrid.SerializeToXml()

{% endtabs %}

## Deserialization

Deserialization allows you to load the settings of SfPivotGrid by using the `Deserialize` method of the SfPivotGrid. It reconstructs the SfPivotGrid control based on the settings stored in the XML file and it can be done with the help of one of the following methods.

### Deserialize using FileSavePicker

It allows you to reload the SfPivotGrid control with the settings available in the _*.xml_ file. This can be achieved by using the `Deserialize` method.

{% tabs %}

{% highlight C# %}

this.pivotGrid.Deserialize();

{% endhighlight %}

{% highlight vb %}

Me.pivotGrid.Deserialize()

{% endhighlight %}

{% endtabs %}

### Deserialize using stream

It allows you to reload the SfPivotGrid control with the settings available in the stream. This can be achieved with the help of `Deserialize` method by passing the stream as parameter.

{% tabs %}

{% highlight C# %}

var folder = ApplicationData.Current.LocalFolder;
var storageFile = await folder.GetFileAsync("PivotGrid.xml");
var stream = await storageFile.OpenStreamForReadAsync();
this.pivotGrid.Deserialize(stream);

{% endhighlight %}

{% highlight vb %}

Dim folder As var = ApplicationData.Current.LocalFolder
Dim storageFile As var = folder.GetFileAsync("PivotGrid.xml")
Dim stream As var = storageFile.OpenStreamForReadAsync
Me.pivotGrid.Deserialize(stream)

{% endhighlight %}

{% endtabs %}

### Deserialize using storage file

It allows you to reload the SfPivotGrid control with the settings available in the storage file. This can be achieved with the help of `Deserialize` method by passing the storage file as parameter.

{% tabs %}

{% highlight C# %}

var folder = ApplicationData.Current.LocalFolder;
var storageFile = await folder.GetFileAsync("PivotGrid.xml");
this.pivotGrid.Deserialize(storageFile);

{% endhighlight %}

{% highlight vb %}

Dim folder As var = ApplicationData.Current.LocalFolder
Dim storageFile As var = folder.GetFileAsync("PivotGrid.xml")
Me.pivotGrid.Deserialize(storageFile)

{% endhighlight %}

{% endtabs %}

### Deserialize from XML string

It allows you to reload the SfPivotGrid with the settings available in the XML string. This can be achieved with the help of `Deserialize` method by passing the XML string as parameter.

{% tabs %}

{% highlight C# %}

// string serializedPivotGrid = this.pivotGrid.Serialize();
this.pivotGrid.Deserialize(serializedPivotGrid);

{% endhighlight %}

{% highlight vb %}

' Dim serializedPivotGrid As String = Me.pivotGrid.Serialize()
Me.pivotGrid.Deserialize(serializedPivotGrid)

{% endhighlight %}

{% endtabs %}

A demo sample is available in the following location.

{system drive}:\Users\&lt;User Name&gt;\AppData\Local\Syncfusion\EssentialStudio\&lt;Version Number&gt;\Samples\UWP\SampleBrowser\PivotGrid\PivotGrid\View\Serialization.xaml
