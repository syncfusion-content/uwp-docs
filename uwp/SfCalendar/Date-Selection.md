---
layout: post
title: Selection features on SfCalendar control for UWP
description: Selection features on SfCalendar control for UWP
platform: uwp
control: SfCalendar
documentation: ug
---

# Date Selection

Dates can be selected in `SfCalendar` in several ways

## SelectedDate

`SelectedDate` property is used to select a date in SfCalendar. 

{% tabs %}

{% highlight XAML %}

<input:SfCalendar SelectedDate="12/15/2015"/>

{% endhighlight %}

{% highlight C# %}

SfCalendar calendar = new SfCalendar();

calendar.SelectedDate = new DateTime(2015, 12, 15);

{% endhighlight %}

{% endtabs %}

## SelectedDates

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

{% endtabs %}

Multiple dates can be selected by

* Setting SelectedDates programmatically

![](SfCalendar-images/SfCalendar-img5.jpeg)


* Clicking on start date and moving the pointer over end date by touch

![](SfCalendar-images/SfCalendar-img6.jpeg)


## DateRange

`DateRange` represents a range of DateTime between a StartDate and EndDate. DateRange can also be a single date. 

### Creating DateRange with single DateTime

Create an instance of DateRange with StartDate. So that it return a collection of DateTime with the StartDate.

{% tabs %}

{% highlight C# %}

DateRange dateRange = new DateRange(new DateTime(2015, 12, 15));

{% endhighlight %}

{% endtabs %}

### Creating DateRange with multiple DateTime

Create an instance of DateRange with `StartDate` and `EndDate`. So that it return a collection of DateTime between these two dates.

{% tabs %}

{% highlight C# %}

DateRange dateRange = new DateRange(new DateTime(2015, 12, 15), new DateTime(2015, 12, 17));

{% endhighlight %}

{% endtabs %}

## Selection Mode

`SelectionMode` property determines whether single or multiple dates can be selected in SfCalendar. The values of SelectionMode are 

* Single – Allows to select any one DateTime
* Multiple – Allows to select one or more DateTime
* None – Does not allow to select any DateTime

{% tabs %}

{% highlight XAML %}

<input:SfCalendar SelectionMode="Single"/>

{% endhighlight %}

{% highlight C# %}

calendar.SelectionMode = Syncfusion.UI.Xaml.Controls.Input.SelectionMode.Single;

{% endhighlight %}

{% endtabs %}

## DisplayDate

`DisplayDate` property is used highlight a date which is not a selected date.

{% tabs %}

{% highlight XAML %}

<input:SfCalendar DisplayDate="12/19/2015"/>

{% endhighlight %}

{% highlight C# %}

SfCalendar calendar = new SfCalendar();

calendar.DisplayDate = new DateTime(2015, 12, 19);

{% endhighlight %}

{% endtabs %}


## SelectionChanged event

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

{% endtabs %}

