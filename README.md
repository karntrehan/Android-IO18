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
    * [AppCompat / Support Library / AndroidX](#appcompat) :package: - Handle app behaviour on older versions of Android efficiently
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
### a.k.a SupportLibrary a.k.a AndroidX
[Webpage](https://developer.android.com/topic/libraries/support-library/) | [Video](https://www.youtube.com/watch?v=jdKUm8tGogw)

* Support libraries will now be called AndroidX (Android Extensions)
* Are going to be a part of Android Jetpack
* **Changes**
    * Feature-based artifacts. eg - `ViewPager` will have its own dependency rather than being bundled with `support-v4`
    * **Versioning to be reset from 28.0.0 to 1.0.0**
    * Strict semantic versioning (Major.Minor.BugFix) i.e. - everything on 1.4 will work on 1.5 till 2.0. Breaking changes only on Major versions
    * **Per artifact versioning** i.e. RecyclerView could be on 1.4 and ViewPager could be on 1.2
    * **Artifact names to be changed**. API specific info like v4, v7 to be dropped and replaced with `androidx.<feature>:<feature>-<sub-feature>`
* **Migration**
    * Automated tool in Android Studio 3.2 Canary 15+
* **New Releases**
    * [RecyclerView Selection](https://developer.android.com/reference/androidx/recyclerview/selection/package-summary) - Allow users to select multiple elements in your `RecyclerView`. (Like Google Photos)
    * [RecyclerView ListAdapter](https://developer.android.com/reference/android/support/v7/recyclerview/extensions/ListAdapter) - Simpler way to use DiffUtil with animated updates and concurrency support on `RecyclerView`
    * androidx.webkit - Provides access to latest `WebView` platform APIs
    * androidx.browser - Renamed from Chrome custom-tabs.
    * HEIF format images support - Coming soon to older versions
    * [Material Components](https://github.com/material-components/material-components-android) - Use components following Material Design guidelines easily in your app. Includes:
        * TextFields
        * TextInputs
        * Button
        * BottomAppBar - **Actions in app**
        * BottomNavigationBar - **Sections in app**
        * MaterialCardView


## AndroidKTX
[Webpage](https://developer.android.com/kotlin/ktx) | [Video](https://www.youtube.com/watch?v=st1XVfkDWqk) | [Source code](https://github.com/android/android-ktx)

* An Android specific Kotlin extension library part of Android Jetpack
* Abstracts Android boilerplate code into extension functions making Kotlin code idiomatic, consize and safer
* Reduces the need for multiple confusing Util classes and adds functionality directly to `String`, `ViewGroup`, `View`, `Color`, `Fragments` etc 
* Contains extensions to elements only in the Android framework
* Has extensions for core framework elements, fragments, palette, collections, lifecycle-reativestreams,sqlite, navigation and work-manager.

#### Articles
* [Exploring KTX for Android - Joe Birch](https://medium.com/exploring-android/exploring-ktx-for-android-13a369795b51)

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
    * **Supports data binding in Instant Apps**
* **Room**
    * Room 1.1 has better support for threading
    * Due to threading and WriteAheadLogging (WAL) **queries to different tables would run in parallel rather than serially**
    * `@RawQuery` helps you create queries at run-time allowing you to query columns dynamically.
        ```kotlin
        @RawQuery
        fun getHouses(query:SimpleSQLiteQuery): List<Houses>
        ```
* **What's next?**
    * Lifecycle aware tools in Android studio - like NavigationEditor
    * **Adding templates** into Android studio for `ViewModel`
    * More architecture components into Jetpack
    * **Make other Google APIs "architecture-components-aware"**
    * Sample apps and Codelabs would be **refactored** to use architecture components
    * Areas under lens:
        * Error Handling
        * **Saved State**
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


# Contribution
Looking for a lot of contributions! 
Kindly refer the [Contribution](CONTRIBUTING.md) guidelines for smoother contributions.