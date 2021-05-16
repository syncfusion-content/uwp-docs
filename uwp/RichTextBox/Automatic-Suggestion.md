---
title: Automatic Suggestion in UWP RichTextBox control | Syncfusion
description: Learn here all about Automatic Suggestion support in Syncfusion UWP RichTextBox (SfRichTextBoxAdv) control and more.
platform: uwp
control: SfRichTextBoxAdv
documentation: ug
keywords: automatic-suggestion, @mentions
---
# Automatic Suggestion in UWP RichTextBox (SfRichTextBoxAdv)

### Automatic Suggestion functionality for using @mentions
RichTextBox control shows an inline dropdown with a list of suggested names while type the mention character (@ symbol). The list of names will filter as you type more letters. You can use up or down arrow key to move selection and Tab or Enter key to insert selected item in keyboard or use mouse to click any option in the list. The selected item from the suggestion list will be inserted as hyperlink with the display text and its respective link.

![Automatic Suggestion](Automatic-Suggestion_images/autosuggestion1.PNG)

The following sample code demonstrates how to use @mentions in RichTextBox.
{% tabs %}
{% highlight xaml %}
<Grid>
	<RichTextBoxAdv:SfRichTextBoxAdv x:Name="richTextboxadv"
									 LayoutType="Continuous">
		<RichTextBoxAdv:SfRichTextBoxAdv.SuggestionSettings>
			<RichTextBoxAdv:SuggestionSettings>
				<RichTextBoxAdv:SuggestionSettings.SuggestionProviders>
					<RichTextBoxAdv:NameSuggestionProvider ItemsSource="{x:Bind suggestionItems}">
					</RichTextBoxAdv:NameSuggestionProvider>
				</RichTextBoxAdv:SuggestionSettings.SuggestionProviders>
			</RichTextBoxAdv:SuggestionSettings>
		</RichTextBoxAdv:SfRichTextBoxAdv.SuggestionSettings>
	</RichTextBoxAdv:SfRichTextBoxAdv>
</Grid>
{% endhighlight %}
{% highlight C# %}
SfRichTextBoxAdv richTextBoxAdv = new SfRichTextBoxAdv();
ISuggestionProvider suggestionProvider = new NameSuggestionProvider();
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
bitmapImage = new BitmapImage(new Uri(new DirectoryInfo(@"ms - appx:..\..\Assets\People_Circle14.png").FullName));
suggestionItem.ImageSource = bitmapImage;
suggestionItems.Add(suggestionItem);

(suggestionProvider as NameSuggestionProvider).ItemsSource = suggestionItems;

richTextboxadv.SuggestionSettings.SuggestionProviders.Add(suggestionProvider);
{% endhighlight %}
{% highlight VB %}
Dim richTextBoxAdv As SfRichTextBoxAdv = New SfRichTextBoxAdv()
Dim suggestionProvider As ISuggestionProvider = New NameSuggestionProvider()
Dim suggestionItems As List<NameSuggestionItem> = New List<NameSuggestionItem>()

Dim suggestionItem As NameSuggestionItem = New NameSuggestionItem()
suggestionItem.Name = "Nancy Davolio"
suggestionItem.Link = "mailto:nancy.davolio@northwindtraders.com"
suggestionItem.ImageSource = "images/nancy.png"
suggestionItems.Add(suggestionItem)

suggestionItem = New NameSuggestionItem()
suggestionItem.Name = "Andrew Fuller"
suggestionItem.Link = "mailto:andrew.fuller@northwindtraders.com"
suggestionItem.ImageSource = "images/andrew.png"
suggestionItems.Add(suggestionItem)

suggestionItem = New NameSuggestionItem()
suggestionItem.Name = "Steven Buchanan"
suggestionItem.Link = "mailto:steven.buchanan@northwindtraders.com"
suggestionItem.ImageSource = "images/steven.png"
suggestionItems.Add(suggestionItem)

TryCast(suggestionProvider, NameSuggestionProvider).ItemsSource = suggestionItems
richTextBoxAdv.SuggestionSettings = New SuggestionSettings()
richTextBoxAdv.SuggestionSettings.SuggestionProviders.Add(suggestionProvider)
{% endhighlight %}
{% endtabs %}

[View sample in GitHub](https://github.com/SyncfusionExamples/UWP-RichTextBox-Examples/tree/main/Samples/Automatic%20Suggestion/Automatic%20Suggestion)

### Customize the SuggestionBox ItemTemplate and Style
By default, the drop-down window lists the filtered items as an image, display text and link. If you want to remove the image or link. You can write your own item Template.

![Modify Suggestion Box Item](Automatic-Suggestion_images/autosuggestion2.PNG)

The following sample code demonstrates how to modify the suggestion box item template and style.
{% tabs %}
{% highlight xaml %}
<Page.Resources>
	<Style x:Key="SuggestionBoxStyle" TargetType="ListBox">
		<Setter Property="MinWidth" Value="300" />
		<Setter Property="MinHeight" Value="250" />
		<Setter Property="Background" Value="#FFDBF5FB"/>
		<Setter Property="ItemTemplate">
			<Setter.Value>
				<DataTemplate>
					<StackPanel Orientation="Vertical" Height="50" VerticalAlignment="Center" Margin="12,15,0,0">
						<TextBlock Text="{Binding Name}" FontFamily="microsoft sans serif" FontSize="14"  />
						<TextBlock Text="{Binding Link}" FontFamily="microsoft sans serif" Foreground="Gray" FontSize="10" />
					</StackPanel>
				</DataTemplate>
			</Setter.Value>
		</Setter>
	</Style>
</Page.Resources>
<Grid>
	<RichTextBoxAdv:SfRichTextBoxAdv x:Name="richTextboxadv"
									 LayoutType="Continuous">
		<RichTextBoxAdv:SfRichTextBoxAdv.SuggestionSettings>
			<RichTextBoxAdv:SuggestionSettings>
				<RichTextBoxAdv:SuggestionSettings.SuggestionProviders>
					<RichTextBoxAdv:NameSuggestionProvider ItemsSource="{x:Bind suggestionItems}"
														   SuggestionBoxStyle="{StaticResource SuggestionBoxStyle}">
					</RichTextBoxAdv:NameSuggestionProvider>
				</RichTextBoxAdv:SuggestionSettings.SuggestionProviders>
			</RichTextBoxAdv:SuggestionSettings>
		</RichTextBoxAdv:SfRichTextBoxAdv.SuggestionSettings>
	</RichTextBoxAdv:SfRichTextBoxAdv>
</Grid>
{% endhighlight %}
{% endtabs %}


### Custom mention character
Any character can be used as mention character, default value is **@**.

![Mention Character](Automatic-Suggestion_images/autosuggestion3.PNG)

The following sample code demonstrates how to use ‘#’ as mention character.
{% tabs %}
{% highlight xaml %}
<Grid>
	<RichTextBoxAdv:SfRichTextBoxAdv x:Name="richTextboxadv"
									 LayoutType="Continuous">
		<RichTextBoxAdv:SfRichTextBoxAdv.SuggestionSettings>
			<RichTextBoxAdv:SuggestionSettings>
				<RichTextBoxAdv:SuggestionSettings.SuggestionProviders>
					<RichTextBoxAdv:NameSuggestionProvider MentionCharacter="#"
														   ItemsSource="{x:Bind suggestionItems}">
					</RichTextBoxAdv:NameSuggestionProvider>
				</RichTextBoxAdv:SuggestionSettings.SuggestionProviders>
			</RichTextBoxAdv:SuggestionSettings>
		</RichTextBoxAdv:SfRichTextBoxAdv.SuggestionSettings>
	</RichTextBoxAdv:SfRichTextBoxAdv>
</Grid>
{% endhighlight %}
{% highlight C# %}
SfRichTextBoxAdv richTextBoxAdv = new SfRichTextBoxAdv();
ISuggestionProvider suggestionProvider = new NameSuggestionProvider();
suggestionProvider.MentionCharacter = '#';
richTextboxadv.SuggestionSettings.SuggestionProviders.Add(suggestionProvider);
{% endhighlight %}

{% endtabs %}


### Multiple Suggestion provider
Two or more suggestion providers can be used at a time but, each suggestion provider should have different mention character. And each suggestion provider can have different item source and suggestion box style.

<table><tr><td><img src="Automatic-Suggestion_images/autosuggestion1.PNG"/><br/></td><td><img src="Automatic-Suggestion_images/autosuggestion3.PNG"/><br/></td></tr></table>

The following sample code demonstrates how to use two suggestion providers. Here we have used ‘@’ and ‘#’ as mention characters.
{% tabs %}
{% highlight xaml %}
<Page.Resources>
        <Style x:Key="SuggestionBoxStyle" TargetType="ListBox">
            <Setter Property="MinWidth" Value="300" />
            <Setter Property="MinHeight" Value="250" />
            <Setter Property="Background" Value="#FFDBF5FB"/>
            <Setter Property="ItemTemplate">
                <Setter.Value>
                    <DataTemplate>
                        <StackPanel Orientation="Vertical" Height="50" VerticalAlignment="Center" Margin="12,15,0,0">
                            <TextBlock Text="{Binding Name}" FontFamily="microsoft sans serif" FontSize="14"  />
                            <TextBlock Text="{Binding Link}" FontFamily="microsoft sans serif" Foreground="Gray" FontSize="10" />
                        </StackPanel>
                    </DataTemplate>
                </Setter.Value>
            </Setter>
        </Style>
</Page.Resources>
<Grid>
	<RichTextBoxAdv:SfRichTextBoxAdv x:Name="richTextboxadv"
									 LayoutType="Continuous">
		<RichTextBoxAdv:SfRichTextBoxAdv.SuggestionSettings>
			<RichTextBoxAdv:SuggestionSettings>
				<RichTextBoxAdv:SuggestionSettings.SuggestionProviders>
					<RichTextBoxAdv:NameSuggestionProvider ItemsSource="{StaticResource suggestionItems}">
					</RichTextBoxAdv:NameSuggestionProvider>
					<RichTextBoxAdv:NameSuggestionProvider MentionCharacter="#" 
														   ItemsSource="{StaticResource suggestionItems01}"
														   SuggestionBoxStyle="{StaticResource SuggestionBoxStyle}">
					</RichTextBoxAdv:NameSuggestionProvider>
				</RichTextBoxAdv:SuggestionSettings.SuggestionProviders>
			</RichTextBoxAdv:SuggestionSettings>
		</RichTextBoxAdv:SfRichTextBoxAdv.SuggestionSettings>
	</RichTextBoxAdv:SfRichTextBoxAdv>
</Grid>
{% endhighlight %}
{% highlight C# %}
SfRichTextBoxAdv richTextBoxAdv = new SfRichTextBoxAdv();
ISuggestionProvider suggestionProvider = new NameSuggestionProvider();		
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
bitmapImage = new BitmapImage(new Uri(new DirectoryInfo(@"ms - appx:..\..\Assets\People_Circle14.png").FullName));
suggestionItem.ImageSource = bitmapImage;
suggestionItems.Add(suggestionItem);

(suggestionProvider as NameSuggestionProvider).ItemsSource = suggestionItems;
richTextboxadv.SuggestionSettings.SuggestionProviders.Add(suggestionProvider);


ISuggestionProvider suggestionProviderAppType = new NameSuggestionProvider();
suggestionProviderAppType.SuggestionBoxStyle = this.Resources["SuggestionBoxStyle"] as System.Windows.Style;
suggestionProviderAppType.MentionCharacter = '#';
List<NameSuggestionItem> suggestionItems01 = new List<NameSuggestionItem>();

NameSuggestionItem desktopApp = new NameSuggestionItem();
desktopApp.Name = "Desktop App";
desktopApp.Link = "10 queries";
desktopApp.ImageSource = bitmapImage;
suggestionItems01.Add(desktopApp);

NameSuggestionItem mobileApp = new NameSuggestionItem();
mobileApp.Name = "Mobile App";
mobileApp.Link = "13 queries";
mobileApp.ImageSource = bitmapImage;
suggestionItems01.Add(mobileApp);

NameSuggestionItem webApp = new NameSuggestionItem();
webApp.Name = "Web App";
webApp.Link = "15 queries";
webApp.ImageSource = bitmapImage;
suggestionItems01.Add(webApp);

(suggestionProviderAppType as NameSuggestionProvider).ItemsSource = suggestionItems01;
richTextboxadv.SuggestionSettings.SuggestionProviders.Add(suggestionProviderAppType);
{% endhighlight %}
{% endtabs %}

[View sample in GitHub](https://github.com/SyncfusionExamples/UWP-RichTextBox-Examples/tree/main/Samples/Automatic%20Suggestion/Multiple%20Suggestion%20Provider)

### Display error message when suggestions are empty
When the entered item is not in the suggestion list, suggestion box displays a text indicating that “We couldn’t find the person you were looking for.”. The text to be displayed for this can be customized using the SuggestionBoxErrorMessage property in resource file (.resx). 
•	Right click your project and add new folder named Resources.
•	Add [default resource file](https://github.com/syncfusion/uwp-controls-localization-resource-files/tree/master/Syncfusion.SfRichTextBoxAdv.UWP) of RichTextBox control into Resources folder.
•	Modify the value of resource key SuggestionBoxErrorMessage in resource file.

![Display message](Automatic-Suggestion_images/autosuggestion5.PNG)

![Display message](Automatic-Suggestion_images/autosuggestion4.PNG)


### Custom suggestion provider
By default, we have implemented [NameSuggestionProvider](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.RichTextBoxAdv.NameSuggestionProvider.html) as suggestion provider. And you can implement your own suggestion provider, inheriting from [ISuggestionProvider](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.RichTextBoxAdv.ISuggestionProvider.html). Which helps you to customize the search and insert selected item functionalities.

The following sample code demonstrates how to create your own suggestion provider inherited from ISuggestionProvider.
{% tabs %}
{% highlight C# %}
internal class AppTypeSuggestionProvider : DependencyObject, ISuggestionProvider
{
#region Property
public char MentionCharacter
{
	get
	{
		return (char)GetValue(MentionCharacterProperty);
	}
	set
	{
		SetValue(MentionCharacterProperty, value);
	}
}

public Style SuggestionBoxStyle
{
	get
	{
		return (Style)GetValue(SuggestionBoxStyleProperty);
	}
	set
	{
		SetValue(SuggestionBoxStyleProperty, value);
	}
}

public IEnumerable ItemsSource
{
	get
	{
		return (IEnumerable)GetValue(ItemsSourceProperty);
	}
	set
	{
		SetValue(ItemsSourceProperty, value);
	}
}

public static DependencyProperty MentionCharacterProperty
{
	get
	{
		return mentionCharacterProperty;
	}
}

public static DependencyProperty ItemsSourceProperty
{
	get
	{
		return itemsSourceProperty;
	}
}

public static DependencyProperty SuggestionBoxStyleProperty
{
	get
	{
		return suggestionBoxStyleProperty;
	}
}
#endregion

#region Static Dependency Properties
/// <summary>
/// Identifies the MentionCharacter dependency property.
/// </summary>
private static DependencyProperty mentionCharacterProperty = DependencyProperty.Register("MentionCharacter", typeof(char), typeof(NameSuggestionProvider), new PropertyMetadata('@'));

/// <summary>
/// Identifies the ItemSource dependency property.
/// </summary>
private static DependencyProperty itemsSourceProperty = DependencyProperty.Register("ItemsSource", typeof(IEnumerable), typeof(NameSuggestionProvider), new PropertyMetadata(null));

/// <summary>
/// Identifies the SuggestionBoxStyle dependency property.
/// </summary>
private static DependencyProperty suggestionBoxStyleProperty = DependencyProperty.Register("SuggestionBoxStyle", typeof(Style), typeof(NameSuggestionProvider), new PropertyMetadata(null));
#endregion

public void Dispose()
{
	ClearValue(mentionCharacterProperty);
	if (ItemsSource != null)
	{
		foreach (NameSuggestionItem itemSource in ItemsSource)
		{
			itemSource.Dispose();
		}
		ClearValue(itemsSourceProperty);
	}
	ClearValue(suggestionBoxStyleProperty);
}

public void InsertSelectedItem(SfRichTextBoxAdv richTextBoxAdv, object selectedItem)
{
	NameSuggestionItem nameSuggestionItem = selectedItem as NameSuggestionItem;
	richTextBoxAdv.Selection.InsertText(MentionCharacter + nameSuggestionItem.Name);
}

public List<object> Search(string searchText)
{
	List<object> matchedItems = new List<object>();
	foreach (NameSuggestionItem item in ItemsSource)
	{
		if (item.Name.ToUpperInvariant().StartsWith(searchText.ToUpperInvariant()))
		{
			matchedItems.Add(item);
		}
	}
	return matchedItems;
}
}
{% endhighlight %}
{% endtabs %}

[View sample in GitHub](https://github.com/SyncfusionExamples/UWP-RichTextBox-Examples/tree/main/Samples/Automatic%20Suggestion/Custom%20Suggestion%20Provider)


### Customize search
In default searching, it list the items which contains the typed text. And you can modify the searching logic like list the items starts or ends with typed text, by implementing your own suggestion provider and overriding the Search method.

<table><tr><td>Search – contains</td><td>Search – starts with</td></tr><tr><td><img src="Automatic-Suggestion_images/autosuggestion1.PNG"/></td><td><img src="Automatic-Suggestion_images/autosuggestion6.PNG"/></td></tr></table>

The following sample code demonstrates how to override search operation in your suggestion provider.
{% tabs %}
{% highlight C# %}
public List<object> Search(string searchText)
{
	List<object> matchedItems = new List<object>();
	foreach (NameSuggestionItem item in ItemsSource)
	{
		if (item.Name.ToUpperInvariant().StartsWith(searchText.ToUpperInvariant()))
		{
			matchedItems.Add(item);
		}
	}
	return matchedItems;
}
{% endhighlight %}
{% endtabs %}


### Customize insert item
By default, the selected item from the suggestions list is inserted as hyperlink. And you can insert it as plain text or without link, by implementing your own suggestion provider and overriding the “InsertSelectedItem” method.

![Custom Insert](Automatic-Suggestion_images/autosuggestion3.PNG)

The following sample code demonstrates how to override insert selected item operation in your suggestion provider.
{% tabs %}
{% highlight C# %}
public void InsertSelectedItem(SfRichTextBoxAdv richTextBoxAdv, object selectedItem)
{
	NameSuggestionItem nameSuggestionItem = selectedItem as NameSuggestionItem;
	richTextBoxAdv.Selection.InsertText(MentionCharacter + nameSuggestionItem.Name);
}
{% endhighlight %}
{% endtabs %}

N> This feature is supported from V18.4.0.30.

[View Sample in GitHub](https://github.com/SyncfusionExamples/UWP-RichTextBox-Examples/tree/main/Samples/Automatic%20Suggestion/Custom%20Suggestion%20Provider)
 


