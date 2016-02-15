# GAWrapper a wrapper for Google Anaytics

[![](https://img.shields.io/badge/carthage-compatible-brightgreen.svg)](https://github.com/Carthage/Carthage)

A Framework for using [Google Analytics iOS SDK](https://developers.google.com/analytics/devguides/collection/ios/resources) without CocoaPods. Google now distributes Google Analytics by means of CocoaPods only, which makes the integration of GA not so simple when we are not using this package manager. This simple wrapper allows us to use **Google Analytics** in our **Swift** or **Objective-C** applications without having to depend on **CocoaPods**.

**If you're already using CocoaPods in your project, just use [Google's pod](https://developers.google.com/analytics/devguides/collection/ios/v3/) directly**

##Requirements

**GAWrapper** is a dynamic framework, so it requires **iOS 8 or later**

##Installation

You can install the framework using **Carthage** or like a normal embedded framework.

###Carthage

Just add to your *Cartfile*

```
github "jandro-es/GAWrapper" >= 1.0

```

###Embedded Framework

Clone the repository or download the Zip version and build it using the **aggregate** target which will create in your home folder a *fat framework* with slices for **arm64, armv7, armv7+ and the simulator**. You just need to add it to your project like any other framework.

##How to use it

First you need to import the Framework:

```swift

import GAWrapper

```
GA's documentation states to start the service like this:

```swift

var configureError:NSError?
GGLContext.sharedInstance().configureWithError(&configureError)
assert(configureError == nil, "Error configuring Google services: \(configureError)")

```

**instead you need to start it using the *old way**

```swift

GAI.sharedInstance().trackerWithTrackingId("<tracking_id>")

```

The rest of the methods and properties in the documentation are available after initialization.



