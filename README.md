# Instagram Feed Compose

A UI recreation of the Instagram feed screen built entirely in **Jetpack Compose**, focused on practicing declarative UI composition, lazy lists, and component decomposition rather than backend integration.

## Features

- Scrollable feed combining a horizontal stories row and a vertical list of posts in a single `LazyColumn`.
- Reusable, self-contained composables: `StoriesRow` and `PostCard`, each driven by simple immutable data models (`Story`, `Post`).
- Stateless components with event callbacks (e.g. `onLikeClick`) lifted up to the screen level, keeping UI state ownership explicit.
- Custom top app bar replicating Instagram's wordmark styling and action icons (Material Icons Extended).
- Static in-memory `DataSource` standing in for a backend, so the UI logic can be exercised in isolation.

## Tech stack & architecture

| Layer | Technology |
|---|---|
| UI | Jetpack Compose, Material 3, Material Icons Extended |
| Image loading | Coil (Compose + OkHttp integration) |
| Language | Kotlin |
| Build | Gradle Kotlin DSL, version catalogs (`libs.versions.toml`) |

```
model/          -> Immutable data classes (Post, Story)
data/           -> In-memory DataSource used as a fake data layer
ui/components/  -> Reusable composables (PostCard, StoriesRow)
ui/screens/     -> Screen-level composition (FeedScreen)
```

## Getting started

**Requirements:** Android Studio (current stable), JDK 17+, Android SDK with API 36.

```bash
git clone https://github.com/eliangilsierra/instagram-feed-compose.git
cd instagram-feed-compose
./gradlew assembleDebug
```

Open the project in Android Studio and run the `app` configuration on an emulator or device (minSdk 26).

## Academic context

Developed as an exercise for the **Desarrollo de Aplicaciones Móviles** course, taught by professor **Fabián Enrique Suárez Carvajal** — Maestría en Gestión, Aplicación y Desarrollo de Software (MGADS), Universidad Autónoma de Bucaramanga (UNAB).

## License

MIT — see [LICENSE](LICENSE).
