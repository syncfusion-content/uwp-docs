---
title: Automatic Suggestion | UWP RichTextBox| Syncfusion
description: This section illustrates about automatic suggestion support in UWP RichTextBox(SfRichTextBoxAdv) control.
platform: uwp
control: SfRichTextBoxAdv
documentation: ug
keywords: automatic-suggestion, @mentions
---
# Automatic Suggestion

## Automatic Suggestion functionality for using @mentions in SfRichTextBoxAdv control
SfRichTextBoxAdv control shows an inline dropdown with a list of suggested names while type the mention character (ex: @ symbol). The list of names will filter as you type more letters. You can use up or down arrow key to move selection and Tab or Enter key to insert selected item in keyboard or use mouse to click any option in the list. The selected item from the suggestion list will be inserted as hyperlink with the display text and its respective link.

![Automatic Suggestion](Automatic-Suggestion_images/autosuggestion1.PNG)

The following sample code demonstrates how to use @mentions in SfRichTextBoxAdv.
{% tabs %}
{% highlight xaml %}
<Page.Resources>
        <Style x:Key="SuggestionBoxStyle" TargetType="ListBox">
            <Setter Property="MinWidth" Value="300" />
            <Setter Property="MinHeight" Value="250" />
            <Setter Property="ItemTemplate">
                <Setter.Value>
                    <DataTemplate >
                        <StackPanel Orientation="Horizontal" Height="64" >
                            <Ellipse Height="48" Width="48" VerticalAlignment="Center">
                                <Ellipse.Fill>
                                    <ImageBrush ImageSource="{Binding ImageSource}"/>
                                </Ellipse.Fill>
                            </Ellipse>
                            <StackPanel Orientation="Vertical" VerticalAlignment="Center" Margin="12,0,0,0">
                                <TextBlock Text="{Binding Name}" FontSize="14"  />
                                <TextBlock Text="{Binding Link}" FontSize="10" />
                            </StackPanel>
                        </StackPanel>
                    </DataTemplate>
                </Setter.Value>
            </Setter>
        </Style>
    </Page.Resources>
    <Grid>
        <RichTextBoxAdv:SfRichTextBoxAdv x:Name="richTextBoxAdv" ManipulationMode="All" 
                                         LayoutType="Continuous"  xmlns:RichTextBoxAdv="using:Syncfusion.UI.Xaml.RichTextBoxAdv"/>
    </Grid>

{% endhighlight %}
{% highlight C# %}
ISuggestionProvider suggestionProvider = new NameSuggestionProvider();
            suggestionProvider.SuggestionBoxStyle = this.Resources["SuggestionBoxStyle"] as Style;

            List<NameSuggestionItem> suggestionItems = new List<NameSuggestionItem>();
            NameSuggestionItem suggestionItem = new NameSuggestionItem();
            suggestionItem.Name = "Nancy Davolio";
            suggestionItem.Link = "mailto:nancy.davolio@northwindtraders.com";
            BitmapImage bitmapImage = new BitmapImage(new Uri(new DirectoryInfo(@"ms - appx:..\..\Assets\People_Circle0.png").FullName));
            suggestionItem.ImageSource = bitmapImage;
            suggestionItems.Add(suggestionItem);

            suggestionItem = new NameSuggestionItem();
            suggestionItem.Name = "Andrew Fuller";
            suggestionItem.Link = "mailto:andrew.fuller@northwindtraders.com";
            bitmapImage = new BitmapImage(new Uri(new DirectoryInfo(@"ms - appx:..\..\Assets\People_Circle5.png").FullName));
            suggestionItem.ImageSource = bitmapImage;
            suggestionItems.Add(suggestionItem);

            suggestionItem = new NameSuggestionItem();
            suggestionItem.Name = "Steven Buchanan";
            suggestionItem.Link = "mailto:steven.buchanan@northwindtraders.com";
            bitmapImage = new BitmapImage(new Uri(new DirectoryInfo(@"ms - appx:..\..\Assets\People_Circle18.png").FullName));
            suggestionItem.ImageSource = bitmapImage;
            suggestionItems.Add(suggestionItem);

            (suggestionProvider as NameSuggestionProvider).ItemsSource = suggestionItems;
            richTextBoxAdv.SuggestionSettings.SuggestionProviders.Add(suggestionProvider);
{% endhighlight %}
{% endtabs %}

N> [View sample in GitHub]()

## Customize the SuggestionBox ItemTemplate and Style
By default, the drop-down window lists the filtered items as an image, display text and link. If you want to remove the image or link. You can write your own item Template.

![Modify Suggestion Box Item](Automatic-Suggestion_images/autosuggestion2.PNG)

The following sample code demonstrates how to modify the suggestion box item template and style.
{% tabs %}
{% highlight xaml %}

{% endhighlight %}
{% highlight C# %}

{% endhighlight %}
{% endtabs %}


## Custom mention character
By default, @ is a mention character. But any character can be used as mention character.

![Mention Character](Automatic-Suggestion_images/autosuggestion3.PNG)

The following sample code demonstrates how to use ‘#’ as mention character.
{% tabs %}
{% highlight xaml %}

{% endhighlight %}
{% highlight C# %}
ISuggestionProvider suggestionProvider = new NameSuggestionProvider();
suggestionProvider.MentionCharacter = '#';
richTextboxadv.SuggestionSettings.SuggestionProviders.Add(suggestionProvider);

{% endhighlight %}
{% endtabs %}


## Multiple Suggestion provider
Two or more suggestion providers can be used at a time but, each suggestion provider should have different mention character. And each suggestion provider can have different item source and suggestion box style.

<table><tr><td><img src="Automatic-Suggestion_images/autosuggestion6.PNG"/><br/></td><td><img src="Automatic-Suggestion_images/autosuggestion7.PNG"/><br/></td></tr></table>

The following sample code demonstrates how to use two suggestion providers. Here we have used ‘@’ and ‘#’ as mentions characters.
{% tabs %}
{% highlight xaml %}
<Page.Resources>
        <Style x:Key="SuggestionBoxStyle01" TargetType="ListBox">
            <Setter Property="MinWidth" Value="300" />
            <Setter Property="MinHeight" Value="250" />
            <Setter Property="ItemTemplate">
                <Setter.Value>
                    <DataTemplate >
                        <StackPanel Orientation="Horizontal" Width="200">
                            <StackPanel Orientation="Vertical" VerticalAlignment="Center" Margin="12,0,0,0">
                                <TextBlock Text="{Binding Name}" FontSize="14"  />
                                <TextBlock Text="{Binding Link}" FontSize="10"  />
                            </StackPanel>
                        </StackPanel>
                    </DataTemplate>
                </Setter.Value>
            </Setter>
        </Style>
        
        <Style x:Key="SuggestionBoxStyle" TargetType="ListBox">
            <Setter Property="MinWidth" Value="300" />
            <Setter Property="MinHeight" Value="250" />
            <Setter Property="ItemTemplate">
                <Setter.Value>
                    <DataTemplate >
                        <StackPanel Orientation="Horizontal" Height="64" >
                            <Ellipse Height="48" Width="48" VerticalAlignment="Center">
                                <Ellipse.Fill>
                                    <ImageBrush ImageSource="{Binding ImageSource}"/>
                                </Ellipse.Fill>
                            </Ellipse>
                            <StackPanel Orientation="Vertical" VerticalAlignment="Center" Margin="12,0,0,0">
                                <TextBlock Text="{Binding Name}" FontSize="14"  />
                                <TextBlock Text="{Binding Link}" FontSize="10" />
                            </StackPanel>
                        </StackPanel>
                    </DataTemplate>
                </Setter.Value>
            </Setter>
        </Style>
    </Page.Resources>

    <Grid>
        <RichTextBoxAdv:SfRichTextBoxAdv x:Name="richTextBoxAdv" ManipulationMode="All" LayoutType="Continuous"
                                         xmlns:RichTextBoxAdv="using:Syncfusion.UI.Xaml.RichTextBoxAdv"/>
    </Grid>
	
{% endhighlight %}
{% highlight C# %}
 ISuggestionProvider suggestionProvider01 = new NameSuggestionProvider();
            suggestionProvider01.MentionCharacter = '#';
            suggestionProvider01.SuggestionBoxStyle = this.Resources["SuggestionBoxStyle01"] as Style;
            List<NameSuggestionItem> suggestionItems01 = new List<NameSuggestionItem>();
            NameSuggestionItem suggestionItem01 = new NameSuggestionItem();
            suggestionItem01.Name = "Desktop App";
            suggestionItem01.Link = "10 queries";
            suggestionItems01.Add(suggestionItem01);

            suggestionItem01 = new NameSuggestionItem();
            suggestionItem01.Name = "Mobile App";
            suggestionItem01.Link = "13 queries";
            suggestionItems01.Add(suggestionItem01);

            suggestionItem01 = new NameSuggestionItem();
            suggestionItem01.Name = "Web App";
            suggestionItem01.Link = "15 queries";
            suggestionItems01.Add(suggestionItem01);

            suggestionItem01 = new NameSuggestionItem();
            suggestionItem01.Name = "Library";
            suggestionItem01.Link = "8 queries";
            suggestionItems01.Add(suggestionItem01);

            (suggestionProvider01 as NameSuggestionProvider).ItemsSource = suggestionItems01;
            richTextBoxAdv.SuggestionSettings.SuggestionProviders.Add(suggestionProvider01);

            ISuggestionProvider suggestionProvider = new NameSuggestionProvider();
            suggestionProvider.SuggestionBoxStyle = this.Resources["SuggestionBoxStyle"] as Style;
            List<NameSuggestionItem> suggestionItems = new List<NameSuggestionItem>();
            NameSuggestionItem suggestionItem = new NameSuggestionItem();
            suggestionItem.Name = "Nancy Davolio";
            suggestionItem.Link = "mailto:nancy.davolio@northwindtraders.com";
            BitmapImage bitmapImage = new BitmapImage(new Uri(new DirectoryInfo(@"ms - appx:..\..\Assets\People_Circle0.png").FullName));
            suggestionItem.ImageSource = bitmapImage;
            suggestionItems.Add(suggestionItem);

            suggestionItem = new NameSuggestionItem();
            suggestionItem.Name = "Andrew Fuller";
            suggestionItem.Link = "mailto:andrew.fuller@northwindtraders.com";
            bitmapImage = new BitmapImage(new Uri(new DirectoryInfo(@"ms - appx:..\..\Assets\People_Circle5.png").FullName));
            suggestionItem.ImageSource = bitmapImage;
            suggestionItems.Add(suggestionItem);


            suggestionItem = new NameSuggestionItem();
            suggestionItem.Name = "Steven Buchanan";
            suggestionItem.Link = "mailto:steven.buchanan@northwindtraders.com";
            bitmapImage = new BitmapImage(new Uri(new DirectoryInfo(@"ms - appx:..\..\Assets\People_Circle18.png").FullName));
            suggestionItem.ImageSource = bitmapImage;
            suggestionItems.Add(suggestionItem);

            (suggestionProvider as NameSuggestionProvider).ItemsSource = suggestionItems;
            richTextBoxAdv.SuggestionSettings.SuggestionProviders.Add(suggestionProvider);
			
{% endhighlight %}
{% endtabs %}

N> [View sample in GitHub]()

## Display a message when suggestions are empty
When the entered item is not in the suggestion list, suggestion box displays a text indicating that “We couldn’t find the person you were looking for.”. The text to be displayed for this can be customized using the SuggestionBoxErrorMessage property in resource file (.resx). 
•	Right click your project and add new folder named Resources.
•	Add [default resource file]() of SfRichTextBoxAdv control into Resources folder.

![Display message](Automatic-Suggestion_images/autosuggestion5.PNG)

![Display message](Automatic-Suggestion_images/autosuggestion4.PNG)


## Custom suggestion provider
By default, we have implemented ‘NameSuggestionProvider’ as suggestion provider. But you can implement your own suggestion provider inheriting from [ISuggestionProvider](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.RichTextBoxAdv.ISuggestionProvider.html). Which helps you to customizing the search and insert selected item functionalities.

The following sample code demonstrates how to create own suggestion provider inherited from ISuggestionProvider.
{% tabs %}
{% highlight Xaml %}
<Page.Resources>
        <Style x:Key="SuggestionBoxStyle" TargetType="ListBox">
            <Setter Property="MinWidth" Value="300" />
            <Setter Property="MinHeight" Value="250" />
            <Setter Property="ItemTemplate">
                <Setter.Value>
                    <DataTemplate >
                        <StackPanel Orientation="Horizontal" Width="200">
                            <StackPanel Orientation="Vertical" VerticalAlignment="Center" Margin="12,0,0,0">
                                <TextBlock Text="{Binding Name}" FontSize="14"  />
                            </StackPanel>
                        </StackPanel>
                    </DataTemplate>
                </Setter.Value>
            </Setter>
        </Style>
    </Page.Resources>
    
    <Grid>
        <RichTextBoxAdv:SfRichTextBoxAdv x:Name="richTextBoxAdv" ManipulationMode="All" LayoutType="Continuous"
                                         xmlns:RichTextBoxAdv="using:Syncfusion.UI.Xaml.RichTextBoxAdv"/>
    </Grid>
	
{% endhighlight %}
{% highlight C# %}
ISuggestionProvider suggestionProvider01 = new NameSuggestionProvider();
            suggestionProvider01.MentionCharacter = '#';
            suggestionProvider01.SuggestionBoxStyle = this.Resources["SuggestionBoxStyle"] as Style;
            List<NameSuggestionItem> suggestionItems01 = new List<NameSuggestionItem>();
            NameSuggestionItem suggestionItem01 = new NameSuggestionItem();
            suggestionItem01.Name = "Desktop App";
            suggestionItems01.Add(suggestionItem01);

            suggestionItem01 = new NameSuggestionItem();
            suggestionItem01.Name = "Mobile App";
            suggestionItems01.Add(suggestionItem01);

            suggestionItem01 = new NameSuggestionItem();
            suggestionItem01.Name = "Web App";
            suggestionItems01.Add(suggestionItem01);

            suggestionItem01 = new NameSuggestionItem();
            suggestionItem01.Name = "Library";
            suggestionItems01.Add(suggestionItem01);

            suggestionItem01 = new NameSuggestionItem();
            suggestionItem01.Name = "Others";
            suggestionItems01.Add(suggestionItem01);

            (suggestionProvider01 as NameSuggestionProvider).ItemsSource = suggestionItems01;
            richTextBoxAdv.SuggestionSettings.SuggestionProviders.Add(suggestionProvider01);
			
{% endhighlight %}
{% endtabs %}

N> [View sample in GitHub]()


## Custom Search
In default searching, it lists the items which contains the typed text. But you can modify the searching like lists the items starts or ends with typed text, by implementing your own suggestion provider and overriding the Search method.

<table><tr><td>Search – contains</td><td>Search – starts with</td></tr><tr><td><img src="Automatic-Suggestion_images/autosuggestion8.PNG"/></td><td><img src="Automatic-Suggestion_images/autosuggestion9.PNG"/></td></tr></table>


The following sample code demonstrates how to override search operation in your suggestion provider.
{% tabs %}
{% highlight C# %}

{% endhighlight %}
{% endtabs %


## Custom insert selected item
By default, the selected item from the suggestions list is inserted as hyperlink. But you can insert it as plain text or without link, by implementing your own suggestion provider and overriding the “InsertSelectedItem” method.

![Custom Insert](Automatic-Suggestion_images/autosuggestion10.PNG)

The following sample code demonstrates how to override insert selected item operation in your suggestion provider.
{% tabs %}
{% highlight C# %}

{% endhighlight %}
{% endtabs %}

N> This feature is supported from V18.4.0.30.

[View Sample in GitHub]()
 


