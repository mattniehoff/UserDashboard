# UserDashboard

A simple project used to illustrate clean architecture and testing in Android with Kotlin.

<img src="AppVideo.gif" alt="AppVideo" width="300" />

The app shows a dashboard of 500 users from [uinames.com](https://uinames.com). When a profile is tapped, a detail view is shown which can be dismissed with a swipe down gesture or the back button.

## Architecture

The app uses a single Activity with multiple Fragments. The activity is the Lifecycle Owner of two ViewModels, one for the dashboard and one for the detail view. These ViewModels serve as the logic for the view. All data is retrieved through a repository, which uses either a local database or a network request in order to populate data.

The ViewModels and Repository are both tested with their dependencies mocked in the unit tests.

## Installing and Testing

### Either:

Import the UserDashboard project into Android Studio and run the `app` configuration. In order to run the tests, right click the `test` folder (not the `androidTest` folder!) in the project navigator and select `'Run 'Tests' in 'jaumoTest''`.

### OR:

To build and install from the command line, make sure a device is connected to [adb](https://developer.android.com/studio/command-line/adb) and run:

    ./gradlew installDebug

To run unit tests:

	./gradlew testDebugUnitTest
	

The results of the unit tests can be found at `app/build/reports/tests/testDebugUnitTests`. In that directory, `index.html` will have the overall information on how the unit tests fared, with specific tests found in the `classes/` directory

## Built With

* [Kotlin](https://kotlinlang.org/) - The language used in the project
* [Lifecycle](https://developer.android.com/topic/libraries/architecture/lifecycle) - Used with LiveData in order to attach data to the activity/fragment lifecycle
* [LiveData](https://developer.android.com/topic/libraries/architecture/livedata) - Used to make data be Lifecycle aware, and helps persist data through the activity Lifecycle 
* [ViewModel](https://developer.android.com/topic/libraries/architecture/viewmodel) - Lifecycle aware model, which is used to create controllers that are attached to a given activity/fragment
* [Mockito](https://site.mockito.org/) - Used for mocking and injecting mock classes in tests
* [RecyclerView](https://developer.android.com/reference/android/support/v7/widget/RecyclerView) - Used to display the dashboard
* [Retrofit](https://square.github.io/retrofit/) - Used to simplify networking
* [Room](https://developer.android.com/topic/libraries/architecture/room) - Used for persistance in a SQLite database
* [Picasso](https://square.github.io/picasso/) - Image handling library used to load images asynchronously
* [Android Design Support Library](https://developer.android.com/topic/libraries/support-library/packages) - Used for the snackbar, which shows errors
* [ConstraintLayout](https://developer.android.com/reference/android/support/constraint/ConstraintLayout) - Layout used to provide complex UIs with a minimal view hierarchy
* [Dagger](https://google.github.io/dagger/) - Used for dependency injection
* [Mockito-Kotlin](https://github.com/nhaarman/mockito-kotlin/wiki) - A library used to make mockito more "kotlin-aware". Used primarily to be able to pass null objects into Mockito mocks.

## License

 ![](app/src/main/res/mipmap-xxxhdpi/ic_launcher_round.png)

Copyright (C) 2018 Boris Kachscovsky

This program is free software: you can redistribute it and/or modify it under the terms of the GNU General Public License as published by the Free Software Foundation, either version 3 of the License, or (at your option) any later version.

This program is distributed in the hope that it will be useful, but WITHOUT ANY WARRANTY; without even the implied warranty of MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. See the GNU General Public License for more details. You should have received a copy of the GNU General Public License along with this program. If not, see http://www.gnu.org/licenses/.