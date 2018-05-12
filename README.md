# Android @ Google I/O 2018
At the Google I/O 2018 there were various Android related launches, talks and discussions. Here is one attempt to bring all of the updates under one page for fellow Android Developers to refer and learn.

## Android Jetpack :new:

### [Webpage](https://developer.android.com/jetpack/) || [Videos](https://www.youtube.com/results?search_query=android+jetpack)

### Summary
*A set of libraries, tools and architectural guidance to help make it quick and easy to build great Android apps.*
Brings development tools, best / recommended practises, recommended app behaviours and common UI elements together under one roof for developer reference and usage.

### Components
* **Foundation** - Handles Android device fragmentation efficiently and help writing concise, testable code
    * [AppCompat](#AppCompat) :package: - Handle app behaviour on older versions of Android efficiently
    * [AndroidKTX](#AndroidKTX) :new: - Android specific extensions to write consizer Kotlin code
    * [Multidex](https://developer.android.com/studio/build/multidex.html) - Cross the 65K limit smoothly
    * [Test](https://developer.android.com/topic/libraries/testing-support-library/index.html) - Test your functions and Android UI easily

* **Architecture** - Architect your app to follow best and recommended practises from Google
    * [Databinding](https://developer.android.com/topic/libraries/data-binding/) - Cut down on `findViewById`s and make data observing / reactive UI elements
    * [Lifecycle](https://developer.android.com/topic/libraries/architecture/lifecycle) - Create lifecycle aware components
    * [LiveData](https://developer.android.com/topic/libraries/architecture/livedata) - A observable stream of data your Activities & Fragments can react to
    * [Navigation](#Navigation) :new: - Define in-app navigation stacks in a single, concise testable file
    * [Paging](#Paging) :package: - Paginate loading data from data sources
    * [Room](https://developer.android.com/topic/libraries/architecture/room) - An SQLlite ORM to handle database management in your apps
    * [ViewModel](https://developer.android.com/topic/libraries/architecture/viewmodel) - Handle data effectively around lifecycle changes of Android components
    * [WorkManager](#WorkManager) :new: - Run parameterized background tasks efficiently

* **Behavior** - Recommended behaviour for common use cases and tools to achieve them
    * [Download Manager](https://developer.android.com/reference/android/app/DownloadManager) - Handle large data downloads
    * [Media & Playback](https://developer.android.com/guide/topics/media/mediaplayer.html) - Effectively support media playback and Google cast
    * [Notifications](https://developer.android.com/guide/topics/ui/notifiers/notifications.html) - Show notifications across all versions of Android
    * [Permissions](https://developer.android.com/guide/topics/permissions/index.html) - Check and request permissions effectively
    * [Sharing](https://developer.android.com/training/sharing/shareaction) - Allow users to share to your app and directly to other users on your platform
    * [Slices](#Slices) :new: - Allow Google Search to launch intents into your app with highlights triggering the user action

* **UI** - Common UI elements to build effective UIs on different Android versions and platforms
    * [Animation & Transitions](https://developer.android.com/training/animation/) - Build smooth & transitioning UIs
    * [Auto](https://developer.android.com/auto) - Build apps for Android Auto with ease
    * [Emoji](https://developer.android.com/guide/topics/ui/look-and-feel/emoji-compat) - Add emojis to your app and support older devices effectly
    * [Fragment](https://developer.android.com/guide/components/fragments) - Break your UI into re-usable components
    * [Layout](https://developer.android.com/guide/topics/ui/declaring-layout) - Build intuitive and performant UIs
    * [Palette](https://developer.android.com/training/material/palette-colors) -  Pull useful information from images and play with your UI
    * [TV](https://developer.android.com/tv) - Build apps for Android TV with ease
    * [WearOS by Google](https://developer.android.com/wear) - Build apps for WearOS

### Details

#### AppCompat
[Webpage](https://developer.android.com/topic/libraries/support-library/packages#v7-appcompat) || [Video](https://www.youtube.com/watch?v=jdKUm8tGogw)

#### AndroidKTX
[Webpage](https://developer.android.com/kotlin/ktx) || [Video](https://www.youtube.com/watch?v=st1XVfkDWqk)

#### Navigation
[Webpage](https://developer.android.com/topic/libraries/architecture/navigation/) || [Video](https://www.youtube.com/watch?v=8GCXtCjtg40)

#### Paging
[Webpage](https://developer.android.com/topic/libraries/architecture/paging/) || [Video](https://www.youtube.com/watch?v=BE5bsyGGLf4)

#### WorkManager
[Webpage](https://developer.android.com/topic/libraries/architecture/workmanager) || [Video](https://www.youtube.com/watch?v=IrKoBFLwTN0)

#### Slices
[Webpage](https://developer.android.com/guide/slices/) || [Video](https://www.youtube.com/watch?v=a7IVH5aNwwc)