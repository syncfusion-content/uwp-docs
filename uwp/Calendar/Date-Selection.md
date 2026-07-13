---
layout: post
title: Date Selection in UWP Calendar control | Syncfusion
description: Learn here all about Date Selection support in the Syncfusion UWP Calendar (SfCalendar) control and more.
platform: uwp
control: SfCalendar
documentation: ug
---

# Date Selection in UWP Calendar (SfCalendar)

Dates can be selected in `SfCalendar` in several ways.

## Selecting a Single Date

The `SelectedDate` property is used to select a date in SfCalendar.

{% tabs %}

{% highlight XAML %}

<Page
   ...
   xmlns:input="using:Syncfusion.UI.Xaml.Controls.Input">

    <input:SfCalendar SelectedDate="12/15/2015"/>
</Page>

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

using Syncfusion.UI.Xaml.Controls.Input;

SfCalendar calendar = new SfCalendar();

calendar.SelectedDate = new DateTime(2015, 12, 15);

{% endhighlight %}

{% highlight VB %}

Dim calendar As New SfCalendar()

calendar.SelectedDate = New Date(2015, 12, 15)

{% endhighlight %}

{% endtabs %}

## Selecting Multiple Dates

The `SelectedDates` property is used to select one or more dates in SfCalendar. Several ranges of dates can be selected using this property.

{% tabs %}

{% highlight XAML %}

<Page
   ...
   xmlns:input="using:Syncfusion.UI.Xaml.Controls.Input">

    <input:SfCalendar x:Name="calendar"/>
</Page>

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

using Syncfusion.UI.Xaml.Controls.Input;

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

Multiple dates can be selected by:

* Setting SelectedDates programmatically

![SfCalendar-img5](SfCalendar-images/SfCalendar-img5.jpeg)


* Clicking on the start date and moving the pointer over the end date by touch

![SfCalendar-img6](SfCalendar-images/SfCalendar-img6.jpeg)


## DateRange

`DateRange` represents a range of DateTime between a StartDate and an EndDate. DateRange can also be a single date.

### Creating DateRange with Single DateTime

Create an instance of DateRange with StartDate so that it returns a collection of DateTime with the StartDate.

{% tabs %}

{% highlight C# %}

using Syncfusion.UI.Xaml.Controls.Input;

DateRange dateRange = new DateRange(new DateTime(2015, 12, 15));

{% endhighlight %}

{% highlight VB %}

Dim dateRange As New DateRange(New Date(2015, 12, 15))

{% endhighlight %}

{% endtabs %}

### Creating DateRange with Multiple DateTime

Create an instance of DateRange with `StartDate` and `EndDate` so that it returns a collection of DateTime between these two dates.

{% tabs %}

{% highlight C# %}

using Syncfusion.UI.Xaml.Controls.Input;

DateRange dateRange = new DateRange(new DateTime(2015, 12, 15), new DateTime(2015, 12, 17));

{% endhighlight %}

{% highlight VB %}

Dim dateRange As New DateRange(New Date(2015, 12, 15), New Date(2015, 12, 17))

{% endhighlight %}

{% endtabs %}

## Date Selection Mode

The `SelectionMode` property determines whether single or multiple dates can be selected in SfCalendar. The values of SelectionMode are:

* Single – Allows selecting any one DateTime
* Multiple – Allows selecting one or more DateTime
* MultiRange – Allows selecting multiple ranges of DateTime
* Range – Allows selecting a range of DateTime
* None – Does not allow selecting any DateTime

{% tabs %}

{% highlight XAML %}

<Page
   ...
   xmlns:input="using:Syncfusion.UI.Xaml.Controls.Input">

    <input:SfCalendar SelectionMode="Single"/>
</Page>

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

using Syncfusion.UI.Xaml.Controls.Input;

calendar.SelectionMode = Syncfusion.UI.Xaml.Controls.Input.SelectionMode.Single;

{% endhighlight %}

{% highlight VB %}

calendar.SelectionMode = Syncfusion.UI.Xaml.Controls.Input.SelectionMode.Single

{% endhighlight %}

{% endtabs %}

## Setting Display Date

The `DisplayDate` property is used to highlight a date which is not a selected date.

{% tabs %}

{% highlight XAML %}

<Page
   ...
   xmlns:input="using:Syncfusion.UI.Xaml.Controls.Input">

    <input:SfCalendar DisplayDate="12/19/2015"/>
</Page>

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

using Syncfusion.UI.Xaml.Controls.Input;

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

<Page
   ...
   xmlns:input="using:Syncfusion.UI.Xaml.Controls.Input">

    <input:SfCalendar x:Name="calendar" SelectionChanged="calendar_SelectionChanged"/>
</Page>

{% endhighlight %}

{% endtabs %}


{% tabs %}

{% highlight C# %}

using Syncfusion.UI.Xaml.Controls.Input;

private void calendar_SelectionChanged(object sender, SelectionChangedEventArgs e)

{

}

{% endhighlight %}

{% highlight VB %}

Private Sub calendar_SelectionChanged(ByVal sender As Object, ByVal e As SelectionChangedEventArgs)


End Sub

{% endhighlight %}


{% endtabs %}

