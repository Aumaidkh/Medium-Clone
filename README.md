
# Medium Clone App

This is a project for building a Medium-style application using **Jetpack Compose** and a **feature-based multi-modular architecture** in Kotlin. The app includes authentication, article management, a user profile, and a search function.

## Project Structure

The project is divided into modules based on features and core utilities. This approach enhances scalability, organizes code, and optimizes build times.

### `app/`

The `app` module serves as the main entry point of the application. It includes dependency injection setup, centralized navigation, and theming. This module depends on all other modules to bring together the app's functionality.

- **`di/`**: Contains application-wide dependency injection (DI) modules, set up with Hilt.
- **`navigation/`**: Manages navigation routes and sets up the navigation graph, connecting feature modules.
- **`ui/`**: Holds shared UI components, styles, and themes for a consistent design across the app.
- **`MainActivity.kt`**: The main entry point for the app, which initializes the navigation graph and theme.

### `modules/`

Each major feature and core functionality is encapsulated in its own module under the `modules` directory, following feature-based modularization.

#### `core/`

The `core` modules include shared functionality such as data models, network configuration, utilities, and base repository interfaces, which are used across the app.

- **`network/`**: Handles network configurations, setting up Retrofit, OkHttp, or other network libraries. This module also exposes API interfaces.
- **`data/`**: Defines common data models, base repository interfaces, and any shared data logic.
- **`utils/`**: Contains utility classes, constants, and extension functions that can be reused throughout the app.

#### `auth/`

The `auth` module is responsible for user authentication. It includes login, signup, and password reset functionality.

- **`login/`**: The login screen and related logic.
- **`signup/`**: Handles user signup with necessary form validation and authentication.
- **`resetPassword/`**: Provides functionality to reset the user's password with form and verification flows.

#### `feed/`

The `feed` module handles the home feed, displaying articles retrieved from the backend. It includes pagination and UI elements for a smooth browsing experience.

- **`ui/`**: Composables for feed-related UI components, such as lists, items, and article previews.
- **`data/`**: Feed-specific repositories and models that interact with the core data layer to fetch articles.

#### `profile/`

The `profile` module manages user profiles, allowing users to view and edit their profile information.

- **`editProfile/`**: UI and logic for editing the user's profile, including fields for bio, profile picture, etc.
- **`viewProfile/`**: UI and logic for displaying the user’s profile, including articles authored by them and general account details.

#### `article/`

The `article` module manages the lifecycle of articles, including creation, editing, and viewing articles.

- **`createArticle/`**: UI and business logic for creating new articles, including rich text editing and form validation.
- **`editArticle/`**: UI and business logic for editing existing articles, allowing users to modify content.
- **`viewArticle/`**: UI and logic for viewing individual articles, including reading modes, like/dislike features, and comment integration.

#### `notifications/`

The `notifications` module handles notification settings and displays notifications to the user, including push and local notifications.

#### `search/`

The `search` module provides a search interface with a repository to query articles, profiles, and tags.

## Build Instructions

1. **Clone the Repository**: `git clone <repository_url>`
2. **Open the Project** in Android Studio.
3. **Build and Run** the project on an emulator or device.

## Contributing

Feel free to open issues or submit pull requests if you would like to contribute to this project.

---

This README provides an overview of the project structure and guidance on how to start development.
