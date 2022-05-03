# Guide\_To\_Cameras\_For\_Interactive\_Installations\_2013

\#Guide to Cameras for Interactive Installations

**Original Text by** [**Blair Neal**](http://blairneal.com) **2013**

\#####Transferred to Github in 2016 - This file should be considered an archive - see this [file](Guide\_To\_Cameras\_For\_Interactive\_Installations\_2020.md) for more recent updates

***

Choosing the right type of camera for your interactive installation is one of the most important technical choices you can make in your  initial planning phases. Making the incorrect choice can really impact how well your installation reacts to its victims and it can also impact its ability to perform robustly in a large amount of environments. You can always correct for certain things in software, but the hardware setup can often be the first line of defense against undesired behavior.

Whether you're working in [Processing](http://www.creativeapplications.net/category/Processing/), [OpenFrameworks](http://www.creativeapplications.net/category/openframeworks/), [Max/MSP/Jitter](http://www.creativeapplications.net/category/maxmsp/), [Quartz Composer](http://www.creativeapplications.net/category/quarz-composer/) , [Cinder](http://www.creativeapplications.net/category/cinder/), [VVVV](http://www.creativeapplications.net/category/vvvv/), or really any artistically geared programming environment, your choice of camera can impact your work no matter the software. Some environments will give you more options with different cameras (maybe you need a Blackmagic capture card, or an IP cam, or a DSLR, or a Point Grey Firefly). Some environments won't have support for certain kinds of cameras, so do some checking before you think you can just plug your DSLR straight into Quartz Composer and expect it to be recognized. If the tool doesn't exist to port it in, there are a lot of technologies to do routing between applications (see [CamTwist](http://camtwiststudio.com) and [Syphon](http://syphon.v002.info) for OS X ), so you may have some luck there.

Each type of imager typically has some amazing strengths and some really hindering downfalls, so it's important to keep these kinds of questions in mind when planning your installation. For beginners, don't expect that because it works in your workspace, it'll work on the classroom or gallery floor...if at all possible, test it early!

**Questions to consider when in planning phases:**

* Where is it being set up?
* Will it be outside or in the presence of direct sunlight?
* What is the lighting control like in the space? Does it change throughout the day?
* How precise does the interactivity need to be? Are you tracking large motions or small ones?
* How big is the space you're trying to track people in? Where is the "active" area?
* How will you run a cable from the camera to your computer? Will cable length be an issue?
* Does the camera have settings that you can manually control or will it adjust itself automatically?
* Do you need a high quality image, or just something low resolution for tracking?
* Is there a lot of movement in the space or in the background, and how will you control for that?

Let's start with the most basic and accessible options for most people working with interactive installations for the first time:

***

\##1. The Basic Webcam - RGB ![BasicWebcam](images/webcam.jpg)

([image source](http://www.flickr.com/photos/designios/2066516480/))

**Connection types:** [USB 2](http://www.amazon.co.uk/s/?\_encoding=UTF8\&camp=1634\&creative=19450\&h=ddc4dfb3cdcf26a1e9d2633324930abe62600a14\&keywords=usb%202%20webcam\&linkCode=ur2\&qid=1361309657\&rh=n%3A430595031%2Ck%3Ausb%202%20webcam\&scn=430595031\&tag=creativenet-21) (Standard), [USB 3.0](http://www.amazon.co.uk/s/?\_encoding=UTF8\&camp=1634\&creative=19450\&field-keywords=usb%203%20webcam\&linkCode=ur2\&rh=n%3A430595031%2Ck%3Ausb%203%20webcam\&tag=creativenet-21) (not many of these, yet), [Firewire](http://www.amazon.co.uk/s/?\_encoding=UTF8\&camp=1634\&creative=19450\&field-keywords=firewire%20webcam\&linkCode=ur2\&rh=n%3A340831031%2Cn%3A!340832031%2Cn%3A429893031%2Cn%3A430595031%2Ck%3Afirewire%20webcam\&tag=creativenet-21\&url=node%3D430595031) (rare - old iSight was one of these)

**Max resolution range (typical):** Ranges wildly, but you usually will stick to  around 640 x 480 @30fps. Some cameras boast 1080p, but check the framerate! USB 2 often does not have enough bandwidth to send 30fps worth of 1080p frames without some serious frame blur artifacts and slowness. 720p is occasionally more achievable but sometimes at around 15-20fps, and some cameras like the Logitech C920 will claim to do their own camera-side compression to get the images through the pipe a little faster.

**Webcam Pros:**

* Cheap! -  best widely available ones I've seen are around $80 bucks, but can get them for as low as $5 or $10 at this point
* Easy to find
* Reliable - leave them on for months (not always though!)
* Full color image - they can see just about everything you can. Some can see some IR wavelengths. Rarely will you actually need the color image since most commonly used CV algorithms at the moment use monochrome images.
* Widely supported by just about any software environment, and well understood.
* They can see projection and content on screens. Essentially they see a less dynamic/contrasty version of what you see with your own eyes.

**Webcam Cons:**

* They can see projection and content on screens.
* Some brands will have really poor image quality, especially in low light.
* Excessive image noise can severely impact tracking algorithms, especially in low light.
* Rarely do you get to manually change the settings of the camera itself without some software investigation.
* Typically a fixed lens (no zooming or manual focus)
* Sensitive to changes in daylight/natural light
* Requires fairly sophisticated computer vision algorithms to extract really meaningful information from these cameras - no skeleton tracking or easy depth information
* USB cable lengths can be limiting if you need to be extremely far away from your processing computer. Plan for extenders/repeaters if going much over 30ft (10m) away
* Latency can sometimes be an issue with these. Not too much, but enough to feel just a little bit behind real life. Analog is a little bit faster in regard to processing the image. Also most of them, aside from the PSEye tend to max out at 30fps, and 60fps is really recommended for a lower feeling of latency and high tracking accuracy.
* Some cameras have weird methods of autofocus that can really screw up your imagery. I've used a few that were nice HD cams, but the slow hunting autofocus made them a deal breaker.
* Try leaving your camera on for an extended period of time. I've seen issues with inexplicable strange coloring, and just non-responsiveness after being left on for a long time with certain brands.

**-Range of effectiveness:** Varies by placement. Could watch an entire room of people, but with very little precision. Seems to work best in a range of about 1ft-50ft (.3-16m). If you're too far back, it can be difficult to get an accurate  or meaningful reading because the people will be too small to the sensor in relation to other image noise. Can be fine if they are on a fairly plain background though.

**-Optimal environment for repeatability/reliability:**

This is one of your only options on the list that is able to see the full color range, so you're sort of stuck with this or the pricier options in the next spot if you're doing any tracking that plans on using the colors in your environment.

Ideally a controlled room with good artificial lighting and no windows will ensure this camera will react the same at any hour of the day.

Most simple tracking methods with this camera will work best when the subject is on a plain solid background so it is easy for your software to pick out a person from other objects in the space. Background subtraction is suggested in a case like this.

**-Troublesome environments:**

An environment with a lot of changing daylight or natural light can really impact this camera's ability to reliably and predictably track at all hours.

A room with none or very little light will pose a lot of issues for getting reliable readings from this camera.

Rapidly changing lights or flashing projection in a space can sometimes upset their calibration.

**Webcam Further reading:**

Check out the differences between a UVC cam and a non UVC cam to get an idea about if you'll be able to manually control the camera from within your software. Check out UVC camera control for OS X [here.](http://phoboslab.org/log/2009/07/uvc-camera-control-for-mac-os-x) [Focal Length Calculator](http://www.videologyinc.com/lens%20focal%20length%20calculator.htm) [Spreadsheet of different current webcams and their capabilities for manual control on OS X](http://mactaris.blogspot.nl/p/webcam-settings-camera-support.html) Check out [Macam](http://webcam-osx.sourceforge.net) for additional support for certain specialized webcam uses.

Be warned, due to some shifts in how Quicktime is handled in OSX (QT\_kit-> AV Foundation), some of these camera tools may be broken in 10.9 whenever it comes around.

***

\##2. Other RGB cameras ![otherrgb](images/red.jpg)

([image source](http://www.brainfarmcinema.com/red.aspx))

For this category, I'm thinking of things like HD/DV camcorders over Firewire, an HD-SDI or component capture card, or high end production cameras like the Red Epic or Arri Alexa (ok, maybe those are a little ridiculous). There are various reasons for wanting something in this category. and it usually comes down to needing really high quality and high resolution images at a very low latency. You may also be working with some unusual equipment, capturing input from another computer or image device that isn't a camera or have some other concerns about image input. There are still a ton of things you can do with analog cameras that you simply cannot do yet with all digital setups.

These cameras tend to have the same qualities/pros/cons as the standard webcam does. There are just a few important differences in certain use cases.

Beware of interlacing from analog capture devices. Tracking algorithms will not be a fan of that. Also be aware of anything involving Black Magic 4K Ultra Studio for an option for getting 4K input.

There are some fantastic options for getting HDMI/SDI input into laptops now via thunderbolt connections, like the [Blackmagic Ultrastudio](http://www.blackmagicdesign.com/products/ultrastudio/) or [Blackmagic Intensity](http://www.blackmagicdesign.com/products/intensity/). These capture devices won't always work if you're sending signal from another computer though, so check your video color formats first for compatibility.

Capturing with a [DSLR](http://www.amazon.co.uk/s/?\_encoding=UTF8\&camp=1634\&creative=19450\&field-keywords=DSLR%20cameras\&linkCode=ur2\&rh=i%3Aaps%2Ck%3ADSLR%20cameras\&tag=creativenet-21\&url=search-alias%3Daps) all day would be great because you'll get the best image for the price range, but those cameras are not always designed to be left on for extended durations. DSLR's can easily suffer from heating issues or auto-shutoff if left on for too long. A more robust production camera or a solid DV Cam is more ideal for long running installations that require a really good image (and can't use a webcam for whatever reason), but make sure to do a lengthy test run before installing. Note: if tested and implemented with care, some DSLR's can perform just fine for long installation runs (one person has mentioned one running for 6 months at 7 hours a day with no issues).

DSLR's may need their SDK and some software massaging to work correctly in your environment, although some offer hit or miss HDMI output that would require a capture card. Canon's EDSDK for example has been [ported](https://github.com/kylemcdonald/ofxEdsdk) to openFrameworks for easy access, and [Magic Lantern Firmware.](http:/blairneal.com/blog/canon2syphon-v1-0%3E%3C/a%3ECanon2Syphon%3C/a%3E%20will%20let%20you%20access%20the%20camera%20feed%20in%20other%20video%20apps%20via%20Syphon.%20You%20can%20also%20play%20with%20custom%20firmware%20for%20Canon%20to%20expose%20additional%20features%20with%20the%20%3Ca%20href=)

Other high end cameras also enjoy the benefits of working with cables that were designed with long cable runs in mind. Webcams over really long (10m/30ft+) USB cables can cause jitter or some other funky consistency issues, so again...test before installing whenever possible. Production quality cameras can work over HD-SDI for fairly long runs (around 200-500ft depending on who you ask), but for the really far stuff, you're best either going over a network if you don't mind latency, or going over fiber with a converter box. Fiber will get you considerably further, more than 2500ft if you need it. You'll also need a capture card for some of these, occasionally requiring a tower instead of a laptop. Adding length in almost any case is going to add to the potential for problems, so if it is something going over 200 or more feet, try to check your whole chain first.

You're sometimes limited by the capture device and its support on your intended system. Some capture devices need special drivers or other magical mysticism to work within your intended environment, so be warned before going down this path...save your receipts.

**Further Reading:**

[Frieder Weiss's writeup on using digital versus analog cameras and the latency issues involved](http://frieder-weiss.de/eyecon/equipment.html) - 2008)

***

\##3. Infrared Cameras ![infraredimage](images/infrared.jpg)

These are really an essential tool for anyone working with interactive installations. Our visible light goes from 400-700nm, but certain cameras have the ability to see from 700-1000nm. This allows you to hide tracking lights (IR LED's or IR floodlights) and do other tracking of things not visible to the human eye.

The [Playstation Eye](http://www.amazon.co.uk/dp/B000W3YQ1Y/?tag=creativenet-21) is sort of the go-to for a lot of these applications (it's used in projects like the [Eyewriter](http://www.eyewriter.org)) because it does 60fps (or higher!), has a range of lenses you can buy, and it's pretty cheap for the quality. [Read more about it here](http://createdigitalmotion.com/2009/08/trick-out-your-ps3-eye-webcam-best-cam-for-vision-augmented-reality/). It will need to be modified and requires a visible light filter to only get the IR bands. It is also a great option as a regular RGB cam since it has variable focus and you can [buy extra lenses](http://peauproductions.com/store/index.php?main\_page=product\_info\&products\_id=2) for it to get wide or narrow angles.

For the next level up, the other common one is the [Point Grey Firefly](http://www.ptgrey.com/products/fireflymv/fireflymv\_usb\_firewire\_cmos\_camera.asp). One tip for this one is to go ahead and buy only the monochrome version of this camera, as the color version has the additional color filter layers that can impact image quality and response. I stick with the firewire version of this camera for the bandwidth, but that can limit you on cable length (you can really only get firewire out about 10-15ft without using a repeater or amplifer, so keep that in mind when building equipment lists). The Firefly will also take a range of lenses that give you an insanely large aperture of around 1.4-1.2f and will be able to give you a much brighter image than a standard webcam. You WILL need a visible light filter for the Firefly to only get IR bands though. See Golan Levin's article on [choosing the right IR filter for your application](http://www.flong.com/blog/2010/a-brief-note-on-infrared-filters-87-vs-87c/). In addition to the Point Grey, you can check out these cameras from [Imaging Source](http://www.theimagingsource.com/en\_US/products/cameras/).

When choosing these higher end cameras, also make note of their sensor size. A larger sensor will potentially increase your output resolution and decrease sensor noise, but you are left with a smaller range of lens choices. The happy medium seems to be a 1/3" sensor with a CS mount for the widest range of options.

**Connection Types: USB 2 (Playstation Eye or another webcam - modified), USB 3 (Point Grey Flea 3), Kinect's IR cam, Composite/Firewire (old Sonycam's with night vision)**

**Resolution Range:** You can generally get the same resolutions in IR that you can in regular webcams. There are plenty of tutorials out there for modifying standard webcams to only process IR light.

**Range of effectiveness:** Generally the same as a webcam (1ft-50ft or .3-16m). Some IR cams like the Point Grey have a wider range of security camera lenses for various zoom ranges if you need to do tracking from far away.

**Infrared Pros:**

* They cannot see images that are projected or on a screen (some can see content on screens...depends on screen type). IR and projection are a really nice interactive match, but you tend to need a dark space to pull these off. Are you also tired of being relegated to a dark windowless room with these tools?
* Can be used in dark spaces when used with IR emitters.
* Since they can see what the human eye can't, they are most useful for hiding certain elements like lights used for tracking points or illuminating a space.
* Tracking a point of IR light is an incredibly effective and robust tracking method because you can have a bright point of light that is invisible to the human eye.
* Good for tracking a large area like a stage flooded with IR.

**Infrared Cons:**

* Monochrome
* They require a healthy source of infrared light. Don't assume the lights inside will provide the type of light these cameras need to see effectively. You may need IR emitters to properly illuminate the space. People wont be able to see the extra light, but the camera will.
* Sensitive to sunlight and certain stage lights. Some stage lights will be bright enough to throw off tracking on an IR camera because the range of the light and camera overlap enough. There may be problems that the camera can see that you might not have seen with your eyes, so it can be useful to know the complete light profile of a room or to just go there with a camera beforehand.
* Certain clothes and materials look different in IR than in visible light. Can have weird effects sometimes.

**Optimal environment for round the clock reliability**

Room with a steady amount of IR light, either artificial or coming from a point source. Undesired sunlight can blow out an IR cam if the aperture isn't set right or if it doesn't have an automatic adjustment.

**Troublesome environments**

A dark room with insufficient IR light. A lot of normal light bulbs will still show up in IR even if they don't put out enough light to illuminate the IR spectrum, so keep an eye out for those in the background as pesky tracking distractions.

**Further Reading for IR cams**

[Frieder Weiss's writeup on IR cameras and equipment](http://frieder-weiss.de/eyecon/infrared.html) -2008

**Other IR camera suggestions:** Cheap Infrared CCTV cams work well, but you'll need a capture device [Sony CCTV cam good in low light (needs light filter)](http:/www.supercircuits.com/security-cameras/2-megapixel-hdcctv-box-security-camera-hdmi-blk-hdc20%3EFull%20HD%20over%20HD-SDI%20or%20HDMI%20\(needs%20filter!\)%3C/a%3E%3Cbr%20/%3E%20%3Ca%20href=/) The Sony M183 or M383 are classic low latency cams used for IR sensing, but are now discontinued, but check eBay.

***

\##4. Depth Cameras ![depthimage](images/depth.jpg)

([image source](http://web.mit.edu/newsoffice/2011/lidar-3d-camera-cellphones-0105.html))

In a way, these are an offshoot of the IR camera category but they involve some form of infrared light projection that gets reassembled as a depth image using a variety of techniques like time-of-flight (TOF) or structured light. These two detection methods are pretty different and have their own pros and cons, in terms of potential speed: [read about their differences here](http://www.computervisiononline.com/books/computer-vision/time-flight-cameras).

The information that comes back in a depth image is much richer than the usual "2D" image captured by the cameras above, and it gives you the ability to more easily and robustly detect things like hands and fingers. Tracking those features would be difficult and require very controlled conditions with just a monochrome 2D image. The depth information makes it easier for you to detect the difference between a person and the background, and therefore assign more meaningful information to the human trying to interact. This is why it is easier for the Kinect to give you a person's skeletal information, something that would be difficult for just a regular 2D IR image.

There are also other methods of obtaining the same information with a high framerate webcam and a projector (structured light). Another method called [LIDAR](http://en.wikipedia.org/wiki/LIDAR) scanning uses lasers and a method of measuring the reflected light to construct a high resolution depth image. LIDAR is usually more effective than other methods at measuring an incredibly large area or the front of a building (for quickly getting a 3D model of the facade for a projection mapping surface).

**Connection types:** Primarily USB2 ([Kinect](http://www.amazon.co.uk/dp/B0036DDW2G/?tag=creativenet-21),[ Asus Xtion](http://www.amazon.co.uk/dp/B005UHB8EK/?tag=creativenet-21), [Panasonic D-Imager](http://www2.panasonic.biz/es/densetsu/device/3DImageSensor/en/index.html), [Intel/Creative Time of Flight cams](http://click.intel.com/intelsdk/Creative\_Interactive\_Gesture\_Camera\_Developer\_Kit-P2061.aspx)), other interfaces in more research oriented/industrial cameras.

**Resolution Range:** This mostly tends to top out around 320x240 @30fps for the more consumer level cameras, mostly for TOF. TOF cameras use different sensors than standard CMOS cams which impacts their speed and resolution. The Kinect is faster and higher resolution because they just use a standard IR cam.  Check the individual camera for it's maximum resolution.

**Range of effectiveness:** Typically less than 10-12ft ( 3-4m).  Some cameras like the Intel/Creative TOF camera are really only designed for desk use and give you about 1m of effective distance, if that. Other TOF cameras like the D-Imager can give you up to 10m of range though. Makes certain sensors not very robust for use on large stages. Requires multiple sensors to cover a large area and thus complicates the CV processing chain and hardware setup. LIDAR can do a large area, but not necessarily in real time.

**Depth Camera Pros:**

* Depth images give you the option of really amazing background subtraction because you can totally ignore everything beyond about 10ft (with a Kinect).
* Processed depth images give you a lot of great tracking information like hand skeleton, body skeleton, shape normals. You can build 3D models of rooms or objects. You can do fairly high quality body and facial motion capture for use in 3D rendering programs.
* Isn't affected by light from a projector. A lot of the same good qualities as standard IR, but they should only be used if you _need_ depth information...they are not preferred over regular IR. Again, do your best to choose right tool for the job.

**Depth Camera Cons:**

* Because of the use of IR, these cameras will also be sensitive to changes in sunlight.
* Do not rely on depth cameras if you need a sharp, clean outline of your subject. You will get jagged artifacts that will need to be blurred or processed to get smooth lines.
* Structured light cameras aren't able to work at an incredibly close range (ie right in front of them). Time of flight cameras are a little more robust in this regard, and are better if you need to use them really close up.
* Certain surfaces will interfere with the ability to produce a good depth image. Shiny surfaces will effectively be invisible or cause strange reflection artifacts in your image.
* Using multiple systems together occasionally requires special consideration. Overlapping structured light from the Kinect (if they are right next to each other) can cause double images to appear due to the extra light grid. If the Kinects are more perpendicular to each other, this negative effect is less likely. You can also use this trick: attach a vibrating motor to one Kinect to make the other sensor's dots blur, and the vibrating sensor's own dots will stay in focus.
* Fairly limited effective range.

**Depth Image Examples:**

LIDAR/Structured light was used to get the massive scans of the spaces in this Radiohead video for House of Cards:

**Further reading:**

If you're just looking for stereo vision capture that can infer depth info, check out the [Readings on structured light and how it works](http:/www.ptgrey.com/products/bumblebee2/bumblebee2\_stereo\_camera.asp%3E%20Point%20Grey%20Bumblebee%20%3C/a%3E%3C/p%3E%20%3Cp%3E%3Ca%20href=/)

\-- ##5. Thermal Cameras ![thermalimage](images/thermal.jpg)

([image source](http://www.humintell.com/2011/09/truthfulness-detection/thermal/))

[http://en.wikipedia.org/wiki/Thermographic\_camera](http://en.wikipedia.org/wiki/Thermographic\_camera)

These cameras are comparatively rare to see in use in interactive installations because they are still prohibitively expensive compared to most other ones. They aren't totally unobtainable ( roughly $1000-20000) but that higher price tag makes them a little less desirable for early exploration on projects. It's a shame because these cameras offer a lot of abilities that just aren't possible with the other kinds of cameras.

There are various types of cameras to look at in this class, mostly pertaining to which part of the IR spectrum you're trying to see. You have the option of Long Wave IR, Mid Wave IR, and Short Wave IR. For thermal imaging, you'll mostly want to work with Long Wave IR, in the 7000-14000nm range.

I have not personally used one of these cameras yet, but they have some properties that would be really amazing in the tool belt of people making interactive installations.

Check out this guy doing some random demos with a thermal camera:

**Connection types:** Most are made to be integrated into existing systems and either have proprietary connections or just output composite video. [Some cameras communicate X/Y position of blobs.](http://www.thermitrack.com)

**Resolution range:** Some are very low resolution (the Thermitrack is 16 x 16px) and some are close to a VGA range, but don't expect to find HD thermal for cheap. You also get a variety of frame rates and contrast ranges.

**Thermal Camera Pros:**

* Normal visible light doesn't have much of an effect on a thermal camera.
* Good for tracking a large area like a stage.
* Gives you the ability to more definitely identify people because of their heat signature...whereas other objects and materials may not show up at all if they are warmer.
* Fairly robust for daytime to night time interaction because people will be the same temperature and appear in the proper dynamic range.
* Give you the ability to track invisible phenomena like hot air from breath, or residual heat from something like a hand leaving a warm mark on a surface, or a cold blast of water hitting a warm surface.
* Can see through certain materials and walls.
* Thermal cameras can see through certain kinds of clothing.

**Thermal Camera Cons:**

* As these are occasionally considered military grade equipment, there may be export restrictions, so be wary when planning on traveling abroad.
* Expensive
* Difficult to integrate - require either custom electronics or capture hardware
* Thermal cameras can see through certain kinds of clothing.
* Not all lights are invisible to thermal cameras...if it's producing heat or radiating it, the camera will see it.
* Thermal imaging sometimes results in ghosting of movement due to the sensor method.
* They are unable to see through windows/glass because the range of radiation ends up being reflected before it transmits through the glass to the camera. [See here for a more involved explanation of why](http://answers.yahoo.com/question/index?qid=20081001100003AAH2Ouo).
* Certain hot materials may result in unforeseen difficulties with using thermal imaging in certain environments. Requires a different type of thinking in order to anticipate things that will be overly hot or cold in the space of the installation.

&#x20;**Further reading:**

[People counters (wiki)](http://en.wikipedia.org/wiki/People\_counter)

[Thermitrack usage](http://www.dbpharrison.com/tag/thermitrack/)

\##6. Experimental technologies

These are cameras that haven't really reached the public market yet, or just haven't had the chance to be explored for interactive installations. This category can also include less conventional means of getting an image or tracking objects, or other tools that can be effected by visible light in the space (for example, the [Leap Motion](https://www.leapmotion.com) controller can be thrown off by excessive amounts of IR light). There are also light field cameras, like the [Lytro](https://www.lytro.com), that are able to get a different kind of information for shooting a scene than a normal CMOS detector can get. Some of these technologies are either brand new or too expensive or not accessible by most so they don't get a lot of use in interactive installations (yet) but it's only a matter of time for several of them.

Lytro example:

**Notes:**

Huge thanks to [Kyle McDonald](http://kylemcdonald.net), [Theo Watson](http://theowatson.com), [Zach Lieberman](http://thesystemis.com) and [Golan Levin](http://www.flong.com) for some great additional tips to help round out some of the suggestions here.

The above information is really from my own experience of using various camera technologies in interactive settings. As usual, try to do your own research first and use this as a guide of someone else's experiences. Some cameras I've used more (webcam), some less or not at all (thermal), so take some of my suggestions with a grain of salt although some pointers I've absorbed from some of the experts in the field.

Also, it would be good to go hit up wikipedia or other more accredited sources for the technical information on the visible light spectrum versus near and far infrared if you need a refresher, I have left most of those details out. Really understanding the science behind how the different cameras work can expand how well you actually use the camera in practice.
