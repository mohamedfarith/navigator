Navigator Library for Jetpack Compose
A modular, scalable, and easy-to-use navigation library designed for Jetpack Compose Android apps. This library enables a clean separation of navigation flows by organizing navigation graphs into reusable modules, perfect for apps with complex navigation structures, including tab-based navigation.

🚀 Features
Modular Navigation Graph Structure: Organize your navigation logic into separate, reusable modules.

Nested & Tab-Based Navigation: Seamlessly support complex navigation patterns, including nested graphs and tab bars.

Separation of Concerns: Keep your navigation logic separate from your UI and business logic.

Built with Kotlin & Jetpack Compose: Leverage modern Android development tools.

Route Serialization Support: Safely pass complex data between screens.

Easy to Integrate: Get up and running quickly with a simple setup.

📦 Getting Started
Step 1: Add the Library
Add the library as a Git submodule in your project's root directory:

git submodule add git@github.com:yourusername/navigator.git libs/navigator

Step 2: Include in settings.gradle.kts
Include the new library module in your settings.gradle.kts file:

include(":app")
include(":libs:navigator")

Step 3: Add the Dependency
Finally, add the dependency to your app module's build.gradle.kts file:

dependencies {
implementation(project(":libs:navigator"))
// Other dependencies...
}

🛠 Usage Example
After including the library, you can use it to create a NavHost and register each module's navigation graph. Each module provides a registerGraph function to add its navigation graph to the NavHost. This example demonstrates how you could set up a tab-based navigation structure.

@Composable
fun MainNavHost() {
val navController = rememberNavController()

    NavHost(
        navController = navController,
        startDestination = "home_graph"
    ) {
        HomeTabModule(navController).registerGraph()
        NewsTabModule(navController).registerGraph()
        VideosTabModule(navController).registerGraph()
        MoreTabModule(navController).registerGraph()
    }
}

🔧 Library Setup Details
Kotlin version: 1.8+

Jetpack Compose: 1.4+

Navigation Compose: 2.5+

Kotlin Serialization: for route data classes