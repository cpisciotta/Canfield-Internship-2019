# Canfield Scientific Summer 2019 Internship Daily Log

## May 13, 2019

This day was spent learning the fundamentals of CoreML and Vision. This was done using Apple Developer Documentation and WWDC videos. A sample project was created named “Identifying Objects.” The foundation of this project uses a camera input and ResNet50 to interpret what an object is. It outputs to the user the predicted object and confidence level. More work will be done with CreateML, Vision, CoreML, and other machine learning frameworks to better understand the machine learning capabilities that are available on the iOS platform. Some research will likely be done on the different types of neural networks and algorithms. 

## May 14, 2019

The beginning of this day was spent researching ways to implement machine learning algorithms on an iOS app. Two solutions were found that could be used for a client project. One included utilizing the iOS platform and reshaping a multiarray. This was done using a set of helper functions found while doing research. The other option determined was to use coremltools to convert a Tensor Flow model into the correct format. The second half of the day was spent learning networking principles on iOS. This included understanding REST API calls, NSURL, and parsing JSON requests. These principles were explored and tested with the project named “Networking Test.” This simple app is designed to show weather in a select number of cities using the imported data. These principles will help in learning how to implement the API functions on the Canon camera.

## May 15, 2019

This day was spent understanding and testing the capabilities of the Canon CCAPI and Canon EDSDK. This included understanding the documentation of API documentation and exploring the capabilities of the camera itself. In exploring the capabilities of the Canon CCAPI, a project was started named “Canon CCAPI Test.” This is the start of an app which would essentially control all of the capabilities of the Canon EOS Rebel SL3 camera. Included in the app as of May 15 is the ability to get device information (i.e.: manufacturer, serial number, mac address), the ability to take photos remotely, and the start of live image preview. The main principles I learned are HTTP requests (GET, POST, PUT) and parsing JSON data. Reading through the API documentation also helped me better my ability to debug code and to understand complex code.

## May 16, 2019

The entirety of this day was spent implementing more functionality from the Canon CCAPI. The main new functionality capabilities are the live view and the ability to see saved photos. Issues arose when trying to download photos in the background. This is an issue regarding threads. At this point, the app has buttons to control various settings of the camera (flash, exposure, white balance, recording, audio, color temperature, etc.). That functionality is next to be implemented. Additionally, the ability to see photo thumbnails will likely be a project to be completed soon. An issue was resolved regarding the remote image capture capability. When utilizing the shutter API function it was later discovered that there is an automatic shutter capture call and a manual shutter capture call. The manual requires a call to press and then release the shutter button- something not implemented at first. This resulted in many issues with the camera not being able to function without the app. Additionally, it was discovered that the app is not able to display saved photos when not in the proper “mode.” This is an issue that has not yet been resolved and will be investigated further to ensure that the camera is always able to remotely access saved photos.

## May 17, 2019

The majority of this day was spent restructuring the format of the code. When reopening the project, it was discovered that many of the files had been lost. This resulted in the need to reprogram much of the functionality that had already been implemented. With this came the opportunity to better architect the program. A large number of structs were created that correspond to different JSON messages in order to efficiently decode and encode any information. This allowed for less error and easier JSON handling. Additionally, the app was restructured to have a tab bar controller with a number of separate view controllers. This allows for a less cluttered interface, an easier time managing functionality, and better readability of the view controller files. When creating the different structs for the corresponding structs it was discovered that optional values could be used because the JSON encoder/decoder would ignore those values if nil. This allowed for more efficient code because many structs could be combined. Towards the end of the day, issues were encountered with getting the image url data. When taking a photo and requesting the corresponding url address, the return message was consistently an error message. This is a problem that will be investigated next time. When working on this next week, the plan is to implement a preview view of the last photo taken, the ability to delete the last photo taken, and the ability to manipulate some of the image capture properties.

## May 20, 2019

This day was spent continuing to understand and implement the major API calls available via the CCAPI. Major additions include the ability to record videos, the ability to access individual image capture parameters, the ability to see and delete the last photo taken, the ability to set device settings, and the start of a photo file hierarchy (via multiple table view controllers). A list of to-do items was made to continue improving the functionality of the app. When working on the code next, I will consult Jim in order to address the best means to download and view all images.

## May 21, 2019

This day was spent making a series of UI/UX design changes to improve the quality of the application. A number of view controllers were consolidated to improve the efficiency of the code. The photo and video capture view controllers were combined into one view controller. In addition, the device information properties were brought onto the main view controller, accessible via one information button, rather than having its own view controller. In addition, image settings (ISO, aperture, flash, etc.) began the process of migrating to the capture view controller for better access and user experience. To better the UI, graphics were added.

## May 22, 2019

This day was spent updating the structure of the program. Given the increasing complexity of the code, it became evident that the structure needed to be reformatted to follow the MVC format. This would allow for better readability and reuse of the code. Additionally, the project was restructured to be used on an iPad environment. The main issue faced today was working with completion handlers. Given that threads execute and finish at different times, data from the camera was being read in an incorrect sequence. This led to the inability to see photos on the camera and the inability to access image setting parameters properly.

## May 23, 2019

This day was again spent restructuring the program to better follow an MVC/MVVM style. This allowed for the reuse of many functions. This included the addition of reusable networking calls. With these changes, the main view controller code was cut from approximately 800 lines to approximately 400 lines. Additionally, the readability of the code was improved. This is the first day in which saved photos can be viewed on the app in a collection view as a thumbnail. Tomorrow’s project is to allow a user to select a thumbnail and see a full-size image. Following that will be the ability for the user to see metadata associated with the photo. Extensive time was spent researching MVC and MVVM principles to better understand them and to try implementing those architectural design principles into the existing program. This led to the removal of unnecessary files and the separation of some functionality to better encapsulate certain tasks.

## May 24, 2019

This day was spent updating the app’s ability to see photos taken on the iPad. The app is now able to see all of the images available on the device in a UICollectionView. Additionally, the user is able to click on an image thumbnail and to see a detailed JPG image. The user is able to zoom in on the image. Difficulty was encountered when trying to delete the image from the device directory, however, the majority of the process is in place. The next steps will be to allow the user to save an image to the camera roll or locally on the app. Networking calls were consolidated to allow for better reusability and unneeded view controller files were removed. Icons, activity indicators, and labels were added to improve UI/UX. In addition, functions were added to regularly monitor the shooting mode (via a timer) and to update the UI if a change is detected. A bug was found where still image capture would – at times – fail to work immediately. This bug has been reduced and improved, however, has not been completely fixed. Another project for the future will be to allow the user to see the root photo folder on the device via the app. 

## May 28, 2019

This day was spent making a series of improvements to the existing code. Major changes include the following: ability to save to the camera roll, ability to delete images from the camera, and ability to capture some basic image metadata. This was done through the inclusion of bar button items. Image capture parameters were added to the LiveCaptureViewController to allow for more image manipulation capabilities. Additionally, repeating code was separated into reusable functions (LiveCaptureViewController UILabel setup and refresh) and code was further separated to better conform to app architecture best practices. This allowed for more lightweight view controller code. Networking calls were added to cover the various HTTP requests, which included the automation of the initial setup call. The next projects include the ability to see full image metadata, the ability to save images locally to the app, the ability to enable autofocus, and the ability to setup camera through the app. 

## May 29, 2019

This day was spent understanding the limitations of the app and determining the best ways to implement new functionality to the app. It was extremely difficult to make design iterations to the app today as the camera wifi network kept crashing when trying to connect. The ability to save photos locally was added, the ability to see photo metadata was added, and the ability to manipulate still image quality was added. Time was spent trying to implement the auto focus ability, however, when implementing this feature the app was often unable to capture an image. 

## June 7, 2019

This day was spent exploring Project Catalyst. This allows for the ability to bridge iPad apps to the Mac platform. This involved downloading OS Catalina, Xcode 11, and exploring the new capabilities of Swift 5 and Xcode 11. Although difficulties were encountered, it appears that Catalyst largely allows for smooth bridging from iPad to Mac. When testing the capabilities, much of the Canon CCAPI functionality worked correctly on MacOS. Next week’s projects will include further researching Project Catalyst, understanding Combine, and researching Reactive Swift. Some other things done today included adding network function calls and error handling.

## June 10, 2019

The beginning of today was spent understanding and implementing the capabilities of Project Catalyst with the existing Canon CCAPI app. During this process a number of Xcode 11 Beta bugs were encountered, however, this led to the inclusion of more error handling code in order to distinguish between Xcode-beta bugs and programmatic bugs. The remainder and majority of the day was spent researching and understanding the new SwiftUI framework. This was done by watching WWDC ’19 presentations, reviewing sample code, and testing functionality. With this new research project, I will be developing an app that uses Canon’s CCAPI and CoreML. Using the external camera, the app will be able to identify objects using Apple’s machine learning technology. As of today, the app is able to display the image from the Canon camera onto the app using SwiftUI.

## June 11, 2019

This day was spent better understanding SwiftUI and Combine. This was done through the creation of two different applications. The first is an app that combines the abilities of the Canon CCAPI, CoreML, and SwiftUI. This takes a photo on the iOS device and identifies the image. The second application started is a weather app that shows the weather in select locations. This app was created to understand the nuances of SwiftUI. This allowed me to better understand how complex apps will be created with this new framework. Given that MacOS Catalina and Xcode 11 are still in beta versions, a number of issues were faced that led to difficulties.

## June 12, 2019

This half-day was spent finishing the basic functionality of the SwiftUI and ML app that uses the Canon camera. Most of the day was spent researching the following: data flow and state, Swift packages, and Swift Instruments. The next project will be to create a package for the new app and to implement it.

## June 13, 2019

This day was spent researching more WWDC material. This included watching videos on Swift Packages Manager, Swift 5/ Xcode 11 best practices, and Combine. A presentation was started to show the research that has been done on WWDC 2019. A Swift package (“CanonCapture”) was created to demonstrate the ability to create, manage, and implement packages directly in Xcode. This package extracted pieces from the Canon capture app w/ ML to demonstrate how the app could modularize reusable code and implement it.

## June 14, 2019

The beginning of today was spent preparing a presentation of the work completed so far. This presentation will be presented to the team to demonstrate what I’ve learned and also to show what has been learned in researching the videos and releases at WWDC 2019. The remainder of the day was spent continuing to watch WWDC 2019 events. Today’s videos focused on testing, debugging, and optimizing. This includes using Xcode instruments, XCTests, and simulating adverse situations. This was extremely helpful as this is a completely new area of app development which I have little to no experience with. Next week, I will try to implement some XCTests to understand their implementation and utility.

## June 17, 2019

Today was spent understanding the fundamentals of ARKit, RealityKit, and Reality Composer. This was done through watching a series of videos published at WWDC 2019. In addition, a number of small test projects were created to understand how to use these technologies. While watching these videos, it was explained that 3-D models can be imported into reality composer that have the “usdz” extension. When trying to import these models into Reality Composer, however, the system kept crashing. A simple solar system scene was created to understand triggers and actions. Another scene was created to test the physics capabilities of Reality Composer. Some difficulty was encountered when trying to understand how anchors and entities work in Xcode. Some more research will likely be done to understand how to implement these in Xcode and how they relate to scenes created in Reality Composer. Overall, I was successful in implementing the basic AR capabilities demonstrated at WWDC 2019. Additionally, I watched a video to understand QuickLook and the new ARQuickLook.

## June 18, 2019

The entirety of today was spent migrating the old Canon CCAPI program to the SwiftUI framework. Approximately 2/3 of the existing functionality has been incorporated. At this point, the outstanding task that remains is to be able to set image capture parameters and to view a detailed view of the photo.

## June 19, 2019

This day was spent migrating the old Canon Capture app to the SwiftUI framework. As this was being done, many of the issues with sequence and network connectivity have been resolved. As of today, the new app is able to get and set capture parameters, view photos on the camera, view device information, save images, and capture images. The next project will be to finish all features from the old application code and to begin researching and implementing the RTP stream into the app, if possible. Starting today the camera was connected to the device via a router instead of an ad-hoc network. This seems to have helped with wireless connectivity.

## June 20, 2019

This day was spent continuing to implement capabilities using the SwiftUI framework. New features were added, such as the ability to view all device information (temperature, battery status, storage information, etc.). In addition, more shooting parameters were added and the ability to change settings like wifi connection, formatting the card, and changing metadata information were added. After some testing, it was discovered that many network calls were being made at unexpected times. This issue will be resolved at a future date once it can be discovered why this issue has come about. It is known to be related to the Combine framework and its implementation. Some other issues faced were the ability to add more than 10 items to an HStack and Xcode not displaying autocomplete on large SwiftUI files.

## June 21, 2019

This day was spent continuing to update the Canon Capture app. While doing this, a number of updates were made to improve the app. The first was the reduction of network calls, using the onAppear() modifier to target when calls would be made. Some improvements were made to the ability to configure settings and the ability to see full size JPEG photos. In addition, EXIF data was parsed and a view was created. When doing some of this, a few bugs were found in Xcode 11 beta 2- namely the inability to use the onDisappear modifier. This prevents the ability to stop some network calls. When speaking to Jim about the project a few key tasks were determined for next week. This includes using a live stream, downloading the raw image, zooming in and out of images, and creating a package for the calls. The app’s performance was drastically improved today, as calls are no longer blocked. This was mainly done through the inclusion of reload buttons to make a call multiple times.

## June 24, 2019

This day was spent continuing to update the Canon Remote Capture App. Some key additions today include the abstraction of the getRequest function, which now handles generics. Additionally, there are now UI elements, such as activity indicators, to improve UX. In addition, raw images and jpeg images can be viewed. I began adding gesture recognizers to the detail image view, in order to zoom in and out of images, however, this will have to be revisited as the image fills the screen on zoom and does not smoothly zoom in and out. A large portion of the day was spent trying to parse the photo EXIF information into a list. This proved to be very difficult as the dictionary with values of type Any were not able to be displayed on the view. This is a problem that will have to be revisited in a later iteration.

## June 25, 2019

This day was spent working on a few new projects. The first was to clean up the code and to add comments throughout to improve readability and understanding. This process included the refactoring of code to separate distinct views and to add an environment object for better data handling. This new environment object holds the live image data, incidental information, and parameter information. A small fix was made to zoom to allow for zoom control without the ability to zoom out. The ability to drag an image still needs to be added. In depth research and trials were done to implement a live stream, however, this process was ultimately unsuccessful. This involved researching AVFoundation, Input and Output Streams, and URLSessions. More research and trials will be done later if time permits. The majority of the day was spent implementing the “flipdetail information”. This process involved creating a custom struct, manipulating data, and parsing the JSON. This data will be used to understand the liveview image information. This will help in the next project which is to display the auto focus frame on the app.

## June 26, 2019

A lot of significant additions and changes were made to the app today to improve its quality and performance. The first major change was to adjust how the image is displayed to best mirror the image on the DSLR LCD. This involved having a fixed aspect ratio of the iPad image, and instead using a clip shape to hide the part of the image not visible on the DSLR LCD. This results in a mirror image every time. The next significant change was the ability to see the auto focus frame on the iPad this involved used the incidental information and resizing the rectangle data to fit the iPad image proportionally. The last major update was the ability to begin autofocus and to use manual shutter control to take a photo. Some other changes were made to the UI layout to better fit portrait and landscape mode. In addition, the start of movie recording capabilities were added. The next projects will be to add complete movie recording capability and the ability to move the auto focus frame via the iPad.

## June 27, 2019

Today was spent making a number of performance changes. The first major update to the app today was the ability to see multiple auto focus frames on the screen at once and their state. For example, in auto focus tracking mode, the active auto focus frames are displayed at once and move with consistent with the DSLR. This required the creation of a new model that represents an auto focus frame. In addition, the ability to designate the auto focus frame position was added. The ability to stop auto focus was added and a call to disable autofocus was added if the app is terminated. The last major change that was made is the consolidation of calls to get current parameter values. Before, each parameter was retrieved through individual calls. Now, each parameter is received in one call and parsed using a new struct that holds, as properties, each parameter.

June 28, 2019

This half day was spent making minor changes and improvements to the code. A new struct was created that handles recordable information. This led to a new get request and a new UI element that displays the number of recordable images available. In addition, research was done to determine how information could be continuously streamed to the application. This has proven difficult as the documentation is limited. Another project was created, named “StreamingTest,” which exercises the abilities of input and output streams. This code works in that it communicates with the camera. However, there are only two calls made and there is no data being decoded. This will be the next project, as being able to do this will further consolidate many of the calls and improve the performance of the application. This will also help demonstrate networking with Swift.

## July 1, 2019

This day was spent researching the RTP protocol, this again resulted in no success. However, other iterations were made, such as the ability to drag image on zoom, the ability to lock image zoom, and the ability to see zoom scale of live image. As discussed with Jim, this project will likely be demonstrated tomorrow and a new project will also likely be determined.

## July 3, 2019

The first part of today was spent researching RTP implementation again. Finally, a solution was found to access the RTP stream via VLC media player. When doing research, it was realized that the developer documentation providing by Canon was misleading. The SDP document received must be used to access the RTP stream. A document explaining this issue was saved to clarify any issues. When accessing the RTP stream, however, it was determined that the stream is not as fluid as accessing the image via the “flip” or “scroll” call. In addition, when accessing the RTP stream, the camera intentionally becomes locked and can only be used to view images. In addition, the ability to view predicted image analysis (Vision/Core ML) was added via double tapping the Live View image. The Swift Package manager was researched again to implement Alamofire. This was done to see how Alamofire could help in making stream calls for image data, image info, and incidental info. This ultimately is only a couple lines of code and extremely helpful to continuously receive chunk data. This ultimately was not used at this time for the image and image info because the chunk format limits the ability to parse information properly. This will be revisited. In addition, the beta 3 version of Xcode and Mac OS were downloaded. The next project will be to fix new warnings and errors and to determine beta changes.

## July 5, 2019

When updating to beta 3, a major bug was found with Navigation View. This prevented the use of this beta release for the project, requiring a great deal of time to be spent reverting the Xcode and Catalina versions. Afterwards, I presented the demo app to Jim. We discussed issues and features of the app. Additionally, we discussed a new project: building a framework for the Canon CCAPI.

## July 8, 2019

Today was spent building the iOS framework for the Canon camera. A large part of three classes were written: “StillImageCaptureManager”, “DeviceCaptureManager”, and “PhotosManager”. These three classes will hold the majority of the Canon CCAPI calls. In addition, a demo app will be created that uses this framework. A number of structs and enums were created to assist the end client in using the framework.

## July 9, 2019

Today was spent making a number of significant changes to the framework. First, the result data type was added. This allows for better error handling and client use. Additionally, many functions were defined that each make a unique API call. Most of the written functions were tested. Additionally, the networking layer was significantly improved to ensure best use. A number of error enums were added to give the user a better understanding of any networking errors. This included the addition of localized error descriptions.

## July 10, 2019

Today was spent continuing to build the iOS framework. Most API calls were added and a few structs were added. The remaining calls mainly relate to receiving a stream of chunk data. The next major projects will be to add XCTests, documentation, and to make the project a CocoaPod.

## July 11, 2019

This day was spent adding functions to the CanonCaptureKit. In addition, unit tests were added for many of the functions. Lastly, documentation was added throughout the document for better understanding and readability.

## July 12, 2019

The beginning of today was spent adding any missing documentation. In addition, event related function calls were added. The project was published onto a Github repository and now supports Cocoapods and Carthage. In addition, the framework was shared with Jim. The next project will be to integrate the framework into a demo app. Other additions include more unit tests and the addition of a “ConnectionManager” to allow a user to change the host and port information.

## July 15, 2019

This entirety of this day was spent implementing the CanonCaptureKit in the demo app using SwiftUI. The only remaining portions of the app that have not been converted to the framework relate to getting and setting shooting parameters and the auto focus frame. In addition, a few framework functions were added, such as the ability to get EXIF information.

## July 16, 2019

This morning was spent finishing the demo app, which implements the CanonCaptureKit. Later, much of the focus was spent improving the framework. A function was added in the ConnectionManager class to check the connection with the camera and to receive a list of all available APIs. A new stable release of the CanonCaptureKit was published. Smaller projects included the addition of zoom control, fixing the getFlipDetail function to parse data correctly, and the addition of a README. The end of today was spent preparing the outline and initial iteration of a presentation to display at the intern event.

## July 17, 2019

This beginning of this day was spent fixing the function call which retrieves the list of current parameter values and abilities. Before today, this function call was only able to retrieve parameters whose values were of type String and whose abilities were of type Array of String. This limited the ability to retrieve parameters where values were custom objects or of type Integer. Using an enum decoder and encoder, it is now possible to retrieve the full parameter list, with nonhomogeneous value and ability types. Later in the day, team met to review the current state of the demo app and to discuss the research regarding the SwiftUI framework. In the meeting, it became clear that a few things needed to be immediately addressed. First is the ability to stream the live image. Currently, making each call as individual frames is extremely costly to the app’s performance. In addition, there are some bugs in the app which prevent it from being a successful app. One being the inability to see ability values for parameters and another being the inability to view the photos efficiently. These issues will be addressed and streaming functionality must be added.

## July 18, 2019

In order to stream live image data using the framework, a new project was created with UI Kit to retrieve an image stream. This required nearly an entire day’s worth of work, as streaming data from the camera proved to be very difficult at first. Ultimately, using various Stack Overflow posts and other similar articles, streaming functionality was finally incorporated into the project. With this a few things became clear. First, when streaming incidental information and event data, there are 7 bytes at the start and 2 bytes at the end, which must be stripped away. However, contrary to Canon documentation, when streaming live image data (“scroll” or “scroll detail”), the data stream contains nontrivial bytes to indicate the start and of the JPEG image (“ffd8” and “ffd9”). These bytes cannot be stripped from the image, as it will not generate a proper image. Without these bytes, the image data will be corrupted. When testing this functionality, a continuous stream of event data and image data was properly received. The next task will be to incorporate streaming into the framework and demo app.

## July 19, 2019

This day was spent trying to incorporate the streaming functionality into the framework. Unfortunately, it was determined that in order to incorporate the streaming functionality the networking layer must be rewritten. This will allow for streaming tasks to be cancelled and created.

## July 22, 2019

This day was spent rewriting the networking layer. The new networking layer follows a protocol-oriented approach and allows for networking tasks to be better managed. In this new networking layer, each individual get, put, post, and delete request is well defined. This allowed for the ability to finally incorporate the “scroll” function into the demo app and into the framework. At the end of today, a time was scheduled to present the demo app to Dan C. and Dan D.

## July 23, 2019

This beginning of today was spent fixing bugs that came with rewriting the networking layer. Later in the morning, the demo app was presented to Dan D. and Jim. Later, more streaming functions were added, such as “scroll detail” and “monitoring.” Additionally, the API calls for the remaining HTTP requests were added, mainly relating to video capture. The ability to modify contents (rotate, rate, protect, archive) was added to the Photo Manager. The parsing of streaming image data was moved to the framework. The last major update will be the ability to change networks. In addition, late in the day, some memory leaks were discovered in the application, preventing its ability to perform as expected.

## July 24, 2019

The beginning of today was spent updating the operating system and Xcode to the beta 4 versions. This resulted in the need to convert deprecated functions. In addition, it was discovered that a bug exists with the iPad simulator, resulting in the need to change all code to work with the iPhone. A lot of work was spent parsing the scroll detail data. This still requires work that will be done tomorrow.

## July 25, 2019

This day was spent completing the scrolling functionality of the application. Most of the day was spent parsing the scroll detail data properly, specifically when both image data and incidental information are being retrieved. The scroll detail parsing was completed. This process involves a data buffer, which searches for specific bytes that indicate image and info data. Once both image data and info data are found, the image data is formatted by removing specific bytes at the beginning and end of the data. The info data goes through the same process, however, also involves an attempt to decode into a specified object. This process works with limited error. The source of the infrequent error is unknown.

## July 26, 2019

This day was spent completing any outstanding tasks. This involved generating a repo which housed all project and internship details. Any outstanding work that could be completed for the framework was done. This included the refactoring of parameter retrieval and editing. The initial framework version was tagged and released.

# Meta

Charles Pisciotta – charles.pisciotta@canfieldsci.com - charles.pisciotta1@gmail.com
