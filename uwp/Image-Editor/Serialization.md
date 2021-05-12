---
layout : post
title: Serialization in UWP Image Editor control | Syncfusion
description: Learn here all about Serialization support in Syncfusion UWP Image Editor (SfImageEditor) control and more.
platform : UWP
control : ImageEditor
documentation : ug
---

# Serialization in UWP Image Editor (SfImageEditor)
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

You can also Serialize and Deserialize the current edited image.

{% tabs %}

{% highlight xaml %}

    <Grid>
        <Grid.RowDefinitions>
            <RowDefinition Height="0.1*"/>
            <RowDefinition Height="0.9*"/>
        </Grid.RowDefinitions>
        <Grid.ColumnDefinitions>
            <ColumnDefinition Width="*"/>
            <ColumnDefinition Width="*"/>
        </Grid.ColumnDefinitions>
        <Button Content="Serialization" Grid.Row="0" Grid.Column="0" x:Name="serialize" Click="Serialize_Click" HorizontalAlignment="Center"/>
        <Button Content="Deserialization" Grid.Row="0" Grid.Column="1" x:Name="deserialize" Click="Deserialize_Click" HorizontalAlignment="Center"/>
        <syncfusion:SfImageEditor Grid.Row="1" Grid.ColumnSpan="2" x:Name="editor" ImageSource="Assets/Bulding.jpeg"/>
    </Grid>

{% endhighlight %}

{% highlight C# %}

        private Stream stream;

        private void Serialize_Click(object sender, RoutedEventArgs e)
        {
            stream = editor.SaveEdits();
            editor.Reset();
        }

        private void Deserialize_Click(object sender, RoutedEventArgs e)
        {
            editor.LoadEdits(stream);
        }        

{% endhighlight %}

{% endtabs %}

You can find the [sample](http://www.syncfusion.com/downloads/support/directtrac/general/ze/ImageEditor_Serilaization238220795.zip) for serialize and deserialize the current edited image.

![SfImageEditor](SerializationImages/serialization.png)



