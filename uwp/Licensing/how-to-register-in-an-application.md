---
layout: post
title: Overview of Syncfusion license registration - Syncfusion
description: Learn here about how to register Syncfusion UWP license key for UWP application for license validation.
platform: uwp
control: Essential Studio
documentation: ug
---

# Register Syncfusion license key in a UWP application

N> **Prerequisites:** Install the Syncfusion UWP NuGet package (for example, `Syncfusion.Licensing.UWP`, or the platform-specific control package that depends on it) from the Syncfusion NuGet feed, and ensure `Syncfusion.Licensing.dll` is referenced in your project. Licensing support is available in Syncfusion Essential Studio version 16.1.0.24 and later.

The generated license key is a string that must be registered before any Syncfusion control is initialized. The `Syncfusion.Licensing.SyncfusionLicenseProvider.RegisterLicense` method takes the license-key string as its only parameter and returns `void`. The following code registers the license.

**Registering a single license key**

{% tabs %}
{% highlight c# %}
Syncfusion.Licensing.SyncfusionLicenseProvider.RegisterLicense("YOUR LICENSE KEY");
{% endhighlight %}
{% endtabs %}

**Registering multiple license keys**

You can register multiple license keys using either a comma (,) or a semicolon (;) as the separator between keys.

{% tabs %}
{% highlight c# %}
Syncfusion.Licensing.SyncfusionLicenseProvider.RegisterLicense("YOUR LICENSE KEY_1,YOUR LICENSE KEY_2,...");
{% endhighlight %}
{% endtabs %}

or

{% tabs %}
{% highlight c# %}
Syncfusion.Licensing.SyncfusionLicenseProvider.RegisterLicense("YOUR LICENSE KEY_1;YOUR LICENSE KEY_2;...");
{% endhighlight %}
{% endtabs %}

N> * Place the license key between double quotes. Also, ensure that Syncfusion.Licensing.dll is referenced in your project where the license key is being registered (see the package name in the Prerequisites note above).
* Syncfusion license validation is done offline during application execution and does not require internet access. Apps registered with a Syncfusion license key can be deployed on any system that does not have an internet connection.
* If the license key is missing or invalid at runtime, a license dialog or warning will appear. For troubleshooting common registration failures, refer to the [Licensing FAQ](https://help.syncfusion.com/uwp/licensing/licensing-faq).

I> Syncfusion license keys can be validated during the Continuous Integration (CI) processes to ensure proper licensing and prevent licensing errors during deployment. Refer to the [CI License Validation](https://help.syncfusion.com/uwp/licensing/licensing-faq/ci-license-validation) section for detailed instructions on how to implement it.

### UWP

You can register the license key in the **App.xaml.cs** constructor before the `InitializeComponent()` method in C#. If an **App** constructor is not available in **App.xaml.cs**, create an `App()` constructor in **App.xaml.cs** and register the license key inside it. In Visual Basic, register the license key in the **App.xaml.vb** file before the `OnLaunched` event.

{% tabs %}
{% highlight c# %}
public App()
{
	//Register Syncfusion license
	Syncfusion.Licensing.SyncfusionLicenseProvider.RegisterLicense("YOUR LICENSE KEY");

	this.InitializeComponent();
	this.Suspending += OnSuspending;
}
{% endhighlight %}

{% highlight vb %}
Public Sub New()
	'Register Syncfusion license key (runs before OnLaunched)
	Syncfusion.Licensing.SyncfusionLicenseProvider.RegisterLicense("YOUR LICENSE KEY")
End Sub

Protected Overrides Sub OnLaunched(e As Windows.ApplicationModel.Activation.LaunchActivatedEventArgs)
	' Standard OnLaunched implementation goes here
End Sub
{% endhighlight %}

{% endtabs %}