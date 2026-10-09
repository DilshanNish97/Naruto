# 🍥 Naruto Character Browser

An Android app that fetches anime characters from a public REST API and displays them in an image grid, built with **Jetpack Compose** and **MVVM** architecture.

## 📱 Features
- Fetches the character list from the [NarutoDB API](https://narutodb.xyz/) and displays it in a 2-column grid
- Loads character images asynchronously, safely skipping characters with no image
- Handles loading, error, and success states through a single UI state object, with the actual error message shown to the user
- Material 3 theming with edge-to-edge display and `Scaffold` safe-area padding

## 🛠️ Tech Stack
| Area | Technology |
|---|---|
| Language | Kotlin |
| UI | Jetpack Compose, Material 3, `Scaffold`, `LazyVerticalGrid` |
| Architecture | MVVM (`ViewModel` + Compose state) |
| Async | Kotlin Coroutines (`viewModelScope`) |
| Networking | Retrofit, Gson converter |
| Image loading | Coil |
| Min SDK | 24 (Android 7.0) |

## 🏗️ Architecture
```
MainActivity (Scaffold)
 └── CharacterScreen (Compose UI)
      └── MainViewModel  ──►  ApiService (Retrofit)  ──►  NarutoDB API
           └── NarutoState (loading / list / error)
```
The `ViewModel` exposes a single immutable state object. The UI observes it and shows a progress indicator while loading, the error message on failure, or the character grid on success.

## 🚀 Getting Started
1. Clone the repository
   ```bash
   git clone https://github.com/DilshanNish97/Naruto.git
   ```
2. Open it in Android Studio
3. Run it on an emulator or device (API 24+)

No API key is required.

## 🔮 Planned Improvements
- Character detail screen with navigation
- Pagination for the full character list
- Repository layer and dependency injection with Hilt
- Unit tests for the ViewModel

## ⚠️ Disclaimer
This is a non-commercial learning project. Naruto and all related characters and images belong to their respective copyright owners. Character data and images come from the third-party NarutoDB API.
