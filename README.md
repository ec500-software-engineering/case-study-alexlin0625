# EC500 - Spring 2019:  Case Studies

PROJECT: **ReactNative(Java/JS)** 
https://github.com/facebook/react-native

# Technology and Platform used for development
### What coding languages are used? Do you think the same languages would be used if the project was started today? What languages would you use for the project if starting it today? 

### What build system is used (e.g. Bazel, CMake, Meson)? What build tools / environment are needed to build (e.g. does it require Visual Studio or just GCC or ?)


### What frameworks / libraries are used in the project? At least one of these projects don’t use any external libraries or explicit threading, yet is noted for being the fastest in its category--in that case, what intrinsic language techniques is it using to get this speed.

React Native is a framework based on JSX (extension to JavaScript), ES6 based syntax, state and props. It's also based on React which is Facebook's JavaScript library for fast building user interfaces. As understanding, this development tool targets mobile platforms instead of the browser. It not only provides rich features of UIs but also supports cross platform for both iOS and Android apps development.  

# Testing: describe unit/integration/module tests and the test framework
### How are they ensuring the testing is meaningful? Do they have code coverage metrics for example?

### What CI platform(s) are they using (e.g. Travis-CI, AppVeyor)?

AppVeyor.

### What computing platform combinations are tested on their CI? E.g. Windows 10, Cygwin, Linux, Mac, GCC, Clang

# Software architecture
### How would you add / edit functionality if you wanted to? How would one use this project from external projects, or is it only usable as a standalone program?

### What parts of the software are asynchronous (if any)?

Please make diagrams as appropriate for your explanation

### How are separation of concerns and information hiding handled?

### What architectural patterns are used

### Does the project lean more towards object oriented or functional components

# Analyze two defects in the project
### Does the issue require an architecture change, or is it just adding a new function or?

### make a patch / pull request for the project to fix problem / add feature

# Demonstration application of the system
Since react-native provide broad API interfaces. I'd like to do a demo by accessing Goolge map in my react native app on an Android simulator. 
### Emulator choice:
Name: Nexus_5X_API_28

CPU/ABI: Google Play Intel Atom (x86)

Path: C:\Users\alexlin0625\.android\avd\Nexus_5X_API_28.avd

Target: google_apis_playstore [Google Play] (API level 28)
  * The emulator has to provide Google Play Service for google map to actually run in the emulator. 
### Development platforms and tools:
  * Android Studio: Android emulator.
  * Code development: Visual Studio Code(Javascript based). 
  * System OS: Windows 10.
  * API: React-Native-Map from airbnb. <https://github.com/react-native-community/react-native-maps>
      
    => provides React Native Map components for iOS + Android.

### Preparation
React-Native-Maps installation complete guide:
  * https://github.com/react-native-community/react-native-maps/blob/master/docs/installation.md

### Result
#### create and run React-Native-App

direct path to your project in either andriod studio or visual studio code, then run following. 
```bash
react-native run-android
```
build success image:
![alt text]
