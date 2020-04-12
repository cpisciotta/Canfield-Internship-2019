# Canfield Scientific Summer Internship 2019
***Charles Pisciotta, iOS Applications Intern***

This includes a detailed description and a daily log of all research and projects done.

---

## Table Of Contents
- [What I Researched And What I Worked On](#what-i-researched-and-what-i-worked-on)
  - [Main Project: iOS Framework for Canon API (CCAPI)](#main-project-ios-framework-for-canon-api-ccapi)
  - [Canon CCAPI](#canon-ccapi)
  - [WWDC 2019](#wwdc-2019)
  - [Xcode 11, SwiftUI, and Combine](#xcode-11-swiftui-and-combine)
  - [Machine Learning](#machine-learning)
  - [Augmented Reality (AR)](#augmented-reality-ar)
  - [Swift Package Manager](#swift-package-manager)
  - [Networking](#networking)
  - [Instruments and Testing](#instruments-and-testing)
  - [Catalyst](#catalyst)
  - [App Architecture](#app-architecture)
- [Resources That I Found Helpful](#resources-that-i-found-helpful)
- [Meta](#meta)

---

## What I Researched And What I Worked On

---

### Main Project: iOS Framework for Canon API (CCAPI)

The main deliverable for my summer internship is an iOS framework. This [framework](https://hq-github.canfield.hq/MobileDevResearch/CanonCaptureKit), “CanonCaptureKit,” allows for the complete use of the [Canon CCAPI](#canon-ccapi). This framework is comprised of several “managers” which control various parts of the Canon camera. For example, one manager might control the ability to setup and execute still image capture, while another manager allows for the retrieval of all saved images. Using this framework, Canfield developers can easily incorporate control of the Canon camera into new and existing Canfield iOS products. By the end of my internship, I completed what can be considered the core foundation of the framework. In it, every available API call to the Canon CCAPI is incorporated. This framework contains many custom classes and structs to handle JSON data, custom errors to account for client and server errors, custom enums to allow for safer communication with the API, Cocoapods and Carthage support, and extensive documentation to help other developers. In addition, there exists many hidden features that help incorporate API calls. For example, there are hidden functions that parse image data when retrieved or streamed. <br /><br />In addition, I included a demo application to demonstrate and test the abilities of the CanonCaptureKit framework. Unfortunately, because this demo application was written using the SwiftUI framework, many bugs and inconsistences exist within the app. This stems from the issues with [Xcode 11+ and SwiftUI](#xcode-11-swiftui-and-combine) still being in beta. Many of the problems that I faced with these new technologies are outlined in later sections. While it appears that there may be errors with the framework, functions were individually tested using UIKit and unit tests. Most, if not all, performed as intended. Any noticable errors that were discovered independent of the SwiftUI demo app were fixed accordingly.

---

### Canon CCAPI

In March 2019, Canon released its first version of the [Canon Camera Control API](https://developercommunity.usa.canon.com/canon?sys_id=1cfbcfe6db5bab00edc0b7beaa9619b9&view=sp&id=kb_article&table=kb_knowledge) (CCAPI). This robust API allows for virtually complete wireless control of [select Canon cameras](https://developercommunity.usa.canon.com/canon?id=kb_article&sys_id=fef6d02f1b08f780091162007e4bcb53). Prior to the release of this API, Canon only had the [EDSDK](https://developercommunity.usa.canon.com/canon?id=kb_article&sys_id=73210d13db522380fbb7d602ca96191f). While this SDK allows developers to program applications to wirelessly control select Canon cameras, it has one major pitfall: it requires tethered USB connection. With the new CCAPI, the compatible cameras can be wirelessly controlled via HTTP protocol over WiFi connection. With this new API, it is easy to gain complete control of the camera. API calls exist to do everything from retrieving fixed device information to deleting images on the SD card to streaming live video. Canon provides extensive documentation on how to use and incorporate these API calls into development projects. Despite this, I occasionally found inconsistences, such as typos in Canon's responses, or data being streamed differently than indicated in Canon's documentation, or the lack of information about certain API calls (i.e.: [RTP streaming](https://developercommunity.usa.canon.com/canon?id=community_question&sys_id=d24b23cfdb46f300d1bb9a82ca96191f)). This required work on my own part to investigate these discrepancies. Most, if not all, were resolved and noted in my own documentation. For example, RTP streaming was finally set up with the help of [VLC Media Player](https://www.videolan.org/vlc/index.html). Despite some of the difficulties encountered, Canon’s CCAPI is something that Canfield should seriously consider implementing in its iOS products, as it offers the ability to complement many of the existing iOS product feature and the opportunity to develop new technology.

---

### WWDC 2019

In June 2019, Apple held its annual Worldwide Developer Conference ([WWDC 2019](https://developer.apple.com/wwdc19/)) where it updated and released an incredible amount of development technology. This annual conference consists of dozens of [presentations](https://developer.apple.com/videos/topics/) that help developers understand the new and updated technology and how to leverage it in their own applications. Throughout the summer, much of my time was spent watching a large portion of these presentations and how they could benefit the developers at Canfield. In many of the sections, I include some of the presentations that I watched, regarding the respective topic, and how that new or updated technology could be beneficial to Canfield developers.

---

### Xcode 11, SwiftUI, and Combine

The entirety of my internship focused around the announcement of 3 major iOS development technologies at WWDC 2019: [Xcode 11](https://developer.apple.com/xcode/), [SwiftUI](https://developer.apple.com/xcode/swiftui/), and [Combine](https://developer.apple.com/documentation/combine). These three new technologies were crucial in my internship experience because they were each incorporated in nearly every project that I worked on this summer. Despite me finding it frustrating to use these new technologies while still in beta, I was impressed with their abilities to streamline iOS development- whether it is reducing the amount of code necessary, easing data management, or streamlining the app design process.<br /><br />

Throughout my experience this summer, I’ve encountered a number of situations that I believe would be helpful to anyone starting to explore these technologies. Below I've included a short list of some of these that may prove useful.

  - [ ] SwiftUI offers a modifier called “onDisappear.” This modifier, while somewhat self-explanatory, is supposed to execute any enclosed functions prior to a view being dismissed or popped from the stack. However, in every beta release of Xcode 11 and SwiftUI, this ability has unfortunately never worked, and I was unable to find any workarounds. This proved to be the biggest handicap in my demo application, as I was unable to stop making unnecessary HTTP requests.
  - [ ] SwiftUI has a view called a Geometry Reader. I found this extremely helpful in developing SwiftUI applications. Essentailly the purpose of this container view is to allow you to access the size and coordinate space of parent views. With the removal of auto layout, it proved helpful in managing layouts.
  - [ ] With the removal of TabBarControllers and NavigationControllers, developers must now use TabbedViews and NavigationViews. I found it easy to use both of these, however, there still seems to be some issues with both. For example, I was unable to navigate to other views via the navigation bar. While I was able to add buttons to the navigation bar, these buttons could only execute actions that did not involve navigation. In addition, I was unable to successfully remove the navigation bar from views where I did not want it to appear.
  - [ ] With every development project that I worked on in Xcode 11 this summer, one of the more frustrating experiences that I had is that errors were frequently wrong or displayed at incorrect locations. This mainly happened with SwiftUI projects. For example, if I forgot to use Text() to display strings in an HStack, it might say that the HStack was missing a parameter.
  - [ ] When using HStacks, VStacks, and ZStacks, it can contain – at most – 10 child views. There are work arounds, such as dividing a larger stack into groups. This is an intentional limit.
  - [ ] The SwiftUI editor does not seem to support landscape orientation preview of the device. It seems that the only workaround, at this time, is to set the fixed size of the view to be that of the device when in landscape orientation.
  - [ ] Xcode 11 beta 4 simulator would not display applications containting navigation views on the iPad.
  - [ ] Xcode 11 frequently does not load auto complete.
  - [ ] Supporting UIKit views and view controllers in SwiftUI is easy. Simply use UIViewRepresentable and UIViewControllerRepresentable.
  
Many of the resources that I used to learn SwiftUI and to understand encountered issues are included at the bottom. This includes an external repo that contains a compilation of all publicly available SwiftUI resources.

---

### Machine Learning

This was one of the first projects that I worked on. While doing this, I mainly focused on understanding Apple’s [Core ML](https://developer.apple.com/machine-learning/core-ml/) and Vision frameworks and its [CreateML](https://developer.apple.com/machine-learning/create-ml/) application. In order to better understand the state of Apple’s native machine learning technology, I spent some time watching [Apple’s machine learning videos from WWDC 2019](https://developer.apple.com/videos/frameworks/machine-learning-and-vision). This allowed me to better understand the new and existing technology and how it could be leveraged to build powerful machine learning technology natively on the iOS platform. To help me better understand and research this technology, I implemented it into a number of demo projects. To better understand CreateML, I created simple algorithms, such as a fruit classifier algorithm. These simple algorithms - that took only a few minutes to build – demonstrated the power of CreateML and how it could be scaled for much larger projects. These algorithms can very easily be done in the same way for classifying sound and classifying text.<br /><br />

As a side project, I helped Alex with understanding the new MLMultiArray type. This data type is in a strange format, however, this [forum](https://forums.developer.apple.com/thread/85017) helped me understand what each value in the array represented. In addition, [this open source project](https://github.com/hollance/CoreMLHelpers) helped me provide a solution to the team which demonstrated the ability to manipulate the array into the desired format. In addition, I discovered a very helpful tool in order to easily configure Tensor Flow models for native iOS use: [coremltools](https://developer.apple.com/documentation/coreml/converting_trained_models_to_core_ml).<br /><br />

The two ways that I truly grasped a strong understanding of the CoreML and Vision frameworks were with demo camera apps that I made using the built in iOS camera and the Canon DSLR. The demo applications I made using this machine learning technology were able to classify the dominant object in the frame. This was easy to implement, thanks to the open source [models](https://developer.apple.com/machine-learning/models/) available for use in iOS. It would’ve been very possible to build my own model, using CreateML. However, this would’ve required a lot of time because I would’ve needed to take pictures of all objects that I wished to classify.

---

### Augmented Reality (AR)

Perhaps some of the coolest technologies that I researched was [augmented reatlity (AR) on the iOS platform](https://developer.apple.com/augmented-reality/). This included [ARKit](https://developer.apple.com/augmented-reality/arkit/) and [RealityComposer](https://developer.apple.com/augmented-reality/reality-composer/). To best understand Apple’s new and existing Augmented Reality technology, I watched many of the [WWDC 2019 presentations](https://developer.apple.com/videos/graphics-and-games/ar-vr). This helped me understand how to natively incorporate AR experiences into iOS applications. I created a number of small demo projects to test various AR functionalities. For example, to test RealityComposer, I created a small 3-D model of part of the solar system. I found it extremely easy to create and animate 3-D models with this application. However, given that this application was still in beta, I ran into many issues with the application crashing or not performing as intended. Despite this, I found it easy to import 3-D models into Xcode projects and to interact with them. I also found it helpful to watch a presentation on [ARQuickLook](https://developer.apple.com/augmented-reality/quick-look/) to understand how this can help with developing AR applications.

---

### Swift Package Manager

One of the most useful new features to Canfield developers that I researched is the adoption of the [Swift Package Manager](https://swift.org/package-manager/) in Xcode 11+. The adoption of this extremely powerful tool will be crucial in future iOS development, as it will help developers easily manage app dependencies. As of right now, two main dependency managers that exist [Cocoapods](https://cocoapods.org) and [Carthage](https://github.com/Carthage/Carthage). While these two dependency managers each have their [pros and cons](https://medium.com/xcblog/carthage-or-cocoapods-that-is-the-question-1074edaafbcb), Swift Package Manager will eliminate almost all of the issues that arise with dependency management. In addition, it will be extremely helpful in the future, when Canfield developers wish to create new dependencies, frameworks, libraries, etc. for Canfield iOS products. To better understand how to create and manage Swift packages with Swift Package Manager, I watched many of the [WWDC 2019 videos about this new update](https://developer.apple.com/videos/developer-tools/swift). While testing this new feature in Xcode 11+, I created my own Swift packages. This included a simple Swift package which communicates with the Canon camera to wirelessly control it. Swift packages will also be extremely helpful to Canfield developers in the future because it will help modularize reusable code and allow for better collaboration between team members on large projects.

---

### Networking

In most every application that Apple consumers use, the internet is frequently needed to perform the core functionality of the respective app. This allows applications to communicate with third-party services, such as databases and external devices. Most of this communication is powered by HTTP requests (and a networking layer): a fundamental area of programming where I had limited experience. Through the projects that I worked on this summer, I quickly gained a strong understanding of how to implement HTTP requests iOS projects. From the first project I developed to the CanonCaptureKit framework that I built, I saw the evolution of how I implemented networking capabilities. By the end of the summer, I was able to successfully build an advanced networking layer that could efficiently make get, upload, and even stream requests to Canon’s CCAPI. The final networking layer in the CanonCaptureKit was developed after extensive research on iOS networking layers and review of a [sample networking layer setup](https://medium.com/flawless-app-stories/writing-network-layer-in-swift-protocol-oriented-approach-4fa40ef1f908).

---

### Instruments and Testing

One small research project that I did was understanding how to use Instruments and how to implement tests into projects. This involved watching WWDC videos on [debugging](https://developer.apple.com/videos/developer-tools/debugging), [implementing XCTests](https://developer.apple.com/videos/developer-tools/testing), and using [instruments](https://developer.apple.com/videos/developer-tools/performance). In addition, with the release of Xcode 11 and SwiftUI, I learned how to easily simulate adverse and unexpected situations. These videos were extremely helpful for me to incorporate tests into my own projects and understanding the fundamentals around Instruments. Later in the summer, the Instruments tool helped me understand the performance of my applications and where attention was required. Prior to my internship at Canfield, I had limited experience with XCTests, however, this opportunity helped me gain an understanding of the fundamentals around [test driven development](https://www.raywenderlich.com/5522-test-driven-development-tutorial-for-ios-getting-started).

---

### Catalyst

[Project Catalyst](https://developer.apple.com/ipad-apps-for-mac/) is an interesting and powerful new development, available in Xcode 11+. This new feature will streamline the development of Mac OS applications. This new development allows iOS developers to easily convert their existing iPad applications into Mac OS applications, too. In order to test this capability, I tried it with the application I made to control the Canon camera. Sure enough, all it took was selecting “Mac” on the project homepage. With this, Xcode took care of the necessary steps behind the scenes to make my iPad app compatible for use on a Mac. This will possibly an opportunity for Canfield to broaden its suite of iOS (and Mac OS) applications, reaching an even larger audience of customers.

---

### App Architecture

One of the foundational programming principles that I learned this summer- with help from Jim- was app architecture patterns. At the start of my internship, I found that my code files were large, somewhat repetitive, and often disorganized. With his help, I researched and learned much more about different design patterns: MVC, MVVM, etc. Understanding these design patterns helped me drastically reduce the size of my code files, helped me reduce the amount of work I did, and allowed me to gain a strong understanding of [separation of concerns](https://medium.com/datadriveninvestor/programming-fundamentals-part-5-separation-of-concerns-software-architecture-f04a900a7c50). The knowledge that I gained from this important topic was implemented in every project I worked on for the rest of the summer and a topic that will prove crucial in the app development projects that I work on in the future.

---

## Resources That I Found Helpful

- Apple Developer
  >[Apple Developer Home](https://developer.apple.com/xcode/swiftui)<br />
- Stack Overflow
  >[Stack Overflow](https://stackoverflow.com)
- Ray Wenderlich Articles and Videos
  >[raywenderlich.com](https://www.raywenderlich.com)
- SwiftUI
  >[Compiled SwiftUI Resources: CONTAINS ALL PUBLIC RESOURCES!](https://github.com/Juanpe/About-SwiftUI)<br />
  >[SwiftUI By Example](https://www.hackingwithswift.com/quick-start/swiftui)<br />
  >[Gosh Darn SwiftUI](https://goshdarnswiftui.com)<br />
- Combine
  >[SwiftLee](https://www.avanderlee.com/swift/combine/)<br />
- WWDC 2019
  >[WWDC 2019 Presentations](https://developer.apple.com/videos/)<br />
- Canon API
  >[Canon Developer Community](https://developercommunity.usa.canon.com/canon)<br />
  >[Introduction to Canon's CCAPI](https://www.youtube.com/watch?v=NwFHUGYzC3Y)<br />
- Burp
  >[Burp Suite Scanner](https://portswigger.net/burp)<br />
- Understanding JPEG Data
  >[Detecting Corrupted JPEG Data](https://stackoverflow.com/questions/46802866/how-to-detect-if-the-jpg-jpeg-image-file-is-corruptedincomplete)<br />
- Closures
  >[Gosh Darn Closure Syntax](http://goshdarnclosuresyntax.com)<br />
- EXIF Data
  >[Reading and Writing to EXIF Data](https://stackoverflow.com/questions/40175160/exif-data-read-and-write)<br />

---

## Meta
Charles Pisciotta, iOS Applications Intern - charles.pisciotta@canfieldsci.com - charles.pisciotta1@gmail.com
