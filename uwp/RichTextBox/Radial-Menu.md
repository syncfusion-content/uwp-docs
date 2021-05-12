---
title: Radial Menu in UWP RichTextBox control | Syncfusion
description: Learn here all about Radial Menu support in Syncfusion UWP RichTextBox (SfRichTextBoxAdv) control and more.
platform: uwp
control: SfRichTextBoxAdv
documentation: ug
keywords: radial-menu
---
# Radial Menu in UWP RichTextBox (SfRichTextBoxAdv)

The SfRichTextBoxAdv supports built-in radial menu to provide rich text formatting options such as bold, italic etc.
The following screenshot shows built-in radial menu for SfRichTextBoxAdv control.

![UWP SfRichtextBoxAdv displays radial menu](Radial-Menu_images/Radial-Menu_img1.jpeg)

N> In Windows Phone device, the built-in radial menu is not supported.

## Enable/Disable Radial Menu

In SfRichTextBoxAdv, the built-in radial menu is enabled by default. It is possible to enable/disable the built-in radial menu. The following code example demonstrates how to disable the built-in radial menu in SfRichTextBoxAdv.
{% tabs %}
{% highlight xaml %}
<RichTextBoxAdv:SfRichTextBoxAdv x:Name="richTextBoxAdv" ManipulationMode="All" EnableRadialMenu="True" xmlns:RichTextBoxAdv="using:Syncfusion.UI.Xaml.RichTextBoxAdv"/>

{% endhighlight %}

{% highlight c# %}
// Initializes a new instance of SfRichTextBoxAdv.
SfRichTextBoxAdv richTextBoxAdv = new SfRichTextBoxAdv();
richTextBoxAdv.ManipulationMode = ManipulationModes.All;

//Disables the built-in radial menu in RichTextBoxAdv.
richTextBoxAdv.EnableRadialMenu = false;
{% endhighlight %}

{% endtabs %}

## Customizing Radial Menu Appearance

You can customize the appearance of built-in radial menu as per your requirement. This can be done by defining the custom styles for Radial menu under the resources of SfRichTextBoxAdv, which will override its default style.
The following code example demonstrates how to customize the appearance of navigation button, rim, radial slider and radial pointer in the built-in radial menu.
{% tabs %}
{% highlight xaml %}
<RichTextBoxAdv:SfRichTextBoxAdv x:Name="richTextBox" ManipulationMode="All" AcceptsTab="True" xmlns:RichTextBoxAdv="using:Syncfusion.UI.Xaml.RichTextBoxAdv">
  <!-- Specify resources for this instance -->
  <RichTextBoxAdv:SfRichTextBoxAdv.Resources>
  
    <!-- Custom style for Radial Menu -->
    <Style TargetType="radialMenu:SfRadialMenu">
      <Setter Property="RimBackground" Value="#EFEFEF"/>
      <Setter Property="RimActiveBrush" Value="#0071BC"/>
      <Setter Property="NavigationButtonStyle" Value="{StaticResource RTERadialMenuNavigationButtonStyle}"/>
    </Style>
    
    <!-- Custom Style for Radial Pointer -->
    <Style TargetType="radialMenu:RadialPointer" x:Key="RadialPointerStyle">
      <Setter Property="Height" Value="2"/>
      <Setter Property="IsTabStop" Value="False"/>
      <Setter Property="Template">
        <Setter.Value>
          <ControlTemplate TargetType="radialMenu:RadialPointer">
            <Border  Background="#0071BC"/>
          </ControlTemplate>
        </Setter.Value>
      </Setter>
    </Style>
    
    <!-- Custom Style for Radial Slider -->
    <Style TargetType="radialMenu:SfRadialSlider">
      <Setter Property="Foreground" Value="#0071BC"/>
      <Setter Property="InnerRimFill" Value="#0071BC"/>
      <Setter Property="OuterRimStroke" Value="#0071BC"/>
      <Setter Property="PointerStyle" Value="{StaticResource RadialPointerStyle}"/>
    </Style>
    
    <!-- Custom Style for Navigation Button -->
    <Style x:Key="RTERadialMenuNavigationButtonStyle" TargetType="Button">
      <Setter Property="FontFamily" Value="Segoe UI Symbol"/>
      <Setter Property="BorderBrush" Value="#0071BC"/>
      <Setter Property="Template">
        <Setter.Value>
          <ControlTemplate TargetType="Button">
            <Grid Background="Transparent" Margin="-5">
              <VisualStateManager.VisualStateGroups>
                <VisualStateGroup x:Name="CommonStates">
                  <VisualState x:Name="Normal"/>
                  <VisualState x:Name="PointerOver">
                    <Storyboard>
                      <ObjectAnimationUsingKeyFrames Storyboard.TargetProperty="Fill" Storyboard.TargetName="BackgroundEllipse">
                        <DiscreteObjectKeyFrame KeyTime="0" Value="LightGray"/>
                      </ObjectAnimationUsingKeyFrames>
                    </Storyboard>
                  </VisualState>
                </VisualStateGroup>
              </VisualStateManager.VisualStateGroups>
              <Ellipse Fill="White" x:Name="BackgroundEllipse" />
              <Ellipse Stroke="{TemplateBinding BorderBrush}" StrokeThickness="2"  Fill="Transparent"/>
              <ContentPresenter HorizontalAlignment="Center" VerticalAlignment="Center"/>
            </Grid>
          </ControlTemplate>
        </Setter.Value>
      </Setter>
    </Style>
  </RichTextBoxAdv:SfRichTextBoxAdv.Resources>
</RichTextBoxAdv:SfRichTextBoxAdv>


{% endhighlight %}

{% endtabs %}
The following screenshot shows the radial menu with customized style.
![UWP SfRichTextBoxAdv displays applied different styles in radial menu](Radial-Menu_images/Radial-Menu_img2.jpeg)

The sample to demonstrate customizing the style of built-in radial menu, can be downloaded from the following link.
[Sample](http://www.syncfusion.com/downloads/support/directtrac/general/ze/RadialMenuCustomization-1397995223# "Click here to download the sample")
