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
1. Node & Python 2 & JDK: Node.js for React Native command line interface. React Native also requires recent version of Java SDK as well as Python2.  
2. Install Android Studio: For Android development environment as well as Android Virtual Emulator. Alternatively, can also use Vitual Studio Code for both Java & JavaScript for code editing. 
3. Android SDK: requires Android 9 (Pie) to build React Native app with native code. 

Detailed environment variable, path and software configurations have complete guide at the following.
https://facebook.github.io/react-native/docs/getting-started

Run:
1. Create new application:
```bash
react-native init AwesomeProject
```
2. Run Android virtual Emulator: list of available Android Virtual Devices (AVDs) by opening the "AVD Manager" from within Android Studio.

3. Direct to the project created and run:
```bash
cd AwesomeProject
react-native run-android
```

### What frameworks / libraries are used in the project? At least one of these projects don’t use any external libraries or explicit threading, yet is noted for being the fastest in its category--in that case, what intrinsic language techniques is it using to get this speed.

React Native is a framework based on JSX (extension to JavaScript), ES6 based syntax, state and props. It's also based on React which is Facebook's JavaScript library for fast building user interfaces. As understanding, this development tool targets mobile platforms instead of the browser. It not only provides rich features of UIs but also supports cross platform for both iOS and Android apps development.  

# Testing: describe unit/integration/module tests and the test framework
### How are they ensuring the testing is meaningful? Do they have code coverage metrics for example?

According to FaceBook's recommendations, Jest Framework plus some additional utilities liek Enzyme can optimizing unit testing especially we are writing code in JS. Facebook stated that using Jest has 5 reasons. Minimal configuration, watches only changed files, fast, snapshot testing and coverage out of box. Detailed Jest documentation and setup refers to https://facebook.github.io/jest/. Jest configuration is very easy to set up, fit the following code inside package.json from your React Native project completes the configuration. 
```bash
"jest": {
    "preset": "react-native",
    "cacheDirectory": "./cache",
    "coveragePathIgnorePatterns": [
      "./app/utils/vendor"
    ],
    "coverageThreshold": {
      "global": {
        "statements": 80
      }
    },
    "transformIgnorePatterns": [
      "/node_modules/(?!react-native|react-clone-referenced-element|react-navigation)"
    ]
  }
```
#### Snapshot testing:

This testing is a configuration file defining your components' style, UI or props. Test case should look like following
```bash
import React from 'react';
import renderer from 'react-test-renderer';
import SomeComponent from '../SomeComponent.component';

describe('Some component', () => {
  it('renders correctly', () => {
    const tree = renderer.create(
      <SomeComponent/>
    ).toJSON();
    expect(tree).toMatchSnapshot();
  });
});
```
Whenever Jest sees this line expect(tree).toMatchSnapshot();, it is going to generate a snapshot and compare it with the previously stored snapshot. If the snapshot is not present, Jest will store the generated snap. While the screenshots don't mathc, the change you've done could be somehow unexpected or other erros need to be addressed. 

#### Enzyme:

While Snapshot testing focus more on external and visual changes, Enzyme is a JavaScript testing utility for React. The user can directly integrate Enzyme in the current Jest framework. There are three components to install, enzyme, jest-enzyme, enzyme-adapters.
```bash
yarn add enzyme jest-enzyme enzyme-adapter-react-16 enzyme-react-16-adapter-setup --dev
```
Now set it up with the following code in your package.json, then you are ready to start using Enzyme utilities. Most of the users use Shallow Renderer from Enzyme to do unit testings. The following link provides tutorial from React Native documentation. https://reactjs.org/docs/shallow-renderer.html
```bash
  {
    ...,
    "jest": {
      ...,
      "setupTestFrameworkScriptFile": "./node_modules/jest-enzyme/lib/index.js",
      "setupFiles": ["enzyme-react-16-adapter-setup"]
    }
  }
```

### What CI platform(s) are they using (e.g. Travis-CI, AppVeyor)?

AppVeyor.

### What computing platform combinations are tested on their CI? E.g. Windows 10, Cygwin, Linux, Mac, GCC, Clang

# Software architecture
### How would you add / edit functionality if you wanted to? How would one use this project from external projects, or is it only usable as a standalone program?

In React Native, you will be implementing or adding a lot of components, everything that are showing on your App could be some sort of components. For example, to add and show google map functionality is basically adding an React Native Map API originated from airbnb. Once you obtained the google map API credential, you could just add the entire map package into React Native as component. Then this is basically adding functionality to your React Native app. All components added are required to go through render to return the results. 

### What parts of the software are asynchronous (if any)?

When a React Native application is launched, it spawns up the following threading queues.

Main thread (Native Queue) - This is the main thread which gets spawned as soon as the application launches. It loads the app and starts the JS thread to execute the Javascript code. The native thread also listens to the UI events like 'press', 'touch', etc. These events are then passed to the JS thread via the RN Bridge. Once the Javascript loads, the JS thread sends the information on what needs to be rendered onto the screen. This information is used by a shadow node thread to compute the layouts. The shadow thread is basically like a mathematical engine which finally decides on how to compute the view positions. These instructions are then passed back to the main thread to render the view.

Javascript thread (JS Queue) - The Javascript Queue is the thread queue where main bundled JS thread runs. The JS thread runs all the business logic, i.e., the code we write in React Native.

Custom Native Modules - Apart from the threads spawned by React Native, we can also spawn threads on the custom native modules we build to speed up the performance of the application. For example - Animations are handled in React Native by a separate native thread to offload the work from the JS thread.

### What architectural patterns are used

![alt text](https://github.com/ec500-software-engineering/case-study-alexlin0625/blob/master/ang2-react-native.png)

Angular 2’s architecture makes it possible to render an application with various renderers including React Native. 

As mentioned before, a React Native application runs 3 threads. The main one is a JS thread where any JS code can be executed; it controls the full application. The other two run the native part of the application: the standard main UI thread, and a “shadow” thread where measuring and layout occur.

The native and JS sides communicate in both directions through a bridge. This means that there are Bridge JS APIs to access native features (network, geolocation, clipboard, etc) and  manipulate native elements, and that native events are sent back to the JS side.

Overall, React Native can be considered as a set of React components, where each component represents the corresponding native views and components. There isn't specific architectural pattern is used. There are abundance of APIs for you to add as components and the results are presented directly as UI. It's very flexible and creative mobile app development. 

### Does the project lean more towards object oriented or functional components

The project lean more towards functional components. Even though asynchronous rendering with React was strictly stuck by using class which is object oriented. But with the new Suspense API in React Native, this is not an issue anymore, functional components can now perform asynchronous calls and render data that comes from them. It basically suspends the rendering of a component while loading data from a cache. This means that our component will only show up once the whole tree is ready.

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
