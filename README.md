<<<<<<< HEAD
# Media Manager — Android (Kotlin + Jetpack Compose)

A fully-featured Android media management app built with **Kotlin**, **Jetpack Compose**, and **Material 3 Expressive** design. Targets **API 35 (Android 15)**.

---

## Features

| Feature | Details |
|---|---|
| **Photo browser** | Grid view, search, sort (date / name / size), multi-select |
| **Video browser** | Grid view with duration badge + play overlay, search, sort, multi-select |
| **Audio browser** | List view with artist / album meta, search, sort, multi-select |
| **Home dashboard** | Summary cards per media type with item count & total size |
| **Material 3 Expressive** | Dynamic color (Material You), spring-motion animations, large collapsing top bar |
| **Edge-to-edge** | Full window insets with transparent status bar |
| **Permission flow** | Graceful runtime permission request screen (Android 13+ scoped media) |
| **Search & filter** | Per-screen search bar with animated sort chips |
| **Selection mode** | Long-press or tap to enter multi-select; contextual action bar |

---

## Tech Stack

- **Language**: Kotlin 1.9
- **UI**: Jetpack Compose (BOM 2024.06)
- **Theme**: Material 3 / Material Expressive with dynamic color
- **Navigation**: Navigation Compose
- **ViewModel**: `AndroidViewModel` + `StateFlow`
- **Media**: `MediaStore` via a coroutine-based `MediaRepository`
- **Image loading**: Coil 2
- **Permissions**: Accompanist Permissions
- **Build**: Gradle 8.6 with Kotlin DSL + version catalog (`libs.versions.toml`)
- **Min SDK**: 29 (Android 10) · **Target / Compile SDK**: 34 (Android 14)

---

## Project Structure

```
MediaManagerApp/
├── gradle/
│   ├── libs.versions.toml          # Centralized dependency catalog
│   └── wrapper/
│       └── gradle-wrapper.properties
├── build.gradle.kts                # Root build script
├── settings.gradle.kts
└── app/
    ├── build.gradle.kts            # App-level build script
    ├── proguard-rules.pro
    └── src/
        ├── main/
        │   ├── AndroidManifest.xml
        │   ├── java/com/example/mediamanager/
        │   │   ├── MainActivity.kt
        │   │   ├── data/
        │   │   │   ├── MediaRepository.kt      # MediaStore queries (coroutines)
        │   │   │   └── model/
        │   │   │       └── MediaItem.kt        # Sealed class hierarchy + extensions
        │   │   ├── navigation/
        │   │   │   └── NavGraph.kt             # Navigation host + routes
        │   │   ├── ui/
        │   │   │   ├── components/
        │   │   │   │   ├── SharedComponents.kt # SearchBar, SortChips, EmptyState…
        │   │   │   │   └── MediaCards.kt       # PhotoCard, VideoCard, AudioRow
        │   │   │   ├── screens/
        │   │   │   │   ├── HomeScreen.kt
        │   │   │   │   ├── PhotosScreen.kt
        │   │   │   │   ├── VideosScreen.kt
        │   │   │   │   └── AudioScreen.kt
        │   │   │   └── theme/
        │   │   │       ├── Color.kt
        │   │   │       ├── Type.kt
        │   │   │       └── Theme.kt            # Dynamic color + dark/light
        │   │   └── viewmodel/
        │   │       └── MediaViewModel.kt       # StateFlow, sort/filter helpers
        │   └── res/
        │       ├── drawable/                   # Vector launcher icons
        │       ├── mipmap-*/                   # Adaptive icon per density
        │       ├── values/
        │       │   ├── strings.xml
        │       │   └── themes.xml              # XML window theme (pre-Compose)
        │       └── xml/
        │           └── file_paths.xml          # FileProvider paths
        ├── test/                               # JUnit unit tests
        └── androidTest/                        # Instrumented tests
```

---

## Getting Started

### Prerequisites
- Android Studio Hedgehog (2023.1.1) or newer
- JDK 17+
- Android device / emulator running API 29+

### Steps
```bash
# 1. Open the project in Android Studio
File → Open → MediaManagerApp/

# 2. Sync Gradle
# Android Studio will sync automatically, or run:
./gradlew app:dependencies

# 3. Build & run
./gradlew assembleDebug
# or press the Run ▶ button in Android Studio
```

### Run unit tests
```bash
./gradlew test
```

### Run instrumented tests
```bash
./gradlew connectedAndroidTest
```

---

## Permissions

| Permission | API level | Purpose |
|---|---|---|
| `READ_MEDIA_IMAGES` | 33+ | Browse photos |
| `READ_MEDIA_VIDEO` | 33+ | Browse videos |
| `READ_MEDIA_AUDIO` | 33+ | Browse audio |
| `READ_EXTERNAL_STORAGE` | ≤32 | Legacy fallback |
| `MANAGE_MEDIA` | 31+ | Delete / modify via MediaStore |

---

## Extending the App

- **Delete support**: Hook up the `Delete` icon button in each screen's top bar to `MediaStore.createDeleteRequest()` (requires `MANAGE_MEDIA` or `createWriteRequest`).
- **Share**: Use `Intent.ACTION_SEND` with the item URI via `FileProvider`.
- **Albums/Buckets**: Group photos by `BUCKET_DISPLAY_NAME` using a `LazyVerticalGrid` with sticky headers.
- **Dark mode toggle**: Pass `darkTheme = false/true` into `MediaManagerTheme`.

---

## License

Apache 2.0 — see `LICENSE` for details.
=======
# android-media-manager
A media manager for Android. Developed in Kotlin, Jetpack Compose and Gradle. It uses API 35. But minimum API required to run is API 29. It is Material Expressive compatible. 
This application is strictly local only and Android only.
#Permissions 
All files
This application is not signed by Google so it may ask to scan with Play Protect. You may dismiss the scan or scan it. 
If you scan it, it is very likely to return "This application is looking safe"
#Compile from source
To compile it from source
You must have SDKMAN!, Git, Gradle 9.4, JDK 21 installed
First, download Android SDK and API 35
Then open the terminal with ctrl+alt+t
Then run
#bash
sudo apt install -y default-jdk git #This is for Ubuntu 24.04 LTS 
#clone the repo 
git clone https://github.com/swastikchatterjee2014/android-media-manager.git 
#Compile 
cd MediaManagerApp
zsh build.zsh
License - GNU Affero General Public License version 3 (AGPLv3)
For more details, see LICENSE.txt
>>>>>>> 6b2a6ef38567542c984f428d793c56d9035fa5e6
