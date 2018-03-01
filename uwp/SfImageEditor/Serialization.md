---
layout : post
title : Serialization in Syncfusion SfImageEditor control in Xamarin.Forms
description : Learn how to serilaize and deserialize shapes in ImageEditor for UWP
platform : UWP
control : ImageEditor
documentation : ug
---

# Serialization And Deserialization:
 ImageEditor provides support to serialize and deserialize the shapes(Circle,Arrow,Rectangle), free hand drawing,Text and Toolbar settings. Save the current state of the image editor and Load it back when its needed.

## Serialization
  To serialize the shapes like circle,arrow,rectangle,text ,freehand drawing and toolbar settings by calling SaveEdits() method.Serialized object will be return in the form of JSON stream.

{% tabs %}

{% highlight C# %}
    
	 SfImageEditor editor = new   SfImageEditor();
	 Stream stream=editor.SaveEdits();
     this.Content = editor;
    
	
{% endhighlight %}

{% endtabs %}

   convert the stream into string and save as .txt format file and set as Embedded resource in UWP.Text file like this
  
  http://www.syncfusion.com/downloads/support/directtrac/general/txt/Chart677841499.txt
       


## Deserialization
   To deserialize serialized objects by calling LoadEdits(stream) method .Deserialize the object by using loaded JSON stream.

{% tabs %}

{% highlight C# %}
       
	  SfImageEditor editor = new SfImageEditor();
            var assembly = typeof(App).GetTypeInfo().Assembly;
            Stream stream = new MemoryStream();
            var fileName = "SerialNativeUWP.Chart.txt";
            stream = assembly.GetManifestResourceStream(fileName);
            if (stream != null)
                editor.LoadEdits(stream);
            this.Content = editor;

{% endhighlight %}

{% endtabs %}


![SfImageEditor](SerializationImages/serialization.png)



