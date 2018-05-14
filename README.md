# Android @ Google I/O 2018
At the Google I/O 2018 there were various Android related launches, talks and discussions. Here is one attempt to bring all of the updates under one page for fellow Android Developers to refer and learn.

## Android Jetpack :new:

### [Webpage](https://developer.android.com/jetpack/) | [Videos](https://www.youtube.com/results?search_query=android+jetpack)

*A set of libraries, tools and architectural guides to help make it quick and easy to build great Android apps.*

* Brings development tools, components, best / recommended practises, recommended app behaviours and common UI elements together under one roof for developer reference and usage.
* Contains 4 major components each of which (and their sub-components) can be used individually.
* Cannot be used as a dependency or a library. Is just an umbrella term for all the libraries maintained by Google to make it easier and faster to develop apps.

### Components
* **Foundation** - Handles Android device fragmentation efficiently and help writing concise, testable code
    * [AppCompat](#appcompat) :package: - Handle app behaviour on older versions of Android efficiently
    * [AndroidKTX](#androidktx) :new: - Android specific extensions to write consizer Kotlin code
    * [Multidex](https://developer.android.com/studio/build/multidex.html) - Cross the 65K limit smoothly
    * [Test](https://developer.android.com/topic/libraries/testing-support-library/index.html) - Test your functions and Android UI easily

* **Architecture** - Architect your app to follow best and recommended practises from Google
    * [Databinding](https://developer.android.com/topic/libraries/data-binding/) - Cut down on `findViewById`s and make data observing / reactive UI elements
    * [Lifecycle](https://developer.android.com/topic/libraries/architecture/lifecycle) - Create lifecycle aware components
    * [LiveData](https://developer.android.com/topic/libraries/architecture/livedata) - A observable stream of data your Activities & Fragments can react to
    * [Navigation](#navigation) :new: - Define in-app navigation stacks in a single, concise testable file
    * [Paging](#paging) :package: - Paginate loading data from data sources
    * [Room](https://developer.android.com/topic/libraries/architecture/room) - An SQLlite ORM to handle database management in your apps
    * [ViewModel](https://developer.android.com/topic/libraries/architecture/viewmodel) - Handle data effectively around lifecycle changes of Android components
    * [WorkManager](#workmanager) :new: - Run parameterized background tasks efficiently

* **Behavior** - Recommended behaviour for common use cases and tools to achieve them
    * [Download Manager](https://developer.android.com/reference/android/app/DownloadManager) - Handle large data downloads
    * [Media & Playback](https://developer.android.com/guide/topics/media/mediaplayer.html) - Effectively support media playback and Google cast
    * [Notifications](https://developer.android.com/guide/topics/ui/notifiers/notifications.html) - Show notifications across all versions of Android
    * [Permissions](https://developer.android.com/guide/topics/permissions/index.html) - Check and request permissions effectively
    * [Sharing](https://developer.android.com/training/sharing/shareaction) - Allow users to share to your app and directly to other users on your platform
    * [Slices](#slices) :new: - Allow Google Search to launch intents into your app with highlights triggering the user action

* **UI** - Common UI elements to build effective UIs on different Android versions and platforms
    * [Animation & Transitions](https://developer.android.com/training/animation/) - Build smooth & transitioning UIs
    * [Auto](https://developer.android.com/auto) - Build apps for Android Auto with ease
    * [Emoji](https://developer.android.com/guide/topics/ui/look-and-feel/emoji-compat) - Add emojis to your app and support older devices effectly
    * [Fragment](https://developer.android.com/guide/components/fragments) - Break your UI into re-usable components
    * [Layout](https://developer.android.com/guide/topics/ui/declaring-layout) - Build intuitive and performant UIs
    * [Palette](https://developer.android.com/training/material/palette-colors) -  Pull useful information from images and play with your UI
    * [TV](https://developer.android.com/tv) - Build apps for Android TV with ease
    * [WearOS by Google](https://developer.android.com/wear) - Build apps for WearOS

## AppCompat
[Webpage](https://developer.android.com/topic/libraries/support-library/packages#v7-appcompat) | [Video](https://www.youtube.com/watch?v=jdKUm8tGogw)

## AndroidKTX
[Webpage](https://developer.android.com/kotlin/ktx) | [Video](https://www.youtube.com/watch?v=st1XVfkDWqk) | [Source code](https://github.com/android/android-ktx)

* An Android specific Kotlin extension library part of Android Jetpack
* Abstracts Android boilerplate code into extension functions making Kotlin code idiomatic, consize and safer
* Reduces the need for multiple confusing Util classes and adds functionality directly to `String`, `ViewGroup`, `View`, `Color`, `Fragments` etc 
* Contains extensions to elements only in the Android framework
* Has extensions for core framework elements, fragments, palette, collections, lifecycle-reativestreams,sqlite, navigation and work-manager.

#### Articles
* [Exploring KTX for Android - Joe Birch](https://medium.com/exploring-android/exploring-ktx-for-android-13a369795b51)

#### Samples

## Navigation
[Webpage](https://developer.android.com/topic/libraries/architecture/navigation/) | [Video](https://www.youtube.com/watch?v=8GCXtCjtg40)

## Paging
[Webpage](https://developer.android.com/topic/libraries/architecture/paging/) | [Video](https://www.youtube.com/watch?v=BE5bsyGGLf4)

## WorkManager
[Webpage](https://developer.android.com/topic/libraries/architecture/workmanager) | [Video](https://www.youtube.com/watch?v=IrKoBFLwTN0)

## Slices
[Webpage](https://developer.android.com/guide/slices/) | [Video](https://www.youtube.com/watch?v=a7IVH5aNwwc)

## App Bundle
[Webpage](https://developer.android.com/guide/app-bundle/) | [Video](https://www.youtube.com/watch?v=bViNOUeFuiQ)
- An Android App Bundle is a new upload format that includes all your app’s compiled code and resources, but defers APK generation and signing to Google Play.
- It uses Google Play’s new app serving model, called Dynamic Delivery. It will generate apk based on the user's device configuration  such as screen density, CPU architecture, locale etc. Your user downloads only resources required for his/her device.
- There will be three apks: 
   - **Base APK:** This APK contains code and resources that all other split APKs can access and provides the basic functionality of your app. 
   - **Configuration APKs:** It includes resources for diffrent screen density, CPU architecture, locale etc.
   - **Dynamic feature APKs:** These are the APKs that are not required at the install time but it will be downloaded and installed in real-time when the feature is required.
- Android Studio 3.2 provides an option to configure your project for Dynamic Delivery while generating signed apk. 
- In order to use App Bundle feature, you must enroll in the [App Signing](https://support.google.com/googleplay/android-developer/answer/7384423?hl=en ) on Google Play console.
  

# Contribution
Looking for a lot of contributions! 
Kindly refer the [Contribution](CONTRIBUTING.md) guidelines for smoother contributions.
