---
layout: post
title: Deals with label options in SfRangeSlider control for UWP
description: Explains about label options in SfRangeSlider control for UWP
platform: uwp
control: SfRange Slider 
documentation: ug
---

# Label Support

This feature allows users to display labels for custom values given in the CustomLabels collection when the ShowCustomLabels property is set to true. It also displays labels for all of the tick values when ShowValueLabels is set to true.

<table>
<tr>
<th>
Property</th><th>
Description</th></tr>
<tr>
<td>
CustomLabels</td><td>
It describes an observable collection of items that contains the custom labels and the values for which the labels should be displayed.</td></tr>
<tr>
<td>
ShowCustomLabels</td><td>
This property allows us to display custom labels for particular values based on CustomLabels collection.</td></tr>
<tr>
<td>
ShowValueLabels</td><td>
This property allows us to display labels for the ticks.</td></tr>
<tr>
<td>
LabelPlacement</td><td>
This property specifies the position of the custom label placement.</td></tr>
<tr>
<td>
ValuePlacement</td><td>
This property specifies the position of the label for all of the ticks.</td></tr>
<tr>
<td>
LabelOrientation</td><td>
LabelOrientation specifies the orientation of the labels as either horizontal or vertical.</td></tr>
</table>

## CustomLabels

CustomLabels is an observable collection of items which contains the Label and Value properties. We have to create an observable collection of items by specifying the custom labels for corresponding values as shown in the following code sample:

{% tabs %}

{% highlight c# %}

this.customCollection.Add(new Items(){label = "Min", value= 100});

this.customCollection.Add(new Items() { label = "Max", value = 200 });

private ObservableCollection<Items> customCollection = new ObservableCollection<Items>();



public ObservableCollection<Items> CustomCollection

{

get { return customCollection; }

set { customCollection = value; }

}

{% endhighlight %}


{% highlight VB %}

  Me.customCollection_Renamed.Add(New Items() With {
	.label = "Min",
	.value= 100
})

Me.customCollection_Renamed.Add(New Items() With {
	.label = "Max",
	.value = 200
})

private ObservableCollection(Of Items) customCollection_Renamed = New ObservableCollection(Of Items)()



public ObservableCollection(Of Items) CustomCollection

If True Then

Get
	Return customCollection_Renamed
End Get

Set
	customCollection_Renamed = value
End Set

End If

{% endhighlight %}

{% endtabs %}


In the following sample, we have bound the CustomCollection property to CustomLabels property in the RangeSlider control, which populates the custom labels collection:


{% tabs %}

{% highlight xaml %}

<editors:SfRangeSlider x:Name="rangeSlider" Width="200" Minimum="100" Maximum="200" TickFrequency="20" TickPlacement="Outside" ShowCustomLabels="True" CustomLabels="{Binding CustomCollection}" />

{% endhighlight %}

{% endtabs %}



![](Label-Support_images/Label-Support_img1.png)


## ShowCustomLabels


The default value of ShowCustomLabels is false. When set to true, it will display the custom labels for particular values based on the CustomLabels collection.

{% tabs %}

{% highlight xaml %}

<editors:SfRangeSlider x:Name="rangeSlider" Width="200" Minimum="100" Maximum="200" TickFrequency="20" TickPlacement="Outside" ShowCustomLabels="True" CustomLabels="{Binding CustomCollection}" />

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight c# %}

   rangeSlider.ShowCustomLabels = true;

{% endhighlight %}

{% highlight VB %}

   rangeSlider.ShowCustomLabels = True

{% endhighlight %}

{% endtabs %}

![](Label-Support_images/Label-Support_img2.png)

## LabelPlacement

LabelPlacement property describes the position of the custom labels for particular values mentioned in the CustomLabels collection. Available options for this property are:

1. BottomRight
2. TopLeft

The following code sample shows the usage of the LabelPlacement property. The output is displayed in the corresponding images.

{% tabs %}

{% highlight xaml %}

<editors:SfRangeSlider x:Name="rangeSlider" Width="200" Minimum="100" Maximum="200" TickFrequency="20" TickPlacement="Outside" ShowCustomLabels="True" CustomLabels="{Binding CustomCollection}" LabelPlacement="BottomRight"/>

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight c# %}

   rangeSlider.LabelPlacement = Syncfusion.UI.Xaml.Controls.Input.LabelPlacement.BottomRight;

{% endhighlight %}

{% highlight VB %}

   rangeSlider.LabelPlacement = Syncfusion.UI.Xaml.Controls.Input.LabelPlacement.BottomRight

{% endhighlight %}

{% endtabs %}

![](Label-Support_images/Label-Support_img3.png)

{% tabs %}

{% highlight xaml %}

<editors:SfRangeSlider x:Name="rangeSlider" Width="200" Minimum="100" Maximum="200" TickFrequency="20" TickPlacement="Outside" ShowCustomLabels="True" 

CustomLabels="{Binding CustomCollection}" LabelPlacement="TopLeft"/>

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight c# %}

   rangeSlider.LabelPlacement = Syncfusion.UI.Xaml.Controls.Input.LabelPlacement.TopLeft;

{% endhighlight %}

{% highlight VB %}

   rangeSlider.LabelPlacement = Syncfusion.UI.Xaml.Controls.Input.LabelPlacement.TopLeft

{% endhighlight %}

{% endtabs %}

![](Label-Support_images/Label-Support_img4.png)

## ShowValueLabels

The default value of the ShowValueLabels property is false. When set to true, it will display the label for all the ticks based on the ValuePlacement property.

{% tabs %}

{% highlight xaml %}

<editors:SfRangeSlider x:Name="rangeSlider" Width="200" Minimum="100"   Maximum="200" TickFrequency="20" TickPlacement="BottomRight" ShowValueLabels="True"/>

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight c# %}

   rangeSlider.ShowValueLabels = true;

{% endhighlight %}

{% highlight VB %}

  rangeSlider.ShowValueLabels = True

{% endhighlight %}

{% endtabs %}

![](Label-Support_images/Label-Support_img5.png)

## ValuePlacement

The ValuePlacement property describes the position of the labels for all the ticks. Available options for this property are:

1. BottomRight
2. TopLeft

The following code sample shows the usage of ValuePlacement property. The output is displayed in the corresponding images.

{% tabs %}

{% highlight xaml %}

<editors:SfRangeSlider x:Name="rangeSlider" Width="200" Minimum="100" Maximum="200" TickFrequency="20" TickPlacement="Outside" ShowValueLabels="True" ValuePlacement="TopLeft"/>

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight c# %}

   rangeSlider.ValuePlacement = Syncfusion.UI.Xaml.Controls.Input.ValuePlacement.TopLeft;

{% endhighlight %}

{% highlight VB %}

  rangeSlider.ValuePlacement = Syncfusion.UI.Xaml.Controls.Input.ValuePlacement.TopLeft

{% endhighlight %}

{% endtabs %}

![](Label-Support_images/Label-Support_img6.png)

{% tabs %}

{% highlight xaml %}

<editors:SfRangeSlider x:Name="rangeSlider" Width="200" Minimum="100" Maximum="200" TickFrequency="20" TickPlacement="Outside" ShowValueLabels="True" ValuePlacement="BottomRight"/>

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight c# %}

   rangeSlider.ValuePlacement = Syncfusion.UI.Xaml.Controls.Input.ValuePlacement.BottomRight;

{% endhighlight %}

{% highlight VB %}

  rangeSlider.ValuePlacement = Syncfusion.UI.Xaml.Controls.Input.ValuePlacement.BottomRight

{% endhighlight %}

{% endtabs %}

![](Label-Support_images/Label-Support_img7.png)

## LabelOrientation

The LabelOrientation property describes the orientation of the labels for both ticks and custom labels. Available options for this property are:

1. Horizontal
2. Vertical

The following code sample shows the usage of LabelOrientation property. The output is displayed in the corresponding images.

{% tabs %}

{% highlight xaml %}

<editors:SfRangeSlider x:Name="rangeSlider" Width="200" Minimum="100" Maximum="200" TickFrequency="20" TickPlacement="Outside" ShowValueLabels="True" LabelOrientation="Horizontal"/>

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight c# %}

   rangeSlider.LabelOrientation = Orientation.Horizontal;

{% endhighlight %}

{% highlight VB %}

  rangeSlider.LabelOrientation = Orientation.Horizontal

{% endhighlight %}

{% endtabs %}

![](Label-Support_images/Label-Support_img8.png)

{% tabs %}

{% highlight xaml %}

<editors:SfRangeSlider x:Name="rangeSlider" Width="200" Minimum="100" Maximum="200" TickFrequency="20" TickPlacement="Outside" ShowValueLabels="True" LabelOrientation="Vertical"/>

{% endhighlight %}


{% endtabs %}

{% tabs %}

{% highlight c# %}

   rangeSlider.LabelOrientation = Orientation.Vertical;

{% endhighlight %}

{% highlight VB %}

  rangeSlider.LabelOrientation = Orientation.Vertical

{% endhighlight %}

{% endtabs %}

![](Label-Support_images/Label-Support_img9.png)


## Customizing label font

The range slider control provides the `FontFamily`, `FontWeight` , `FontStyle` and `FontSize` properties to customize the value text and custom label text.


{% tabs %}

{% highlight xaml %}

<editors:SfRangeSlider x:Name="rangeSlider" Width="300" FontFamily="Times New Roman" FontSize="15" FontStyle="Normal" FontWeight="Bold" Minimum="100" Maximum="200" TickFrequency="20" TickPlacement="Outside" ShowValueLabels="True" LabelOrientation="Horizontal"/>

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight c# %}

   rangeSlider.FontSize = 15;
   rangeSlider.FontStyle = Windows.UI.Text.FontStyle.Normal;
   rangeSlider.FontWeight = Windows.UI.Text.FontWeights.Bold;
   rangeSlider.FontFamily = new FontFamily("Times New Roman");

{% endhighlight %}

{% highlight VB %}

   rangeSlider.FontSize = 15
   rangeSlider.FontStyle = Windows.UI.Text.FontStyle.Normal
   rangeSlider.FontWeight = Windows.UI.Text.FontWeights.Bold
   rangeSlider.FontFamily = new FontFamily("Times New Roman")

{% endhighlight %}

{% endtabs %}

![](Label-Support_images/Label-Support_img10.png)


