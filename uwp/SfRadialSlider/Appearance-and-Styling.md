---
layout: post
title: Appearance and Styling of SfRadialSlider control for UWP
description: Appearance and Styling of SfRadialSlider control for UWP
platform: uwp
control: SfRadial Slider 
documentation: ug
---

# Appearance and Styling 

## Inner Rim 

Inner Rim term denotes the circle in the center of SfRadialSlider.  Following properties can be used to customize the Inner Rim. 

### Inner Rim Radius Factor

InnerRimRadiusFactor property decides the radius of Inner Rim from the total radius available to render the Radial Slider.

### Inner Rim Stroke

InnerRimStroke property can be used to set the stroke color of the Inner Rim. 

### Inner Rim Stroke Thickness

InnerRimStrokeThickness property can be used to set the thickness of the Inner Rim.

### Inner Rim Fill

InnerRimFill property can be used the set the fill color of the Inner Rim. 

{% highlight xaml %}

  <syncfusion:SfRadialSlider

InnerRimFill="LightGray"

            InnerRimRadiusFactor="0.25"

            InnerRimStroke="LightSkyBlue"

            InnerRimStrokeThickness="4" />

{% endhighlight %}

![](Concepts--and-Features_images/Concepts--and-Features_img6.png)

## Outer Rim 

Outer Rim term denotes circular track (outer circle) of SfRadialSlider.  Following properties can be used to customize the Inner Rim

### Outer Rim Radius Factor

OuterRimRadiusFactor property decides the radius of Outer Rim from the total radius available to render the SfRadialSlider. 

### Outer Rim Stroke 

OuterRimStroke property can be used to set the stroke color of the Outer Rim. 

### Outer Rim Stroke Thickness 

OuterRimStrokeThickness property can be used to set the thickness of the Outer Rim. 

### Background

Background property can be used to fill the Outer Rim.

{% highlight xaml %}

<syncfusion:SfRadialSlider

            Background="LightGray"

            OuterRimRadiusFactor="0.8"

            OuterRimStroke="LightSkyBlue"

            OuterRimStrokeThickness="4" />

{% endhighlight %}

![](Concepts--and-Features_images/Concepts--and-Features_img7.png)

## Ticks

Ticks displayed along the circular path can be customized using the following properties. 

### Tick Template

Ticks can be customized using the TickTemplate property. 

{% highlight xaml %}

<syncfusion:SfRadialSlider>

            <syncfusion:SfRadialSlider.TickTemplate>

                <DataTemplate>

                    <Border Background="Red"></Border>

                </DataTemplate>

            </syncfusion:SfRadialSlider.TickTemplate>

 </syncfusion:SfRadialSlider>

{% endhighlight %}

![](Concepts--and-Features_images/Concepts--and-Features_img8.png)

### Tick Radius Factor

TickRadiusFactor property decides the radius of the ticks from the total radius available to render the SfRadialSlider. 

{% highlight xaml %}

<syncfusion:SfRadialSlider  TickRadiusFactor="0.75"  />

{% endhighlight %}

![](Concepts--and-Features_images/Concepts--and-Features_img9.png)

### Tick Visibility

Visibility of ticks can be controlled by TickVisibility property. 

{% highlight xaml %}

<syncfusion:SfRadialSlider TickVisibility="Collapsed" />

{% endhighlight %}

![](Concepts--and-Features_images/Concepts--and-Features_img10.png)

## Labels

Labels displayed along the circular path in the Radial slider can be customized by the following properties. 

### Label Template

The LabelTemplate property can be used to customize the label object. 

{% highlight xaml %}

<syncfusion:SfRadialSlider>

<syncfusion:SfRadialSlider.LabelTemplate>

           <DataTemplate>

               <TextBlock Text="{Binding}" Foreground="DodgerBlue"></TextBlock>

           </DataTemplate>

       </syncfusion:SfRadialSlider.LabelTemplate>

</syncfusion:SfRadialSlider>

{% endhighlight %}

![](Concepts--and-Features_images/Concepts--and-Features_img11.png)

### Label Radius Factor

LabelRadiusFactor property decides the radius of the labels from the total radius available to render the SfRadialSlider. 

![](Concepts--and-Features_images/Concepts--and-Features_img12.png)

{% highlight xaml %}

<syncfusion:SfRadialSlider LabelRadiusFactor="0.7" />

{% endhighlight %}

### Label Visibility

Visibility of ticks can be controlled by LabelVisibility property. 

{% highlight xaml %}

<syncfusion:SfRadialSlider  LabelVisibility="Collapsed" />

{% endhighlight %}

![](Concepts--and-Features_images/Concepts--and-Features_img13.png)

## Pointer
The Pointer that is used for the select the value by dragging in circular track can be customized with the following properties. 

### Pointer Radius Factor

The PointerRadiusFactor property decides the radius of the Pointer from the total radius available to render the SfRadialSlider. 

{% highlight xaml %}

<syncfusion:SfRadialSlider PointerRadiusFactor="0.5" />

{% endhighlight %}

![](Concepts--and-Features_images/Concepts--and-Features_img14.png)

### Pointer Style

Style of the Pointer can be customized using the PointerStyle property. 

{% highlight xaml %}

<syncfusion:SfRadialSlider>

<syncfusion:SfRadialSlider.PointerStyle>

                <Style TargetType="syncfusion:RadialPointer" >

                    <Setter Property="Height" Value="2"/>

                    <Setter Property="Template">

                        <Setter.Value>

                            <ControlTemplate TargetType="syncfusion:RadialPointer">

                                <Border  Background="Red"/>

                            </ControlTemplate>

                        </Setter.Value>

                    </Setter>

                </Style>

            </syncfusion:SfRadialSlider.PointerStyle>

</syncfusion:SfRadialSlider>

{% endhighlight %}

![](Concepts--and-Features_images/Concepts--and-Features_img15.png)

### Preview Pointer Style

The Preview Pointer that appears when hovering over the SfRadialSlider can be customized using the PreviewPointerStyle property. 

{% highlight xaml %}

<syncfusion:SfRadialSlider

            Minimum="0" 

            Maximum="100"  >

            <syncfusion:SfRadialSlider.PreviewPointerStyle>

                <Style TargetType="syncfusion:RadialPreviewPointer" >

                    <Setter Property="Height" Value="2"/>

                    <Setter Property="Template">

                        <Setter.Value>

     <ControlTemplate TargetType="syncfusion:RadialPreviewPointer">

                                <Border Opacity="0.2"  Background="Red"/>

                          </ControlTemplate>

                        </Setter.Value>

                    </Setter>

                </Style>

            </syncfusion:SfRadialSlider.PreviewPointerStyle>

</syncfusion:SfRadialSlider>

{% endhighlight %}

![](Concepts--and-Features_images/Concepts--and-Features_img16.png)





