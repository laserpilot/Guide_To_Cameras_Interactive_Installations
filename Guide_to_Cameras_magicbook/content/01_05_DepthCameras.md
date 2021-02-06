# Depth Cameras
![depthimage](depth.jpg)

(<a href="http://web.mit.edu/newsoffice/2011/lidar-3d-camera-cellphones-0105.html" target="_blank">image source</a>)

In a way, these are an offshoot of the IR camera category but they involve some form of infrared light projection that gets reassembled as a depth image using a variety of techniques like time-of-flight (TOF) or structured light. These two detection methods are pretty different and have their own pros and cons, in terms of potential speed: <a href="http://www.computervisiononline.com/books/computer-vision/time-flight-cameras">read about their differences here</a>.

The information that comes back in a depth image is much richer than the usual "2D" image captured by the cameras above, and it gives you the ability to more easily and robustly detect things like hands and fingers. Tracking those features would be difficult and require very controlled conditions with just a monochrome 2D image. The depth information makes it easier for you to detect the difference between a person and the background, and therefore assign more meaningful information to the human trying to interact. This is why it is easier for the Kinect to give you a person's skeletal information, something that would be difficult for just a regular 2D IR image.

<iframe src="http://www.youtube.com/embed/7QrnwoO1-8A?rel=0" width="640" height="480" frameborder="0" allowfullscreen="allowfullscreen"></iframe>

There are also other methods of obtaining the same information with a high framerate webcam and a projector (structured light). Another method called <a href="http://en.wikipedia.org/wiki/LIDAR">LIDAR</a> scanning uses lasers and a method of measuring the reflected light to construct a high resolution depth image. LIDAR is usually more effective than other methods at measuring an incredibly large area or the front of a building (for quickly getting a 3D model of the facade for a projection mapping surface).

**Connection types:** Primarily USB2 (<a href="http://www.amazon.co.uk/dp/B0036DDW2G/?tag=creativenet-21" target="_blank">Kinect</a>,<a href="http://www.amazon.co.uk/dp/B005UHB8EK/?tag=creativenet-21" target="_blank"> Asus Xtion</a>, <a href="http://www2.panasonic.biz/es/densetsu/device/3DImageSensor/en/index.html">Panasonic D-Imager</a>, <a href="http://click.intel.com/intelsdk/Creative_Interactive_Gesture_Camera_Developer_Kit-P2061.aspx">Intel/Creative Time of Flight cams</a>), other interfaces in more research oriented/industrial cameras.

**Resolution Range:** This mostly tends to top out around 320x240 @30fps for the more consumer level cameras, mostly for TOF. TOF cameras use different sensors than standard CMOS cams which impacts their speed and resolution. The Kinect is faster and higher resolution because they just use a standard IR cam.  Check the individual camera for it's maximum resolution.

**Range of effectiveness:** Typically less than 10-15ft (3-5m) for many popular cameras. Very close range (<1ft/30cm) often requires a device particularly suited for close range tracking.

**Depth Camera Pros:**

- Depth images give you the option of great background subtraction for tracking people and object because you can effectively ignore things after a certain depth range
- Machine Vision algorithms for depth images can easily give you additional information like hand skeleton, body skeleton, and shape normals. Some software sllows you to build up a reusable 3D Model of a space or object by moving the camera around it. You can also do decent body and facial motion capture for use in 3D rendering programs.
- Just like infrared cameras, Depth cameras aren't effected by light from projectors and screens if you're working with something where a tracking algorithm could get confused by the images that people are interacting with. This is a big reason why they are favorites for simple touch applications with screens.

**Depth Camera Cons:**


- Compatibility/Interoperability: There are many, many camera options out there and many have different ways of actually communicating with your software. Some of the more popular options have well maintained libraries for many creative coding frameworks, but more specialized depth cameras may have you making your own bridges to work with them.
- Fixed lensing - pretty much all of these cameras, aside from the Azure Kinect, have fixed lenses which means you won't be able to change their field of view.
- Resolution and framerate limitations - this is greatly improved since a few years ago, but you often still aren't getting anything like a 4K60fps depth or RGB image. 
- Due to the reliance on IR, these cameras will often be sensitive to changes in sunlight and only certain ones may be acceptable for 24/7 outdoor use (even behind a window).
- Subject outlines can be a bit rough depending on your camera, however they have improved dramatically in recent years and there are several algorithms for keeping a cleaner edge.
- Very close range applications may need additional testing, espeically if your subject is within a few inches or centimeters from the lens
- Certain surfaces will interfere with the ability to produce a good depth image. For many cameras, shiny surfaces be invisible or cause strange reflection artifacts in your image. Additionally, some fabrics have unusual behaviors in their absorbtion of light
- Using multiple systems together occasionally requires special consideration, particularly with structured light systems.
- Many cameras have limitations for how far they can generate depth images, and many common ones really only work out to about 10-15ft/3-5m. There are certainly exceptions, but be wary of looking at a manufacturer's specification for maximum depth range as they are often a bit oversold.

**Depth Cameras to consider and further reading**
 - [Intel Realsense](https://www.intelrealsense.com/compare-depth-cameras/)
 - [Microsoft Azure Kinect](https://docs.microsoft.com/en-us/azure/Kinect-dk/hardware-specification) - this is Microsoft's latest version of the Kinect from 2019. It has many improvements over the originals and is much more geared towards developers and integration instead of gaming and the Xbox. It features two different lens options for a wide field of view, and it can capture a 1024x1024 resolution depth image.
 - Microsoft Kinect V2. You are no longer able to purchase these new, so I don't suggest them for long term installations. However, they do have a lot of software options out there from years ago and are great for quick demos.
 - [2015 Academic paper comparing Depth Cameras](https://www.ocularrobotics.com/wp-content/uploads/2015/12/MMT2015_MMT2015_61.pdf)
 - [Stimulant's Depth Camera Shootout from 2016](https://stimulant.com/depth-sensor-shootout-2/)
