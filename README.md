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

## Architecture Components
[Webpage](https://developer.android.com/topic/libraries/architecture/) | [Video](https://www.youtube.com/watch?v=pErTyQpA390)

* 52% Android devs showed interest in using the components
* `AppCompatActivity` & `Fragment` implement `LifecycleOwner`
* **LifecycleOwner**
    * When using `Fragments` and `LiveData`+`ViewModel`, change the calls to use the Fragment lifecycle
        ```kotlin
        viewmodel.livedata.observe(viewLifeCycleOwner,Observer{
            //Handle new data
        })
        ```
* **Data binding**
    * Pass the `LifecycleOwner` to your binding initializer to allow bindings to respect Activity lifecycle
        ```kotlin
        val binding: ViewBinding = DatabindingUtil.getBinding(user)
        binding.setLifecycleOwner(viewLifeCycleOwner)
        ```
    * Data binding v2 to support incremental compiling and make multi-modular apps build faster
    * Supports data binding in Instant Apps
* **Room**
    * Room 1.1 has better support for threading
    * Due to threading and WriteAheadLogging (WAL) queries to different tables would run in parallel rather than serially
    * `@RawQuery` helps you create queries at run-time allowing you to query columns dynamically.
        ```kotlin
        @RawQuery
        fun getHouses(query:SimpleSQLiteQuery): List<Houses>
        ```
* **What's next?**
    * Lifecycle aware tools in Android studio - like NavigationEditor
    * Adding templates into Android studio for `ViewModel`
    * More architecture components into Jetpack
    * Make other Google APIs "architecture-components-aware"
    * Sample apps and Codelabs would be refactored to use architecture components
    * Areas under lens:
        * Error Handling
        * Saved State
        * Fragments & Lifecycles
        * Making components Kotlin idiomatic

## Navigation
[Webpage](https://developer.android.com/topic/libraries/architecture/navigation/) | [Video](https://www.youtube.com/watch?v=8GCXtCjtg40)

## Paging
[Webpage](https://developer.android.com/topic/libraries/architecture/paging/) | [Video](https://www.youtube.com/watch?v=BE5bsyGGLf4)

## WorkManager
[Webpage](https://developer.android.com/topic/libraries/architecture/workmanager) | [Video](https://www.youtube.com/watch?v=IrKoBFLwTN0)

## Slices
[Webpage](https://developer.android.com/guide/slices/) | [Video](https://www.youtube.com/watch?v=a7IVH5aNwwc)




## Android Things :traffic_light:

Android Things is Google's platform to support the development of Internet of Things devices. Which is now in 1.0 prodution ready version.This section has all Android Things related video Whats'new ? updates and best practises

[**Website**](https://developer.android.com/things/)   |   [**Playlist**](https://www.youtube.com/playlist?list=PLpgHr8jf5brGpgyiQpdDrGbFfbxNEbNWH)   |   [**Androiod Thing Console**](https://partner.android.com/things/console/u/0/?pli=1)


   - [**What's New ?**](https://www.youtube.com/watch?v=e_PI_Npb3-U) : Learn more about the breadth of hardware reference designs, the operating system, building apps, device management, and support from chip vendors.
   
   
   - [**Device Provisioning and Authentication**](https://www.youtube.com/watch?v=gkjV-TWLkIc&t=875s) : This talk will discuss how to support authentication, provisioning from a mobile device, and device attestation.
   
   
   - [**Android Things Console**](https://www.youtube.com/watch?v=PDBG9U-oNXY): Android Things provides a powerful developer Console that manages your device deployments. Learn more about how to take your APKs and hardware configurations, and build them into system images, which can then be rolled out to all of your devices via over-the-air updates.
   
   
   - [**System On Modules**](https://www.youtube.com/watch?v=cyphkm5XluA): How to create your own SOM carrier boards, including creating the design from scratch, working with a fabrication company, assembly and testing, and taking it all the way to production.
   
   
   - [**Build Real Consumer Devices**](https://www.youtube.com/watch?v=zBpP2kxDa2M) : This talk will walk through the journey of building consumer devices like Smart Displays using Android Things
   
   
   - [**Build effective OEM-level apps**](https://www.youtube.com/watch?v=dVtYVjGGYmE) : As an Android Things OEM. How should you structure your code? Should you use activities or services? Should the code be running in the foreground or the background? Do you package all the code into one APK, or split components up into modules? Find answers to all of these questions and more with best practices for building OEM-level apps.
   


# Contribution
Looking for a lot of contributions! 
Kindly refer the [Contribution](CONTRIBUTING.md) guidelines for smoother contributions.
