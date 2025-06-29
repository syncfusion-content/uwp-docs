---
title: Getting Started with UWP RichTextBox control | Syncfusion
description: Learn here about getting started with Syncfusion UWP RichTextBox (SfRichTextBoxAdv) control, its elements and more.
platform: uwp
control: SfRichTextBoxAdv
documentation: ug
keywords: getting-started
---
# Getting Started with UWP RichTextBox (SfRichTextBoxAdv)

SfRichTextBoxAdv is a control that allows you to view and edit rich text contents including table, text, images and hyperlinks. This section describes how to get started with SfRichTextBoxAdv control.

## Assembly Reference

You can find SfRichTextBoxAdv control from the following assembly under the namespace Syncfusion.UI.Xaml.RichTextBoxAdv

* Syncfusion.SfRichTextBoxAdv.UWP


The following assembly references are required to deploy SfRichTextBoxAdv control in your application.

* Syncfusion.DocIO.UWP

* Syncfusion.SfRadialMenu.UWP

* Syncfusion.SfShared.UWP


N> 1. Starting with v16.2.0.41 (2018 Vol 2), if you reference Syncfusion&reg; assemblies from trial setup or from the NuGet feed, you also have to add "Syncfusion.Licensing" assembly reference and include a license key in your projects. Please refer to this [link](https://help.syncfusion.com/common/essential-studio/licensing/overview) to know about registering Syncfusion license&reg; key in your UWP application to use our components.
N> 2. Starting from version v20.3.0.52, we internally disposed all the resources used by SfRichTextBoxAdv instance inside Unloaded event. This change is added to automatically release the memory utilized by SfRichTextBoxAdv instance when it is unloaded. This behavior change may introduce a break if you remove the SfRichTextBoxAdv instance from its parent container and add it to the same or another parent container in your application. In case you used such logic in your application, then kindly add below code before removing the SfRichTextBoxAdv instance from its parent container.

<table>
  <thead>
    <tr>
      <th>Old code</th>
      <th>New code</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>
        <pre><code>
//Remove the control from the parent Grid
grid.Children.Remove(richTextBoxAdv);

//Add the SfRichTextBoxAdv control to the Grid
grid.Children.Add(richTextBoxAdv);
      </code></pre>
    </td>
    <td>
      <pre><code>
//Create a file stream
MemoryStream memoryStream = new MemoryStream();

//Save the document to the stream 
richTextBoxAdv.Save(memoryStream, FormatType.Docx);

//Remove the control from the parent Grid
grid.Children.Remove(richTextBoxAdv);

//Create new instance of SfRichTextBoxAdv
richTextBoxAdv = new SfRichTextBoxAdv();

//Add the SfRichTextBoxAdv control to the Grid
grid.Children.Add(richTextBoxAdv);

//Load the saved stream into SfRichTextBoxAdv
richTextBoxAdv.Load(memoryStream, FormatType.Docx);
      </code></pre>
    </td>
  </tr>
  </tbody>
</table>

## Adding SfRichTextBoxAdv to an application


After adding the aforementioned assembly references to your application, you can add SfRichTextBoxAdv as any normal control.
You can either drag the SfRichTextBoxAdv control from the toolbox window to the Design view or directly define the control in XAML view.
![Getting-Started_img1](Getting-Started_images/Getting-Started_img1.jpeg)

{% tabs %}
{% highlight xaml %}
<RichTextBoxAdv:SfRichTextBoxAdv x:Name="richTextBoxAdv" ManipulationMode="All" xmlns:RichTextBoxAdv="using:Syncfusion.UI.Xaml.RichTextBoxAdv"/>

{% endhighlight %}

{% highlight c# %}
// Initializes a new instance of SfRichTextBoxAdv.
SfRichTextBoxAdv richTextBoxAdv = new SfRichTextBoxAdv();
richTextBoxAdv.ManipulationMode = ManipulationModes.All;

{% endhighlight %}

{% endtabs %}

## Using SfRichTextBoxAdv as a standard RichTextBox

This section discusses about how to use the SfRichTextBoxAdv control as a standard RichTextBox control with rich text formatting options.
{% tabs %}
{% highlight xaml %}
<Page>

    <Page.Resources>
        <RichTextBoxAdv:UnderlineToggleConverter x:Key="UnderlineToggleConverter"/>
        <RichTextBoxAdv:LeftAlignmentToggleConverter x:Key="LeftAlignmentToggleConverter"/>
        <RichTextBoxAdv:CenterAlignmentToggleConverter x:Key="CenterAlignmentToggleConverter"/>
        <RichTextBoxAdv:RightAlignmentToggleConverter x:Key="RightAlignmentToggleConverter"/>
        <RichTextBoxAdv:JustifyAlignmentToggleConverter x:Key="JustifyAlignmentToggleConverter"/>
        <Style TargetType="Button">
            <Setter Property="Background" Value="Transparent" />
            <Setter Property="Margin" Value="12 4"/>
        </Style>
        <Style TargetType="ToggleButton">
            <Setter Property="Background" Value="Transparent" />
            <Setter Property="Margin" Value="12 4"/>
        </Style>
    </Page.Resources>

    <Grid Background="#F1F1F1">
        <Grid.RowDefinitions>
            <RowDefinition Height="Auto"/>
            <RowDefinition Height="*"/>
        </Grid.RowDefinitions>
        <Grid>
            <!-- Defines the data context as RichTextBoxAdv -->
            <StackPanel Orientation="Horizontal" DataContext="{Binding ElementName=richTextBoxAdv}">
                <!-- UI option to perform Undo/Redo using command binding -->
                <StackPanel Orientation="Horizontal">
                    <Button Command="{Binding UndoCommand}" IsTabStop="False">
                        <Image Source="/Images/Undo.png" Height="40" Width="40" />
                    </Button>
                    <Button Command="{Binding RedoCommand}" IsTabStop="False">
                        <Image Source="/Images/Redo.png" Height="40" Width="40" />
                    </Button>
                </StackPanel>
                <!-- UI option to perform Clipboard operations using command binding -->
                <Border Width="2" Height="46" Background="#1F1F1F"/>
                <StackPanel Orientation="Horizontal">
                    <Button Command="{Binding CutCommand}" IsTabStop="False">
                        <Image Source="/Images/Cut.png" Height="40" Width="40" />
                    </Button>
                    <Button Command="{Binding CopyCommand}" IsTabStop="False">
                        <Image Source="/Images/Copy.png" Height="40" Width="40" />
                    </Button>
                    <Button Command="{Binding PasteCommand}" IsTabStop="False">
                        <Image Source="/Images/Paste.png" Height="40" Width="40" />
                    </Button>
                </StackPanel>
                <!-- UI option to apply character formatting using property binding -->
                <Border Width="2" Height="46" Background="#1F1F1F"/>
                <StackPanel Orientation="Horizontal">
                    <ToggleButton IsChecked="{Binding Selection.CharacterFormat.Bold}" IsTabStop="False">
                        <Image Source="/Images/Bold.png" Height="40" Width="40" />
                    </ToggleButton>
                    <ToggleButton IsChecked="{Binding Selection.CharacterFormat.Italic}" IsTabStop="False">
                        <Image Source="/Images/Italic.png" Height="40" Width="40" />
                    </ToggleButton>
                    <ToggleButton IsChecked="{Binding Selection.CharacterFormat.Underline, Converter={StaticResource UnderlineToggleConverter}}" IsTabStop="False">
                        <Image Source="/Images/Underline.png" Height="40" Width="40" />
                    </ToggleButton>
                </StackPanel>
                <Border Width="2" Height="46" Background="#1F1F1F"/>
                <!-- UI option to apply paragraph formatting using property binding -->
                <StackPanel Orientation="Horizontal">
                    <ToggleButton IsChecked="{Binding Selection.ParagraphFormat.TextAlignment, Converter={StaticResource LeftAlignmentToggleConverter}}" IsTabStop="False">
                        <Image Source="/Images/Left.png" Height="40" Width="40" />
                    </ToggleButton>
                    <ToggleButton IsChecked="{Binding Selection.ParagraphFormat.TextAlignment, Converter={StaticResource CenterAlignmentToggleConverter}}" IsTabStop="False">
                        <Image Source="/Images/Center.png" Height="40" Width="40" />
                    </ToggleButton>
                    <ToggleButton IsChecked="{Binding Selection.ParagraphFormat.TextAlignment, Converter={StaticResource RightAlignmentToggleConverter}}" IsTabStop="False">
                        <Image Source="/Images/Right.png" Height="40" Width="40" />
                    </ToggleButton>
                    <ToggleButton IsChecked="{Binding Selection.ParagraphFormat.TextAlignment, Converter={StaticResource JustifyAlignmentToggleConverter}}" IsTabStop="False">
                        <Image Source="/Images/Justify.png" Height="40" Width="40" />
                    </ToggleButton>
                </StackPanel>
            </StackPanel>
        </Grid>
        <RichTextBoxAdv:SfRichTextBoxAdv x:Name="richTextBoxAdv" Grid.Row="1" ManipulationMode="All" />
    </Grid>
</Page>



{% endhighlight %}

{% endtabs %}
