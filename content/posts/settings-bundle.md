---
title: "App Settings Bundle"
date: 2019-12-30T22:28:55-04:00
draft: true
---

Apple provides developers with two options for presenting preference data, that was stored using `NSUserDefaults`, to the user: 

<br />

* Displaying the preferences inside the app through custom built UI.
* Using a Settings bundle to manage preferences from the Settings app.

<br />

While [Apple's guidelines](https://developer.apple.com/library/archive/documentation/Cocoa/Conceptual/UserDefaults/Preferences/Preferences.html) suggest using in app preferences only when these preferences need to be accessed frequently, a lot of apps tend to go this route. While there are good arguments on each side of the camp, this article isn't really about that. But I'd like to share another awesome use we found for `Settings Bundles`...

# A different use case

Many applications I've worked on have different environments (UAT, QA, Production, etc) and usually also load a remote configuration file on launch to enable or disable features remotely.

> Using remote configurations can have many benefits. We've used them to disable features that caused unexpected issues after launch, keep certain features off in new regions until our partners in those areas have fully tested them or in some cases disable some features permanently in some regions where they aren't supported.

But we can also make use of the `Settings Bundle` to toggle features on and off, change the app environment or provide our QA/Product teams with an easy way to access and change these options, allowing us to receive valuable feedback faster than before.

# OK, but how?

In Xcode, go to `File -> New -> File` and select `Settings Bundle` under the `Resource` section, select your preferred directory. You should get something like this:

![iOS Settings Bundle in the Xcode Navigator view](/img/posts/settings_bundles/settings_bundle_xcode_navigator.png)

Apple has provided some example values in the newly generated `Settings.bundle` file, but you'll want to pop over to [Apple's documentation](https://developer.apple.com/library/archive/documentation/Cocoa/Conceptual/UserDefaults/Preferences/Preferences.html) which describes the control types available to us in great detail. In short, they are: Text field, Title, Toggle Switch, Slider, Multivalue (essentially a list of values you can select one from), Group and a Child Pane (embed another `.bundle` on a new page).

For example, if we create a plist that looks like (I collapsed the 2nd and 3rd `Group` entries, as they are essentially duplicates of the first):

![An example plist file](/img/posts/settings_bundles/settings_bundle_plist.png)

Provides us with the following screenshots:

{{< gallery caption-effect="fade" >}}
    {{< figure src="/img/posts/settings_bundles/settings_bundle_settings1.png" >}}
    {{< figure src="/img/posts/settings_bundles/settings_bundle_settings2.png" >}}
{{< /gallery >}}


* Discuss how to do it, how it works, the options available to developer (settings bundle has a few different types)
* Discuss how you access values in code
* Discuss the default value issue and workarounds for it. 
