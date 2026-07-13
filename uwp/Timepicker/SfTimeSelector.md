---
layout: post
title: SfTimeSelector in UWP TimePicker control | Syncfusion®
description: Learn here all about SfTimeSelector support in Syncfusion® UWP TimePicker (SfTimePicker) control and more.
platform: uwp
control: SfTimePicker
documentation: ug
---

# SfTimeSelector in UWP TimePicker (SfTimePicker)

The SfTimeSelector control opens inside the popup window.



![Features_img3](Features_images/Features_img3.png)





The visual elements of the time selector can be customized using the SelectorStyle property.



## Header

The Header property defines the top part of the time selector.
{% highlight xaml %}




<syncfusion:SfTimePicker VerticalAlignment="Center"

                       HorizontalAlignment="Center"

                       Width="200">

       <syncfusion:SfTimePicker.SelectorStyle>

                <Style TargetType="syncfusion:SfTimeSelector">

                    <Setter Property="Header" Value="Set your alarm"/>

                </Style>

       </syncfusion:SfTimePicker.SelectorStyle>

</syncfusion:SfTimePicker >

{% endhighlight %}

![Features_img4](Features_images/Features_img4.png)







## HeaderTemplate

The HeaderTemplate property is used to decorate the header.
{% highlight xaml %}




<syncfusion:SfTimePicker VerticalAlignment="Center" 

                               HorizontalAlignment="Center"

                               Width="200">

            <syncfusion:SfTimePicker.SelectorStyle>

                <Style TargetType="syncfusion:SfTimeSelector">

                    <Setter Property="HeaderTemplate">

                        <Setter.Value>

                            <DataTemplate>

                                <StackPanel Orientation="Horizontal">

                                    <TextBlock Text="&#xE170;" 

                                           VerticalAlignment="Top"

                                           Margin="5"

                                           FontSize="22"

                                           FontFamily="Segoe UI Symbol"/>

                                    <TextBlock Text="Set your alarm" 

                                           VerticalAlignment="Top"

                                           Margin="5"

                                           FontSize="22"

                                           />

                                </StackPanel>

                            </DataTemplate>

                        </Setter.Value>

                    </Setter>

                </Style>

            </syncfusion:SfTimePicker.SelectorStyle>        </syncfusion:SfTimePicker>

{% endhighlight %}

![Features_img5](Features_images/Features_img5.png)





## Cell template

The CellTemplate property is used to decorate the selection box with custom visuals. 


N>  The DataContext of Selection box is Syncfusion.UI.Xaml.Primitives.DateTimeWrapper.



## HourCellTemplate

The HourCellTemplate property is used to decorate the hour cell selection box.

{% highlight xaml %}





<syncfusion:SfTimePicker VerticalAlignment="Center"

                               HorizontalAlignment="Center"

                               Width="200">

            <syncfusion:SfTimePicker.SelectorStyle>

                <Style TargetType="syncfusion:SfTimeSelector">

                    <Setter Property="HourCellTemplate">

                        <Setter.Value>

                            <DataTemplate>

                                <Grid>

                                    <TextBlock VerticalAlignment="Top" 

                                               HorizontalAlignment="Right"

                                               Margin="5"

                                               FontSize="22"

                                               FontFamily="Segoe UI Symbol"

                                               Text="&#xE170;"/>

                                    <TextBlock Text="{Binding HourNumber}" 

                                               VerticalAlignment="Bottom" 

                                               Margin="5"

                                               FontSize="22"/>

                                </Grid>

                            </DataTemplate>

                        </Setter.Value>

                    </Setter>

                </Style>

            </syncfusion:SfTimePicker.SelectorStyle>         </syncfusion:SfTimePicker>

{% endhighlight %}

![Features_img7](Features_images/Features_img7.png)





## MinuteCellTemplate

The MinuteCellTemplate property is used to decorate the minute cell selection box.

{% highlight xaml %}

       



       <syncfusion:SfTimePicker VerticalAlignment="Center"

                               HorizontalAlignment="Center"

                               Width="200">

            <syncfusion:SfTimePicker.SelectorStyle>

                <Style TargetType="syncfusion:SfTimeSelector">

                    <Setter Property="MinuteCellTemplate">

                        <Setter.Value>

                            <DataTemplate>

                                <Grid>

                                    <TextBlock VerticalAlignment="Top" 

                                               HorizontalAlignment="Right"

                                               Margin="5"

                                               FontSize="22"

                                               FontFamily="Segoe UI Symbol"

                                               Text="&#xE170;"/>

                                    <TextBlock Text="{Binding MinuteNumber}" 

                                               VerticalAlignment="Bottom" 

                                               Margin="5"

                                               FontSize="22"/>

                                </Grid>

                            </DataTemplate>

                        </Setter.Value>

                    </Setter>

                </Style>

            </syncfusion:SfTimePicker.SelectorStyle>        </syncfusion:SfTimePicker>

{% endhighlight %}

![Features_img8](Features_images/Features_img8.png)





## MeridiemCellTemplate

The MeridiemCellTemplate property is used to decorate the meridiem cell selection box. 
{% highlight xaml %}






<syncfusion:SfTimePicker VerticalAlignment="Center"

                               HorizontalAlignment="Center"

                               Width="200">

            <syncfusion:SfTimePicker.SelectorStyle>

                <Style TargetType="syncfusion:SfTimeSelector">

                    <Setter Property="MeridiemCellTemplate">

                        <Setter.Value>

                            <DataTemplate>

                                <Grid>

                                    <TextBlock VerticalAlignment="Top" 

                                               HorizontalAlignment="Right"

                                               Margin="5"

                                               FontSize="22"

                                               FontFamily="Segoe UI Symbol"

                                               Text="&#xE170;"/>

                                    <TextBlock Text="{Binding AmPmString}" 

                                               VerticalAlignment="Bottom" 

                                               Margin="5"

                                               FontSize="22"/>

                                </Grid>

                            </DataTemplate>

                        </Setter.Value>

                    </Setter>

                </Style>

            </syncfusion:SfTimePicker.SelectorStyle>        </syncfusion:SfTimePicker>   

{% endhighlight %}

![Features_img9](Features_images/Features_img9.png)





## Setting Incremental Values

To set minute and second values in the SfTimeSelector with incremental values, use the MinuteInterval and SecondsInterval properties respectively.

### MinuteInterval

The MinuteInterval property is used to set the interval for minute values in the SfTimeSelector.

### SecondsInterval

The SecondsInterval property is used to set the interval for second values in the SfTimeSelector.

{% tabs %}

{% highlight xaml %}


<syncfusion:SfTimeSelector FormatString="hh:mm:ss tt" MinuteInterval="2" SecondsInterval="10"/>

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight c# %}

SfTimeSelector timeSelector = new SfTimeSelector();

timeSelector.FormatString = "hh:mm:ss tt";

timeSelector.MinuteInterval = 2;

timeSelector.SecondsInterval = 10;

{% endhighlight %}

{% highlight VB %}

Dim timeSelector As New SfTimeSelector()

timeSelector.FormatString = "hh:mm:ss tt"

timeSelector.MinuteInterval = 2

timeSelector.SecondsInterval = 10

{% endhighlight %}

{% endtabs %}

![Features_img10](Features_images/Features_img10.png)



![Features_img11](Features_images/Features_img11.png)
