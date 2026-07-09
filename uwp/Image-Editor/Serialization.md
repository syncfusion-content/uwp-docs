---
layout: post
title: Serialization in UWP Image Editor control | Syncfusion
description: Learn here all about Serialization support in Syncfusion UWP Image Editor (SfImageEditor) control and more.
platform: UWP
control: ImageEditor
documentation: ug
---

The following namespaces are required for using serialization in the SfImageEditor control:

* `Syncfusion.UI.Xaml.ImageEditor`
* `Windows.UI.Xaml`
* `Windows.UI.Xaml.Controls`
* `System.IO`
* `System.Reflection`

# Serialization in UWP Image Editor (SfImageEditor)

The SfImageEditor provides support to serialize and deserialize the shapes (Circle, Arrow, Rectangle), free-hand drawing, text, and toolbar settings. Save the current state of the image editor and load it back when it is needed.

## Serialization

The `SaveEdits()` method is used to serialize the current edits of shapes. The serialized object is returned in the form of a JSON stream.

{% tabs %}

{% highlight C# %}

    using Syncfusion.UI.Xaml.ImageEditor;
    using Windows.UI.Xaml;
    using Windows.UI.Xaml.Controls;
    using System.IO;

    SfImageEditor editor;
    public MainPage()
    {
        this.InitializeComponent();
        Grid grid = new Grid();
        Button saveEdits = new Button();
        saveEdits.Content = "Serialization";
        saveEdits.Click += SaveEdits_Click;
        editor = new SfImageEditor();
        grid.RowDefinitions.Add(new RowDefinition() { Height = GridLength.Auto });
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

You can save the stream into a .txt file. If you save it as a .txt file to deserialize the shapes, then set it as an embedded resource in the project.

Please find the sample text file shown below:

[Chart.txt](http://www.syncfusion.com/downloads/support/directtrac/general/txt/Chart677841499.txt)

## Deserialization

The `LoadEdits()` method is used to deserialize the shapes.

{% tabs %}

{% highlight C# %}

    using Syncfusion.UI.Xaml.ImageEditor;
    using System.IO;
    using System.Reflection;

    SfImageEditor editor = new SfImageEditor();
    var assembly = typeof(App).GetTypeInfo().Assembly;
    var fileName = "namespace_name.Chart.txt";
    Stream stream = assembly.GetManifestResourceStream(fileName);
    if (stream != null)
        editor.LoadEdits(stream);
    this.Content = editor;

{% endhighlight %}

{% endtabs %}

You can also serialize and deserialize the currently edited image.

{% tabs %}

{% highlight XAML %}

    xmlns:syncfusion="using:Syncfusion.UI.Xaml.ImageEditor"

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

    using System.IO;

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

You can find the [sample](http://www.syncfusion.com/downloads/support/directtrac/general/ze/ImageEditor_Serilaization238220795.zip) for serializing and deserializing the currently edited image.

![SfImageEditor](SerializationImages/serialization.png)



