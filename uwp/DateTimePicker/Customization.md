---
layout: post
title: Customization in UWP DateTimePicker control | Syncfusion
description: Learn here all about Customization support in Syncfusion UWP DateTimePicker (SfDateTimeCombo) control and more.
platform: uwp
control: SfDateTimeCombo
documentation: ug
---

# Customization in UWP DateTimePicker (SfDateTimeCombo)

The DateTimeItem drop-down lists displayed in this control include date or time parts that can be customized in a user-friendly manner using the properties below.

## DayComboStyle

The DayComboStyle property is used to customize the style of the DateTimeItem containing the day part of the DateTime set in the SfDateTimeCombo control.



{% highlight html %}

   <syncfusion:SfDateTimeCombo FormatString="Mdy" Name="SfDateTimeCombo" 

                               Width="430" HorizontalAlignment="Left">

            <syncfusion:SfDateTimeCombo.DayComboStyle>

                <Style TargetType="syncfusion:DateTimeItem">

                    <Setter Property="Background" Value="Blue"/>

                </Style>

            </syncfusion:SfDateTimeCombo.DayComboStyle>

        </syncfusion:SfDateTimeCombo>

{% endhighlight %}

![Customization_img1](Customization_images/Customization_img1.png)


## MonthComboStyle

The MonthComboStyle property is used to customize the style of the DateTimeItem containing the month part of the DateTime set in the SfDateTimeCombo control.

![Customization_img2](Customization_images/Customization_img2.png)



## YearComboStyle

The YearComboStyle property is used to customize the style of the DateTimeItem containing the year part of DateTime set in the SfDateTimeCombo control.



![Customization_img3](Customization_images/Customization_img3.png)


## MinuteComboStyle

The MinuteComboStyle property is used to customize the style of the DateTimeItem containing the minute part of the DateTime set in the SfDateTimeCombo control.

![Customization_img4](Customization_images/Customization_img4.png)





## TwelveHourComboStyle

The TwelveHourComboStyle property is used to customize the style of the DateTimeItem containing the twelve hour part of the DateTime set in the SfDateTimeCombo control.



![Customization_img5](Customization_images/Customization_img5.png)





## TwentyFourHourComboStyle

The TwentyFourHourComboStyle property is used to customize the style of the DateTimeItem containing the twenty-four hour part of the DateTime set in the SfDateTimeCombo control.

![Customization_img6](Customization_images/Customization_img6.png)





## SecondComboStyle

The SecondComboStyle property is used to customize the style of the DateTimeItem containing the second part of the DateTime set in the SfDateTimeCombo control. 


![Customization_img7](Customization_images/Customization_img7.png)


## AMPMDesignatorComboStyle

The AMPMDesignatorComboStyle property is used to customize the style of the DateTimeItem containing the AM/PM part of DateTime set in the SfDateTimeCombo control.

![Customization_img8](Customization_images/Customization_img8.png)



## Item template

The Item template property is used to decorate the DateTimeItem drop-down list containing the date or time lists with custom visuals. 

N>  The DataContext of a DateTimeItem drop-down list containing date or time parts is Syncfusion.UI.Xaml.Primitives.DateTimeWrapper.



### DayItemTemplate

The DayItemTemplate property is used to define the DateTimeItem template of the day section set in the SfDateTimeCombo control.

{% highlight html %}

<syncfusion:SfDateTimeCombo FormatString="d" Name="SfDateTimeCombo" 

                               Width="430" HorizontalAlignment="Left">

            <syncfusion:SfDateTimeCombo.DayItemTemplate>

                <DataTemplate>

                    <Grid>

                        <Grid.ColumnDefinitions>

                            <ColumnDefinition Width="*"></ColumnDefinition>

                            <ColumnDefinition Width="20"></ColumnDefinition>

                        </Grid.ColumnDefinitions>

                        <TextBlock Grid.Column="0" Text="{Binding DayName}" />

                        <TextBlock Grid.Column="1" Text="{Binding DayNumber}" />

                    </Grid>

                </DataTemplate>

            </syncfusion:SfDateTimeCombo.DayItemTemplate>

    </syncfusion:SfDateTimeCombo>

{% endhighlight %}

![Customization_img10](Customization_images/Customization_img10.png)

### MonthItemTemplate

The MonthItemTemplate property is used to define the DateTimeItem template of the month set in the SfDateTimeCombo control.

![Customization_img11](Customization_images/Customization_img11.png)

### YearItemTemplate

The YearItemTemplate property is used to define the DateTimeItem template of the year part in the SfDateTimeCombo control.

![Customization_img12](Customization_images/Customization_img12.png)



### MinuteItemTemplate

The MinuteItemTemplate property is used to define the DateTimeItem template of the minute part in the SfDateTimeCombo control.

![Customization_img13](Customization_images/Customization_img13.png)

### SecondItemTemplate

The SecondItemTemplate property is used to define the DateTimeItem template of the second part in the SfDateTimeCombo control.

![Customization_img14](Customization_images/Customization_img14.png)

### TwelveHourItemTemplate

The TwelveHourItemTemplate property is used to define the DateTimeItem template of twelve hour part in the SfDateTimeCombo control.

![Customization_img15](Customization_images/Customization_img15.png)


### TwentyFourHourItemTemplate

The TwentyFourHourItemTemplate property is used to define the DateTimeItem template of twenty-four hour part in the SfDateTimeCombo control.


![Customization_img16](Customization_images/Customization_img16.png)

### AMPMDesignatorItemTemplate

The AMPMDesignatorItemTemplate property is used to define the DateTimeItem template of the AM/PM part set in the SfDateTimeCombo control.

![Customization_img17](Customization_images/Customization_img17.png)
