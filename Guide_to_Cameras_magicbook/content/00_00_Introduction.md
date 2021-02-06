# Guide to Cameras for Interactive Installations


 Original Text by [Blair Neal](http://blairneal.com) in 2013 with major update in 2021 (update in progress)

-------------------

## **Preface:**

I published this guide in 2013 on [Creative Applications](http://creativeapplications.net) and moved it to Github in 2016. I don't think the Kinect 2 was even out at the time of the original, and many other cameras have since come and gone. Camera technologies have obviously changed a lot in the 7 years since I published, so it is certainly time for a major update. The 2013 version is being kept in the repository for historical reference.

Major changes to this since 2013 are that a lot of technologies have come out, HDMI capture is a lot easier and cheaper than it was in 2013, and Machine Vision algorithms have been able to accomplish things with object and body recognition that didn't even seem casually possible 7 years ago. I'm also covering a slightly broader set of cameras than I did in 2013 for further completeness.

-------------------

## **Introduction**

Cameras are one of the most commonly used sensors for interactive installations. They are useful for a wide range of interactions - motion detection, motion visualization, image detection, video and still recording, and more advanced feature and object detection, just to name a few possible applications. Essentially every creative technology coding framework has the ability to take in a basic camera feed and many beginner examples use a laptop's build-in webcams as their input source. The camera's traits of accessibility, portability, and ubiquity make them an ideal sensor for both early prototypes and advanced applications. 

As of this writing, I haven't found a comprehensive guide that covers all of the different types of image and light sensors, especially from the lens of interactive installations. Choosing the right type of camera for your interactive installation is one of the most important technical choices you can make in the initial planning phases of your project. You can always correct for certain things in software, but your hardware and camera choices are the first line of defense against undesired behavior. To be clear, I'm not intending to point out the ideal make and model of a particular camera that everyone should use - as we'll explore in the following chapters, there is absolutely not a one-size-fits-all solution when it comes to cameras. The choice depends on what you want to use it for.

As I've researched, I've found that drawing a line at what I'm defining as a "camera" is a bit challenging. There is a huge range of options available for observational tracking and light detection. In general for this writeup, we can think of a camera as an electronic device with a sensor that is capable of detecting different wavelengths of light that have been focused by a lens - but even that definition gets stretched in a few spots. In case you're curious for more detail - [Here](https://ciechanow.ski/cameras-and-lenses/) is a great guide by Bartosz Ciechanowski on the different physics involved in cameras and lenses.


In the sections below, Part 1 covers several common camera types and their strengths and weaknesses. Following that, Part 2 will cover some less common cameras and other topics like camera systems that use hybrid approaches. Part 3 will cover some supplementary information like camera measurements, latency, and other brief software topics.  Here is an outline of what we'll be covering.


 - **Part 0 - Questions to consider when choosing a camera**
 - **Part 1 - The Basics**
	 - The Basic RGB Webcam
	 - Other RGB Cameras
	 - Infrared Cameras
	 - Depth Cameras
	 - LIDAR
 - **Part 2 - The Exotic**
	 - Thermal Cameras
	 - High-end Machine Vision Cameras
	 - Multi-camera and on-board compute systems
	 - High-speed or Slow Motion Cameras 
	 - Wireless Cameras
	 - Motion Capture systems
	 - Volumetric Capture
	 - 360 Cameras and Filming
	 - Other Cameras and Systems (Robotic/Moving, and other "observational tracking devices")
	 - Older Camera/Video Technologies (Analog, Old RCA Cams)
	 - Experimental Technologies
 - **Part 3 - Supplemental Information**
	 - Camera interfaces (USB 2 and 3, HDMI, NDI, IP, GigE, etc)
	 - Outdoor considerations
	 - Notes on Lenses
	 - Notes on Latency
	 - Notes on image touch-up and noise reduction
	 - Brief software discussions
 - Other References and Acknowledgments

-------
## Questions to consider when choosing a camera:

Before we dive in, consider the following questions when considering which camera best suits your use case. You don't need an answer for everything, but having an idea for many of these will help determine the strengths and weaknesses of various technologies and help narrow down your list.

- Do you even need a camera? Would another sensor work better or be more reliable? Sometimes cameras can introduce a lot of unnecessary complexity where a simple distance sensor or physical button would be simpler.
- Where is the camera being set up? Does it need to be hidden?
- Will the camera be outside and exposed to the elements, or in the presence of direct sunlight?
- What is the lighting control like in the space? Does the space lighting change throughout the day or year?
- How precise does the interactivity need to be? Are you tracking large motions or small ones?
- Do you need more than one camera to cover the space? How will you combine or map the various camera images together?
- How will you run a cable from the camera to your computer? Will cable length be an issue?
- Is your software compatible with your choice of camera?
- Does the camera have settings that you can manually control or will it adjust itself automatically? If you need to control the settings automatically, does the camera allow for that?
- Do you need a high quality live feed image that the visitor will see, or can you get by with low resolution for tracking purposes?
- Is there a lot of movement in the space or in the background? How will you control for that?
- What is your subject? Are you tracking people or objects? Is there a controlled and defined space for interaction (i.e. a tabletop or a "stand here" floor sign), or is it more freeform?
- How big is the space you're trying to track people in? Where is the "active" area?
- Do you need to record audio as well? How do you plan on syncing a (potentially) separate microphone?
- Do you need a variable field of view (FOV), or is a fixed image fine? If necessary, can the image be zoomed or cropped on site?
- If necessary, how are you lighting the scene? What kinds of artificial lights will need to be tested and integrated into your setup?
