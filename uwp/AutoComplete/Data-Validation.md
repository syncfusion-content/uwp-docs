---
layout: post
title: Data Validation in UWP AutoComplete control | Syncfusion
description: Learn here all about Data Validation support in Syncfusion UWP AutoComplete (SfTextBoxExt) control and more.
platform: UWP
control: SfTextBoxExt
documentation: ug
---

# Data Validation in UWP AutoComplete (SfTextBoxExt)

All editors have the data validation support, it can be done by inheriting the model class from the Syncfusion.UI.Xaml.Controls.Data.IDataValidation.

![Data Validation](Data-Validation_images/Data-Validation_img1.png)

N>  The Model should also inherit the INotifyPropertyChanged Interface.



The following code sample shows the model class:

{% tabs %}

{% highlight c# %}

public class DataValidationHelper : INotifyPropertyChanged, IDataValidation

{

    private string name;

    public string Name

    {

        get { return name; }

        set

        {

            name = value;

            RaisePropertyChanged("Name");

            RaisePropertyChanged("Error");

        }

    }

    public string Error

    {

        get

        {

            if (String.IsNullOrEmpty(Name))

            {

                return "Name field required.";

            }
         
            return "";

        }         

    }

    public string this[string columnname]

    {

        get

        {

            switch (columnname)

            {

                case "Name":

                    if (String.IsNullOrEmpty(Name))

                    {

                        return "Name field required.";

                    }

                    break;

            }

            return "";

        }

    }

    public event PropertyChangedEventHandler PropertyChanged;

    public void RaisePropertyChanged(string propertyname)

    {

        if (PropertyChanged != null)

        {

            PropertyChanged(this, new PropertyChangedEventArgs(propertyname));

        }

    }

{% endhighlight %}

{% highlight VB %}

Public Class DataValidationHelper

	Implements INotifyPropertyChanged, IDataValidation

	Private name_Renamed As String

	Public Property Name() As String


		Get
			Return name_Renamed
		End Get

		Set(ByVal value As String)


			name_Renamed = value

			RaisePropertyChanged("Name")

			RaisePropertyChanged("Error")

		End Set

	End Property

	Public ReadOnly Property [Error]() As String


		Get


			If String.IsNullOrEmpty(Name) Then


				Return "Name field required."

			End If

		End Get
		 Return ""

	End Property

	Default Public ReadOnly Property Item(ByVal columnname As String) As String


		Get


			Select Case columnname


				Case "Name"

					If String.IsNullOrEmpty(Name) Then


						Return "Name field required."

					End If


			End Select

			Return ""

		End Get

	End Property

	Public Event PropertyChanged As PropertyChangedEventHandler Implements INotifyPropertyChanged.PropertyChanged

	Public Sub RaisePropertyChanged(ByVal propertyname As String)

	RaiseEvent PropertyChanged(Me, New PropertyChangedEventArgs(propertyname))

End Sub

{% endhighlight %}

{% endtabs %}

### NotifyOnDataErrors 

Gets or Sets the bool value which determine the enable or disable the DataValidation with the control.



### PropertyPath

Gets or sets the name of the property which bound to the SfTextBoxExt Value property.

{% highlight xaml %}

<Page xmlns:data="using:Syncfusion.UI.Xaml.Controls.Data" xmlns:Input="using:Syncfusion.UI.Xaml.Controls.Input">

    <Grid Background="{StaticResource ApplicationPageBackgroundThemeBrush}">

        <StackPanel Margin="5" Orientation="Vertical">

            <TextBlock Text="Name:" />

            <Input:SfTextBoxExt x:Name="NameBox"

                                Width="250"

                                Text="{Binding Name,Mode=TwoWay}"

                                data:DataValidation.NotifyOnDataErrors="True"

                                data:DataValidation.PropertyPath="Name" />

        </StackPanel>

    </Grid>

</Page>

{% endhighlight %}

N>  The following additional properties have the status of DataValidation:
 HasError: Gets whether the element has data error or not.
 ErrorMessage: Gets or sets the name of the property which bound to the SfTextBoxExt Value property.



