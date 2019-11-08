---
layout: post
title: Reminder | SfSchedule | uwp | Syncfusion
description: Reminder
platform: uwp
control: SfSchedule
documentation: ug
---

# Reminder

Schedule reminds you the particular appointment in the specified time by setting the **EnableReminderTimer** property is true. The remainder time can be set using the ReminderTime property of ScheduleAppointment.

>**Note:-Open package.appxmanifest file to the _Application UI tab,and select "Yes" from the "Toast capable" dropdown list,to enable toast notifications in your application manifest.**

{% highlight c# %}

     SfSchedule schedule = new SfSchedule();
     schedule.EnableReminderTimer = true;
     schedule.Appointments.Add(new ScheduleAppointment
            {
                StartTime = DateTime.Now.Date.AddHours(9),
                EndTime   = DateTime.Now.Date.AddHours(12),
                AppointmentBackground = new SolidColorBrush(Color.FromArgb(0xFf, 0xA2, 0xC1, 0x39)),
                Subject = "Business Meeting",
                ReminderTime = ReminderTimeType.TenHours
            });
            schedule.Appointments.Add(new ScheduleAppointment
            {
                StartTime = currentDate.Date.AddDays(1).AddHours(10),
                EndTime = currentDate.Date.AddDays(1).AddHours(16),
                AppointmentBackground = new SolidColorBrush(Color.FromArgb(0xFf, 0xD8, 0x00, 0x73)),
                Subject = "Auditing",
                ReminderTime = ReminderTimeType.TwoDays
            });
             schedule.Appointments.Add(new ScheduleAppointment
            {
                StartTime = DateTime.Now.Date.AddDays(7).AddHours(10),
                EndTime = DateTime.Now.Date.AddDays(7).AddHours(13),
                AppointmentBackground = new SolidColorBrush(Color.FromArgb(0xFf, 0xF0, 0x96, 0x09)),
                Subject = "Conference",
                ReminderTime = ReminderTimeType.TwoWeeks
            });
            this.grid.Children.Add(schedule);

{% endhighlight %}

![](Reminder_images/Reminder_img1.jpeg)
