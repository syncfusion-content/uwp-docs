---
layout : post
title : Serialization in Syncfusion SfImageEditor control in UWP
description : Learn how to serilaize and deserialize shapes in ImageEditor for UWP
platform : UWP
control : ImageEditor
documentation : ug
---

# Serialization And Deserialization
 ImageEditor provides support to serialize and deserialize the shapes(Circle, Arrow, Rectangle), free hand drawing, Text and Toolbar settings. Save the current state of the image editor and Load it back when its needed.

## Serialization
  SaveEdits() method used to serialize the current edits of shapes. Serialized object will be return in the form of JSON stream.

{% tabs %}

{% highlight C# %}
    
	 SfImageEditor editor;
        public MainPage()
        {
            this.InitializeComponent();
            Grid grid = new Grid();
            Button saveEdits = new Button();
            saveEdits.Content = "Serialization";
            saveEdits.Click += SaveEdits_Click;
            editor = new SfImageEditor();
            grid.RowDefinitions.Add(new RowDefinition() { Height =GridLength.Auto });
            grid.RowDefinitions.Add(new RowDefinition());
            Grid.SetRow(saveEdits, 0);
            Grid.SetRow(editor, 1);
            grid.Children.Add(saveEdits);
            grid.Children.Add(editor);
            this.Content = grid;
        }

        private void SaveEdits_Click(object sender, RoutedEventArgs e)
        {
            Stream stream = editor.SaveEdits();
        }
    

{% endhighlight %}

{% endtabs %}

  you can save stream into .txt format file.if you saved as .txt format file to deserialize the shapes then set as Embedded resource in project.
  
  Please find sample text file shown below
  
  [Chart.txt](http://www.syncfusion.com/downloads/support/directtrac/general/txt/Chart677841499.txt)
       

## Deserialization
LoadEdits() method used to deserialize the shapes.

{% tabs %}

{% highlight C# %}
       
	  SfImageEditor editor = new SfImageEditor();
            var assembly = typeof(App).GetTypeInfo().Assembly;
            Stream stream = new MemoryStream();
            var fileName = "namespace_name.Chart.txt";
            stream = assembly.GetManifestResourceStream(fileName);
            if (stream != null)
                editor.LoadEdits(stream);
            this.Content = editor;

{% endhighlight %}

{% endtabs %}


![SfImageEditor](SerializationImages/serialization.png)



