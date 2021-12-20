---
layout: post
title: How to clear all annotations programmatically | Syncfusion
description: Learn here about how to clear all the annotations (Text, Shapes, Paths, Custom views) alone added in the image editor.
platform: uwp
control: SfImageEditor
documentation : ug
---

# Clear all annotations (Text, Shapes, Paths, etc) from Image Editor

By invoking the [`ClearAnnotations`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.ImageEditor.SfImageEditor.html#Syncfusion_UI_Xaml_ImageEditor_SfImageEditor_ClearAnnotations) method of SfImageEditor, you can clear all the annotations (Text, Shapes, Path, and CustomView) added in the image editor without resetting the other edits (Rotation, Flip, Crop, Effects, etc).

The following code sample demonstrates this.

{% highlight xaml %}

<Grid>
    <Grid.RowDefinitions>
        <RowDefinition Height="*" />
        <RowDefinition Height="Auto" />
    </Grid.RowDefinitions>

    <imageEditor:SfImageEditor x:Name="ImageEditor"
                               ImageSource="Assets/Buldingimage.jpeg"/>

    <StackPanel Grid.Row="1"
                Orientation="Horizontal">
        <Button x:Name="clearAnnotations"
                Width="500"
                Content="Clear Annotations"
                Click="clearAnnotations_Click" />
    </StackPanel>
</Grid>

{% endhighlight %}

{% highlight c# %}

public MainPage()
{
    this.InitializeComponent();
    this.ImageEditor.ToolbarSettings.ToolbarItemSelected += this.ToolbarSettings_ToolbarItemSelected;
    this.ImageEditor.ToolbarSettings.ToolbarItems.Add(new FooterToolbarItem()
    {
        Text = "Custom View"
    });
}

private void clearAnnotations_Click(object sender, RoutedEventArgs e)
{
    this.ImageEditor.ClearAnnotations();
}

private void ToolbarSettings_ToolbarItemSelected(object sender, ToolbarItemSelectedEventArgs e)
{
    if (e.ToolbarItem.Text == "Custom View")
    {
        Image customImage = new Image() { Height = 100, Width = 100 };
        customImage.Source = new BitmapImage(new Uri("ms-appx:///Assets/Buldingimage.jpeg"));
        this.ImageEditor.AddCustomView(customImage, new CustomViewSettings());
    }
}

{% endhighlight %}

![ClearAnnotations support in UWP ImageEditor](images/ClearAnnotations.gif)