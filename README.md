# EC500 - Spring 2019:  Case Studies

PROJECT: **ReactNative(Java/JS)** 
https://github.com/facebook/react-native

# Technology and Platform used for development
### What coding languages are used? Do you think the same languages would be used if the project was started today? What languages would you use for the project if starting it today? 

Coding languages: Java and JavaScript

ReactNative is powerful because they languages chosen are so far still the most well-established and used in industry. Java is an OOP programming language while Java Script is an OOP scripting language. Java creates applications that run in a virtual machine or browser while JavaScript code is run on a browser only. Since pretty much all Android apps are based on java and React along with Javascript can run even the most complex of apps smoothly, the combination gives huge potentials on developing any IoT or mobile devices appplications. On top of this, the JavaScript part of the code runs on its own thread, so your app’s UI animation won’t lag, no matter how heavy the compilations. 

There's no doubt I'd choose to use Java and JavaScript to run on React Native even today especially for the CrossPlatform Compatibility on majority of React Native APIs. Even though each component will work on both Andriod and IOS, the instance has to be platform specific. When React Native package are downloaded. The package contains platform module and platform specific file extensions for Andriod and IOS, you can choose either edit the code on Vitual Studio or Andriod Studio in Andriod folder to start creating your React Native app. Respectively, develop your React Native App in IOS folder in Xcode. 

![alt text](https://github.com/ec500-software-engineering/case-study-alexlin0625/blob/master/CrossPlatform.JPG)

Picture aboves illustrates that React Native uses the same React.js framework, but writing for Android vs iOS are actually different projects with some shared code, as mentioned before, it's in different folders within your React Native App project. This also means code for each device can be written specifically for that device using entirely native components.

### What build system is used (e.g. Bazel, CMake, Meson)? What build tools / environment are needed to build (e.g. does it require Visual Studio or just GCC or ?)
There are two tools to build the React Native developing environment:

#### Expo CLI
the easiest way to get started with React Native is with Expo tools because they allow you to start a project without installing and configuring Xcode or Android Studio. Expo CLI sets up a development environment on your local machine and you can be writing a React Native app within minutes. To install Expo CLI, use the following command.
```bash
npm install -g expo-cli
```
After you installed the Expo CLI, run the following command to create a project, the name is dafault AwesomeProject.

```bash
expo init AwesomeProject
cd AwesomeProject
npm start
```
After the project is created. Install "the Expo client" app on your iOS or Android phone and connect to the same wireless network as your computer. On Android, use the Expo app to scan the QR code from your terminal to open your project. On iOS, follow on-screen instructions to get a link.

#### React Native CLI
The instructions of this build tool differs depends on your Development OS and Target OS. So far React Native allows macOS, Windows and Linux as development OS. The target OS would be either iOS or Android. I'll introduce the build tools and environment needed to run Andriod App on Windows 10.
1. Node & Python 2 & JDK: 
Node.js for React Native command line interface. React Native also requires recent version of Java SDK as well as Python2.  
2. Install Android Studio: 
For Android development environment as well as Android Virtual Emulator. Alternatively, can also use Vitual Studio Code for both Java & JavaScript for code editing. 
3. Android SDK: requires 
Android 9 (Pie) to build React Native app with native code. 

Detailed environment variable, path and software configurations have complete guide at the following.
https://facebook.github.io/react-native/docs/getting-started

Run:
1. Create new application:
```bash
react-native init AwesomeProject
```
2. Run Android virtual Emulator: 
list of available Android Virtual Devices (AVDs) by opening the "AVD Manager" from within Android Studio.
3. Direct to the project created and run:
```bash
cd AwesomeProject
react-native run-android
```

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
Since react-native provide broad API interfaces. I'd like to do a demo by accessing Goolge map in my react native app on an Android simulator. Before start doing this application, obtaining google cloud platform account and Google Map API key is needed. Also make sure the <Maps SDK for Android> API was enabled in google cloud platform.

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
![alt text](https://github.com/ec500-software-engineering/case-study-alexlin0625/blob/master/Build_Successful.JPG)

React-Native-APP emulator result:

![alt text](https://github.com/ec500-software-engineering/case-study-alexlin0625/blob/master/React-Native-App.JPG)
