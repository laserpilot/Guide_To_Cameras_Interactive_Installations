# Overview

###

## Guide to Cameras for Interactive Installations

Original Text by [Blair Neal](http://blairneal.com) in 2013 with major update in 2021 (update in progress)

***

To-do for 2020 Update:

* Clean up language and links
* Publish a version to Medium/personal site?
* Update references to various camera technologies in all categories
* Reference different connection protocols now available or more common (HDMI Capture, NDI, IP Cameras, GigE)
* Webcam update technologies (Logitech Brio)
* Other RGB Cameras (PTZ, 4K, DSLR, Broadcast)
* Major depth camera update (Kinect Azure, Orbbec, Realsense, include [Stimulant Depth camera shootout link](https://stimulant.com/depth-sensor-shootout-2/), [GigE Realsense](https://imaging.framos.com/cpc/en/d435e/?keyword=Realsense+GigE+Camera\&gclid=EAIaIQobChMIsqmywIPU5wIViJOzCh2NZQYsEAAYASAAEgIg7fD\_BwE)
* Thermal camera update (portable cams, USB, cheaper)
* High Speed cameras (Edgertronic, ix cameras, phantom)
* Others? (Leap Motion, GoPro, motion capture systems, things like Blacktrak(https://blacktrax.cast-soft.com) ), other things to consider as cameras or "observational tracking devices"
* Older camera technologies (DVCam, RCA/Analog, "Analog" capture devices, etc)
* Experimental
* Maybe more general tips outside of specific camera technologies? Suggestions below from Elliot
* Monochrome advantages
* USB3 vs GigE
* Lenses
* Noise and Noise reduction
* Machine learning touchup (upscaling, noise reduction, low light)
* Using a smartphone camera (pros, cons, intgerated sensor data and intrinsics)
* High end machine vision cams

### **Preface:**

I published this guide in 2013 on [Creative Applications](http://creativeapplications.net) and moved it to Github in 2016. I don't think the Kinect 2 was even out at the time of the original, and many other cameras have since come and gone. Camera technologies have obviously changed a lot in the 7 years since I published, so it is certainly time for a major update. The 2013 version is being kept in the repository for historical reference.

Major changes to this since 2013 are that a lot of technologies have come out, HDMI capture is a lot easier and cheaper than it was in 2013, and Machine Vision algorithms have been able to accomplish things with object and body recognition that didn't even seem casually possible 7 years ago. I'm also covering a slightly broader set of cameras than I did in 2013 for further completeness.

***

### **Introduction**

Cameras are one of the most commonly used sensors for interactive installations. They are useful for a wide range of interactions - motion detection, motion visualization, image detection, video and still recording, and more advanced feature and object detection, just to name a few possible applications. Essentially every creative technology coding framework has the ability to take in a basic camera feed and many beginner examples use a laptop's build-in webcams as their input source. The camera's traits of accessibility, portability, and ubiquity make them an ideal sensor for both early prototypes and advanced applications.

As of this writing, I haven't found a comprehensive guide that covers all of the different types of image and light sensors, especially from the lens of interactive installations. Choosing the right type of camera for your interactive installation is one of the most important technical choices you can make in the initial planning phases of your project. You can always correct for certain things in software, but your hardware and camera choices are the first line of defense against undesired behavior. To be clear, I'm not intending to point out the ideal make and model of a particular camera that everyone should use - as we'll explore in the following chapters, there is absolutely not a one-size-fits-all solution when it comes to cameras. The choice depends on what you want to use it for.

As I've researched, I've found that drawing a line at what I'm defining as a "camera" is a bit challenging. There is a huge range of options available for observational tracking and light detection. In general for this writeup, we can think of a camera as an electronic device with a sensor that is capable of detecting different wavelengths of light that have been focused by a lens - but even that definition gets stretched in a few spots. In case you're curious for more detail - [Here](https://ciechanow.ski/cameras-and-lenses/) is a great guide by Bartosz Ciechanowski on the different physics involved in cameras and lenses.

