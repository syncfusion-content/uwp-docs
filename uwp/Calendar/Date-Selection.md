---
layout: post
title: Date Selection in UWP Calendar control | Syncfusion
description: Learn here all about Date Selection support in Syncfusion UWP Calendar (SfCalendar) control and more.
platform: uwp
control: SfCalendar
documentation: ug
---

# Date Selection in UWP Calendar (SfCalendar)

Dates can be selected in `SfCalendar` in several ways

## Selecting a Single Date

`SelectedDate` property is used to select a date in SfCalendar. 

{% tabs %}

{% highlight XAML %}

<input:SfCalendar SelectedDate="12/15/2015"/>

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

SfCalendar calendar = new SfCalendar();

calendar.SelectedDate = new DateTime(2015, 12, 15);

{% endhighlight %}

{% highlight VB %}

Dim calendar As New SfCalendar()

calendar.SelectedDate = New Date(2015, 12, 15)

{% endhighlight %}

{% endtabs %}

## Selecting Multiple Dates

`SelectedDates` property is used to select one or more dates in SfCalendar. Several range of dates can be selected using this property.

{% tabs %}

{% highlight XAML %}

<input:SfCalendar x:Name="calendar"/>

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

public MainPage()

{
    
   ObservableCollection<DateRange> dateCollection = new  ObservableCollection<DateRange>();
   
   dateCollection.Add(new DateRange(new DateTime(2015, 12, 1), new DateTime(2015, 12, 7)));
   
   dateCollection.Add(new DateRange(new DateTime(2015, 12, 15), new DateTime(2015, 12, 17)));
   
   dateCollection.Add(new DateRange(new DateTime(2015, 12, 27), new DateTime(2015, 12, 31)));
   
   calendar.SelectedDates = dateCollection;
   
}

{% endhighlight %}

{% highlight VB %}

Public Sub New()

   Dim dateCollection As New ObservableCollection(Of DateRange)()

   dateCollection.Add(New DateRange(New Date(2015, 12, 1), New Date(2015, 12, 7)))

   dateCollection.Add(New DateRange(New Date(2015, 12, 15), New Date(2015, 12, 17)))

   dateCollection.Add(New DateRange(New Date(2015, 12, 27), New Date(2015, 12, 31)))

   calendar.SelectedDates = dateCollection

End Sub

{% endhighlight %}


{% endtabs %}

Multiple dates can be selected by

* Setting SelectedDates programmatically

![SfCalendar-img5](SfCalendar-images/SfCalendar-img5.jpeg)


* Clicking on start date and moving the pointer over end date by touch

![SfCalendar-img6](SfCalendar-images/SfCalendar-img6.jpeg)


## DateRange

`DateRange` represents a range of DateTime between a StartDate and EndDate. DateRange can also be a single date. 

### Creating DateRange with Single DateTime

Create an instance of DateRange with StartDate. So that it return a collection of DateTime with the StartDate.

{% tabs %}

{% highlight C# %}

DateRange dateRange = new DateRange(new DateTime(2015, 12, 15));

{% endhighlight %}

{% highlight VB %}

Dim dateRange As New DateRange(New Date(2015, 12, 15))

{% endhighlight %}

{% endtabs %}

### Creating DateRange with Multiple DateTime

Create an instance of DateRange with `StartDate` and `EndDate`. So that it return a collection of DateTime between these two dates.

{% tabs %}

{% highlight C# %}

DateRange dateRange = new DateRange(new DateTime(2015, 12, 15), new DateTime(2015, 12, 17));

{% endhighlight %}

{% highlight VB %}

Dim dateRange As New DateRange(New Date(2015, 12, 15), New Date(2015, 12, 17))

{% endhighlight %}

{% endtabs %}

## Date Selection Mode

`SelectionMode` property determines whether single or multiple dates can be selected in SfCalendar. The values of SelectionMode are 

* Single – Allows to select any one DateTime
* Multiple – Allows to select one or more DateTime
* None – Does not allow to select any DateTime

{% tabs %}

{% highlight XAML %}

<input:SfCalendar SelectionMode="Single"/>

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

calendar.SelectionMode = Syncfusion.UI.Xaml.Controls.Input.SelectionMode.Single;

{% endhighlight %}

{% highlight VB %}

calendar.SelectionMode = Syncfusion.UI.Xaml.Controls.Input.SelectionMode.Single

{% endhighlight %}

{% endtabs %}

## Setting Display Date

`DisplayDate` property is used highlight a date which is not a selected date.

{% tabs %}

{% highlight XAML %}

<input:SfCalendar DisplayDate="12/19/2015"/>

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

SfCalendar calendar = new SfCalendar();

calendar.DisplayDate = new DateTime(2015, 12, 19);

{% endhighlight %}

{% highlight VB %}

Dim calendar As New SfCalendar()

calendar.DisplayDate = New Date(2015, 12, 19)

{% endhighlight %}

{% endtabs %}


## Notifying Selected Date Changed

`SelectionChanged` event fires whenever a calendar day button is selected.

{% tabs %}

{% highlight XAML %}

<input:SfCalendar x:Name="calendar" SelectionChanged="calendar_SelectionChanged"/>

{% endhighlight %}

{% endtabs %}


{% tabs %}

{% highlight C# %}

private void calendar_SelectionChanged(object sender, SelectionChangedEventArgs e)

{

}

{% endhighlight %}

{% highlight VB %}

Private Sub calendar_SelectionChanged(ByVal sender As Object, ByVal e As SelectionChangedEventArgs)


End Sub

{% endhighlight %}


{% endtabs %}

