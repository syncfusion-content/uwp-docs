---
layout: post
title: Timescale
platform: uwp
control: SfGantt
documentation: ug
---

# Timescale

This section provides an overview on the features of timescale. The following properties are used for configuring the timescale in the [`TimescaleSettings`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfGantt.UWP~Syncfusion.UI.Xaml.Gantt.TimescaleSettings.html) class:

* [`TopTier`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfGantt.UWP~Syncfusion.UI.Xaml.Gantt.TimescaleSettings~TopTier.html): Represents the top tier of the timescale.
* [`BottomTier`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfGantt.UWP~Syncfusion.UI.Xaml.Gantt.TimescaleSettings~BottomTier.html): Represents the bottom tier of the timescale.

{% tabs %}
{% highlight xaml %}
<Gantt:SfGantt.TimescaleSettings>
      <Gantt:TimescaleSettings>
         <Gantt:TimescaleSettings.TopTier>
             <Gantt:TimescaleTier></Gantt:TimescaleTier>
          </Gantt:TimescaleSettings.TopTier>
         <Gantt:TimescaleSettings.BottomTier>
              <Gantt:TimescaleTier IntervalType="Days"></Gantt:TimescaleTier>
          </Gantt:TimescaleSettings.BottomTier>
      </Gantt:TimescaleSettings>
 </Gantt:SfGantt.TimescaleSettings>
{% endhighlight %}

{% highlight c# %}
this.Gantt.TimescaleSettings.TopTier = new TimescaleTier();

this.Gantt.TimescaleSettings.BottomTier = new TimescaleTier();

{% endhighlight %}

{% endtabs %}

![](Timescale_images/overview.jpeg)

By default, the interval type is set to Auto. You can change the interval type and interval using the following properties in `TimescaleTier` class:

* [`IntervalType`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfGantt.UWP~Syncfusion.UI.Xaml.Gantt.TimescaleTier~IntervalType.html): Defines the type of the interval as minutes, hours, days, weeks, quarter, and year.
* [`Interval`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfGantt.UWP~Syncfusion.UI.Xaml.Gantt.TimescaleTier~Interval.html): Sets a value that determines the interval between the timescale tier cells.

The following code sample demonstrates displaying the timescale as years and days.

{% tabs %}
{% highlight xaml %}
<Gantt:SfGantt.TimescaleSettings>
    <Gantt:TimescaleSettings>
       <Gantt:TimescaleSettings.TopTier>
          <Gantt:TimescaleTier Interval="1" IntervalType="Years"></Gantt:TimescaleTier>
       </Gantt:TimescaleSettings.TopTier>
       <Gantt:TimescaleSettings.BottomTier>
          <Gantt:TimescaleTier Interval="4" IntervalType="Days"></Gantt:TimescaleTier>
       </Gantt:TimescaleSettings.BottomTier>
    </Gantt:TimescaleSettings>
  </Gantt:SfGantt.TimescaleSettings>

{% endhighlight %}

{% highlight c# %}
this.Gantt.TimescaleSettings.TopTier = new TimescaleTier()
            {
                Interval = 1,
                IntervalType = IntervalType.Years
            };

this.Gantt.TimescaleSettings.BottomTier = new TimescaleTier()
            {
                Interval = 4,
                IntervalType = IntervalType.Days
            };

{% endhighlight %}
{% endtabs %}
![](Timescale_images/Interval.jpeg)

N> The top tier’s interval and interval type must be greater than the bottom tier’s interval and interval type.

**Display formats**

The display formats can be defined for each interval type. You can set the default date-time format strings as display formats. The display formats can be defined using the following properties:

* [`YearsLabelFormat`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfGantt.UWP~Syncfusion.UI.Xaml.Gantt.TimescaleTier~YearsLabelFormat.html): Sets the the label format for year interval type.
* [`QuarterLabelFormat`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfGantt.UWP~Syncfusion.UI.Xaml.Gantt.TimescaleTier~QuarterLabelFormat.html): Sets the the label format for quarter interval type.
* [`WeeksLabelFormat`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfGantt.UWP~Syncfusion.UI.Xaml.Gantt.TimescaleTier~WeeksLabelFormat.html): Sets the the label format for week interval type.
* [`DaysLabelFormat`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfGantt.UWP~Syncfusion.UI.Xaml.Gantt.TimescaleTier~DaysLabelFormat.html): Sets the label format for days interval type.
* [`HoursLabelFormat`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfGantt.UWP~Syncfusion.UI.Xaml.Gantt.TimescaleTier~HoursLabelFormat.html): Sets the the label format for hours interval type.

## Visual customization

The default view of the timescale can be customized using the following properties:

* [`Background`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfGantt.UWP~Syncfusion.UI.Xaml.Gantt.TimescaleSettings~Background.html): Sets the background color for timescale.
* [`BorderBrush`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfGantt.UWP~Syncfusion.UI.Xaml.Gantt.TimescaleSettings~BorderBrush.html): Sets the color for the border for every timescale cell.
* [`Foreground`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfGantt.UWP~Syncfusion.UI.Xaml.Gantt.TimescaleSettings~Foreground.html): Sets the color for the text in timescale.
* [`LabelAlignment`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfGantt.UWP~Syncfusion.UI.Xaml.Gantt.TimescaleTier~LabelAlignment.html): Changes the alignment of the label in timescale cell.

The following code sample demonstrates how to customize a timescale.

{% tabs %}

{% highlight xaml %}
<Gantt:SfGantt x:Name="Gantt" ItemsSource="{Binding TaskCollection}" ProjectResources="{Binding ResourceCollection}">

     <Gantt:SfGantt.TimescaleSettings>

        <Gantt:TimescaleSettings  Background="LightBlue" BorderBrush="DarkBlue" Foreground="Blue">

           <Gantt:TimescaleSettings.TopTier>

               <Gantt:TimescaleTier LabelAlignment="Left"  IntervalType="Years" >

            </Gantt:TimescaleTier>

            </Gantt:TimescaleSettings.TopTier>

            <Gantt:TimescaleSettings.BottomTier>

                <Gantt:TimescaleTier LabelAlignment="Left" IntervalType="Days">

                </Gantt:TimescaleTier>

           </Gantt:TimescaleSettings.BottomTier>

       </Gantt:TimescaleSettings>

   </Gantt:SfGantt.TimescaleSettings>

</Gantt:SfGantt>

{% endhighlight %}
{% highlight c# %}

this.Gantt.TimescaleSettings.Background = new SolidColorBrush(Colors.LightBlue);
this.Gantt.TimescaleSettings.BorderBrush = new SolidColorBrush(Colors.DarkBlue);
this.Gantt.TimescaleSettings.Foreground = new SolidColorBrush(Colors.Blue);
this.Gantt.TimescaleSettings.TopTier.LabelAlignment = TextAlignment.Left;
this.Gantt.TimescaleSettings.BottomTier.LabelAlignment = TextAlignment.Left;

{% endhighlight %}

{% endtabs %}
![](Timescale_images/DisplayFormats.jpeg)

**Label template**

The default appearance of the label in timescale cell can be customized using the [`LabelTemplate`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfGantt.UWP~Syncfusion.UI.Xaml.Gantt.TimescaleTier~LabelTemplate.html) property in TimescaleTier class.

{% tabs %}

{% highlight xaml %}
 <Gantt:SfGantt x:Name="Gantt" ItemsSource="{Binding TaskCollection}" AllowEditing="True" ProjectResources="{Binding ResourceCollection}">

      <Gantt:SfGantt.TimescaleSettings>

          <Gantt:TimescaleSettings >

             <Gantt:TimescaleSettings.TopTier>

                 <Gantt:TimescaleTier  IntervalType="Years" >

                     <Gantt:TimescaleTier.LabelTemplate>

                        <DataTemplate>

                            <TextBlock Text="{Binding Content}" Foreground="Red" FontSize="24"></TextBlock>

                         </DataTemplate>

                    </Gantt:TimescaleTier.LabelTemplate>

                  </Gantt:TimescaleTier>

               </Gantt:TimescaleSettings.TopTier>

         <Gantt:TimescaleSettings.BottomTier>

         <Gantt:TimescaleTier IntervalType="Days">

              <Gantt:TimescaleTier.LabelTemplate>

                   <DataTemplate>

                       <TextBlock Text="{Binding Content}" Width="30" Foreground="Black" FontSize="20"></TextBlock>

                   </DataTemplate>

                 </Gantt:TimescaleTier.LabelTemplate>

              </Gantt:TimescaleTier>

           </Gantt:TimescaleSettings.BottomTier>

       </Gantt:TimescaleSettings>

    </Gantt:SfGantt.TimescaleSettings>

</Gantt:SfGantt>

{% endhighlight %}

{% endtabs %}

![](Timescale_images/Template.jpeg)

## Cell width customization

The width for the timescale cell in the bottom tier can be set using the [`CellSize`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfGantt.UWP~Syncfusion.UI.Xaml.Gantt.TimescaleSettings~CellSize.html) property in [`TimescaleSettings`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfGantt.UWP~Syncfusion.UI.Xaml.Gantt.TimescaleSettings.html).

The following code sample demonstrates how to increase the width of a timescale cell.

{% tabs %}

{% highlight xaml %}
<Gantt:SfGantt x:Name="Gantt" ItemsSource="{Binding TaskCollection}" ProjectResources="{Binding ResourceCollection}">

     <Gantt:SfGantt.TimescaleSettings>

        <Gantt:TimescaleSettings CellSize="350" >

        </Gantt:TimescaleSettings>

     </Gantt:SfGantt.TimescaleSettings>

</Gantt:SfGantt>

{% endhighlight %}

{% highlight c# %}


this.Gantt.TimescaleSettings.CellSize = 350;

{% endhighlight %}

{% endtabs %}

![](Timescale_images/cellwidth.jpeg)

N> The value for the cell width ranges between 25 and 1000.

## Range customization

The start or end range of a timescale can be explicitly defined using the [`TimescaleStartDate`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfGantt.UWP~Syncfusion.UI.Xaml.Gantt.SfGantt~TimescaleStartDate.html) and [`TimescaleEndDate`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfGantt.UWP~Syncfusion.UI.Xaml.Gantt.SfGantt~TimescaleEndDate.html) properties in [`SfGantt`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfGantt.UWP~Syncfusion.UI.Xaml.Gantt.SfGantt.html) class.

The following code sample demonstrates how to customize the range of a timescale.

{% tabs %}

{% highlight xaml %}


<Gantt:SfGantt x:Name="Gantt" TimescaleStartDate="2014/1/1" 
               TimescaleEndDate="2014/4/1" 
               ItemsSource="{Binding TaskCollection}"
               ProjectResources="{Binding ResourceCollection}">

</Gantt:SfGantt>

{% endhighlight %}

{% highlight c# %}


this.Gantt.TimescaleStartDate = new DateTime(2014, 1, 1);

this.Gantt.TimescaleEndDate = new DateTime(2014, 5, 1);


{% endhighlight %}

{% endtabs %}

![](Timescale_images/range.jpeg)
