##Guide to Cameras for Interactive Installations </h2>


#### Original Text by [Blair Neal](http://blairneal.com) 2013
#####Transfered to Github in 2016 - really needs some updates to reflect the latest tech...

-------------------

Choosing the right type of camera for your interactive installation is one of the most important technical choices you can make in your  initial planning phases. Making the incorrect choice can really impact how well your installation reacts to its victims and it can also impact its ability to perform robustly in a large amount of environments. You can always correct for certain things in software, but the hardware setup can often be the first line of defense against undesired behavior.

Whether you're working in <a href="http://www.creativeapplications.net/category/Processing/">Processing</a>, <a href="http://www.creativeapplications.net/category/openframeworks/">OpenFrameworks</a>, <a href="http://www.creativeapplications.net/category/maxmsp/">Max/MSP/Jitter</a>, <a href="http://www.creativeapplications.net/category/quarz-composer/">Quartz Composer</a> , <a href="http://www.creativeapplications.net/category/cinder/">Cinder</a>, <a href="http://www.creativeapplications.net/category/vvvv/">VVVV</a>, or really any artistically geared programming environment, your choice of camera can impact your work no matter the software. Some environments will give you more options with different cameras (maybe you need a Blackmagic capture card, or an IP cam, or a DSLR, or a Point Grey Firefly). Some environments won't have support for certain kinds of cameras, so do some checking before you think you can just plug your DSLR straight into Quartz Composer and expect it to be recognized. If the tool doesn't exist to port it in, there are a lot of technologies to do routing between applications (see <a href="http://camtwiststudio.com/">CamTwist</a> and <a href="http://syphon.v002.info/">Syphon</a> for OS X ), so you may have some luck there.

Each type of imager typically has some amazing strengths and some really hindering downfalls, so it's important to keep these kinds of questions in mind when planning your installation. For beginners, don't expect that because it works in your workspace, it'll work on the classroom or gallery floor...if at all possible, test it early!

<strong>Questions to consider when in planning phases:</strong>

• Where is it being set up?
• Will it be outside or in the presence of direct sunlight?
• What is the lighting control like in the space? Does it change throughout the day?
• How precise does the interactivity need to be? Are you tracking large motions or small ones?
• How big is the space you're trying to track people in? Where is the "active" area?
• How will you run a cable from the camera to your computer? Will cable length be an issue?
• Does the camera have settings that you can manually control or will it adjust itself automatically?
• Do you need a high quality image, or just something low resolution for tracking?
• Is there a lot of movement in the space or in the background, and how will you control for that?

Let's start with the most basic and accessible options for most people working with interactive installations for the first time:

----------------
<h2>1. The Basic Webcam - RGB</h2>
<a href="http://www.creativeapplications.net/wp-content/uploads/2013/02/2066516480_a4a196d518_o.jpg"><img class="alignnone size-large wp-image-32566" src="http://www.creativeapplications.net/wp-content/uploads/2013/02/2066516480_a4a196d518_o-640x426.jpg" alt="2066516480_a4a196d518_o" width="640" height="426" /></a>

<small>(<a href="http://www.flickr.com/photos/designios/2066516480/" target="_blank">image source</a>)</small>

<strong>Connection types:</strong> <a href="http://www.amazon.co.uk/s/?_encoding=UTF8&amp;camp=1634&amp;creative=19450&amp;h=ddc4dfb3cdcf26a1e9d2633324930abe62600a14&amp;keywords=usb%202%20webcam&amp;linkCode=ur2&amp;qid=1361309657&amp;rh=n%3A430595031%2Ck%3Ausb%202%20webcam&amp;scn=430595031&amp;tag=creativenet-21" target="_blank">USB 2</a> (Standard), <a href="http://www.amazon.co.uk/s/?_encoding=UTF8&amp;camp=1634&amp;creative=19450&amp;field-keywords=usb%203%20webcam&amp;linkCode=ur2&amp;rh=n%3A430595031%2Ck%3Ausb%203%20webcam&amp;tag=creativenet-21" target="_blank">USB 3.0</a> (not many of these, yet), <a href="http://www.amazon.co.uk/s/?_encoding=UTF8&amp;camp=1634&amp;creative=19450&amp;field-keywords=firewire%20webcam&amp;linkCode=ur2&amp;rh=n%3A340831031%2Cn%3A!340832031%2Cn%3A429893031%2Cn%3A430595031%2Ck%3Afirewire%20webcam&amp;tag=creativenet-21&amp;url=node%3D430595031" target="_blank">Firewire</a> (rare - old iSight was one of these)

<strong>Max resolution range (typical):</strong> Ranges wildly, but you usually will stick to  around 640 x 480 @30fps. Some cameras boast 1080p, but check the framerate! USB 2 often does not have enough bandwidth to send 30fps worth of 1080p frames without some serious frame blur artifacts and slowness. 720p is occasionally more achievable but sometimes at around 15-20fps, and some cameras like the Logitech C920 will claim to do their own camera-side compression to get the images through the pipe a little faster.

<strong>-Webcam Pros:</strong>

• Cheap! -  best widely available ones I've seen are around $80 bucks, but can get them for as low as $5 or $10 at this point
• Easy to find
• Reliable - leave them on for months (not always though!)
• Full color image - they can see just about everything you can. Some can see some IR wavelengths. Rarely will you actually need the color image since most commonly used CV algorithms at the moment use monochrome images.
• Widely supported by just about any software environment, and well understood.
• They can see projection and content on screens. Essentially they see a less dynamic/contrasty version of what you see with your own eyes.

<strong>-Webcam Cons:</strong>

• They can see projection and content on screens.
• Some brands will have really poor image quality, especially in low light.
• Excessive image noise can severely impact tracking algorithms, especially in low light.
• Rarely do you get to manually change the settings of the camera itself without some software investigation.
• Typically a fixed lens (no zooming or manual focus)
• Sensitive to changes in daylight/natural light
• Requires fairly sophisticated computer vision algorithms to extract really meaningful information from these cameras - no skeleton tracking or easy depth information
• USB cable lengths can be limiting if you need to be extremely far away from your processing computer. Plan for extenders/repeaters if going much over 30ft (10m) away
• Latency can sometimes be an issue with these. Not too much, but enough to feel just a little bit behind real life. Analog is a little bit faster in regard to processing the image. Also most of them, aside from the PSEye tend to max out at 30fps, and 60fps is really recommended for a lower feeling of latency and high tracking accuracy.
• Some cameras have weird methods of autofocus that can really screw up your imagery. I've used a few that were nice HD cams, but the slow hunting autofocus made them a deal breaker.
• Try leaving your camera on for an extended period of time. I've seen issues with inexplicable strange coloring, and just non-responsiveness after being left on for a long time with certain brands.

<strong>-Range of effectiveness:</strong> Varies by placement. Could watch an entire room of people, but with very little precision. Seems to work best in a range of about 1ft-50ft (.3-16m). If you're too far back, it can be difficult to get an accurate  or meaningful reading because the people will be too small to the sensor in relation to other image noise. Can be fine if they are on a fairly plain background though.

<strong>-Optimal environment for repeatability/reliability:</strong>

This is one of your only options on the list that is able to see the full color range, so you're sort of stuck with this or the pricier options in the next spot if you're doing any tracking that plans on using the colors in your environment.

Ideally a controlled room with good artificial lighting and no windows will ensure this camera will react the same at any hour of the day.

Most simple tracking methods with this camera will work best when the subject is on a plain solid background so it is easy for your software to pick out a person from other objects in the space. Background subtraction is suggested in a case like this.

<strong>-Troublesome environments:</strong>

An environment with a lot of changing daylight or natural light can really impact this camera's ability to reliably and predictably track at all hours.

A room with none or very little light will pose a lot of issues for getting reliable readings from this camera.

Rapidly changing lights or flashing projection in a space can sometimes upset their calibration.

<strong>Webcam Further reading:</strong>

Check out the differences between a UVC cam and a non UVC cam to get an idea about if you'll be able to manually control the camera from within your software. Check out UVC camera control for OS X <a href="http://phoboslab.org/log/2009/07/uvc-camera-control-for-mac-os-x">here.</a>
<a href="http://www.videologyinc.com/lens%20focal%20length%20calculator.htm">Focal Length Calculator</a>
<a href="http://mactaris.blogspot.nl/p/webcam-settings-camera-support.html">Spreadsheet of different current webcams and their capabilities for manual control on OS X</a>
Check out <a href="http://webcam-osx.sourceforge.net/">Macam</a> for additional support for certain specialized webcam uses.

Be warned, due to some shifts in how Quicktime is handled in OSX (QT_kit-&gt; AV Foundation), some of these camera tools may be broken in 10.9 whenever it comes around.

--------------------
<h2>2. Other RGB cameras</h2>
<a href="http://www.creativeapplications.net/wp-content/uploads/2013/02/epic_stock1.jpeg"><img class="alignnone size-large wp-image-32565" src="http://www.creativeapplications.net/wp-content/uploads/2013/02/epic_stock1-640x397.jpeg" alt="epic_stock1" width="640" height="397" /></a>

<small>(<a href="http://www.brainfarmcinema.com/red.aspx" target="_blank">image source</a>)</small>

For this category, I'm thinking of things like HD/DV camcorders over Firewire, an HD-SDI or component capture card, or high end production cameras like the Red Epic or Arri Alexa (ok, maybe those are a little ridiculous). There are various reasons for wanting something in this category. and it usually comes down to needing really high quality and high resolution images at a very low latency. You may also be working with some unusual equipment, capturing input from another computer or image device that isn't a camera or have some other concerns about image input. There are still a ton of things you can do with analog cameras that you simply cannot do yet with all digital setups.

These cameras tend to have the same qualities/pros/cons as the standard webcam does. There are just a few important differences in certain use cases.

Beware of interlacing from analog capture devices. Tracking algorithms will not be a fan of that. Also be aware of anything involving <a href="http://www.wisegeek.com/what-is-the-difference-between-ntsc-and-pal.htm#slideshow&gt;PAL versus NTSC.&lt;/a&gt;&lt;/p&gt; &lt;p&gt;You will be able to capture at a higher resolution and full frame rate, sometimes up to 60fps (or higher!) and 1080p and beyond, but that comes at a hefty price tag and will consume a large amount of computational resources. Some capture tools let you do full 4K resolution preview monitoring, but these occasionally need their own software pipes to get something that big into your processor. Check out this &lt;a href=">Black Magic 4K Ultra Studio</a> for an option for getting 4K input.

There are some fantastic options for getting HDMI/SDI input into laptops now via thunderbolt connections, like the <a href="http://www.blackmagicdesign.com/products/ultrastudio/">Blackmagic Ultrastudio</a> or <a href="http://www.blackmagicdesign.com/products/intensity/">Blackmagic Intensity</a>. These capture devices won't always work if you're sending signal from another computer though, so check your video color formats first for compatibility.

Capturing with a <a href="http://www.amazon.co.uk/s/?_encoding=UTF8&amp;camp=1634&amp;creative=19450&amp;field-keywords=DSLR%20cameras&amp;linkCode=ur2&amp;rh=i%3Aaps%2Ck%3ADSLR%20cameras&amp;tag=creativenet-21&amp;url=search-alias%3Daps" target="_blank">DSLR</a> all day would be great because you'll get the best image for the price range, but those cameras are not always designed to be left on for extended durations. DSLR's can easily suffer from heating issues or auto-shutoff if left on for too long. A more robust production camera or a solid DV Cam is more ideal for long running installations that require a really good image (and can't use a webcam for whatever reason), but make sure to do a lengthy test run before installing. Note: if tested and implemented with care, some DSLR's can perform just fine for long installation runs (one person has mentioned one running for 6 months at 7 hours a day with no issues).

DSLR's may need their SDK and some software massaging to work correctly in your environment, although some offer hit or miss HDMI output that would require a capture card. Canon's EDSDK for example has been <a href="https://github.com/kylemcdonald/ofxEdsdk">ported</a> to openFrameworks for easy access, and <a href="http://blairneal.com/blog/canon2syphon-v1-0&gt;&lt;/a&gt;Canon2Syphon&lt;/a&gt; will let you access the camera feed in other video apps via Syphon. You can also play with custom firmware for Canon to expose additional features with the &lt;a href=">Magic Lantern Firmware.</a>

Other high end cameras also enjoy the benefits of working with cables that were designed with long cable runs in mind. Webcams over really long (10m/30ft+) USB cables can cause jitter or some other funky consistency issues, so again...test before installing whenever possible. Production quality cameras can work over HD-SDI for fairly long runs (around 200-500ft depending on who you ask), but for the really far stuff, you're best either going over a network if you don't mind latency, or going over fiber with a converter box. Fiber will get you considerably further, more than 2500ft if you need it. You'll also need a capture card for some of these, occasionally requiring a tower instead of a laptop. Adding length in almost any case is going to add to the potential for problems, so if it is something going over 200 or more feet, try to check your whole chain first.

You're sometimes limited by the capture device and its support on your intended system. Some capture devices need special drivers or other magical mysticism to work within your intended environment, so be warned before going down this path...save your receipts.

<strong>Further Reading:</strong>


<a href="http://frieder-weiss.de/eyecon/equipment.html">Frieder Weiss's writeup on using digital versus analog cameras and the latency issues involved</a> - 2008)

--------------
<h2>3. Infrared Cameras</h2>
<a href="http://www.creativeapplications.net/wp-content/uploads/2013/02/IR_example.jpeg"><img class="alignnone size-large wp-image-32564" src="http://www.creativeapplications.net/wp-content/uploads/2013/02/IR_example-640x216.jpeg" alt="IR_example" width="640" height="216" /></a>

These are really an essential tool for anyone working with interactive installations. Our visible light goes from 400-700nm, but certain cameras have the ability to see from 700-1000nm. This allows you to hide tracking lights (IR LED's or IR floodlights) and do other tracking of things not visible to the human eye.

The <a href="http://www.amazon.co.uk/dp/B000W3YQ1Y/?tag=creativenet-21" target="_blank">Playstation Eye</a> is sort of the go-to for a lot of these applications (it's used in projects like the <a href="http://www.eyewriter.org/">Eyewriter</a>) because it does 60fps (or higher!), has a range of lenses you can buy, and it's pretty cheap for the quality. <a href="http://createdigitalmotion.com/2009/08/trick-out-your-ps3-eye-webcam-best-cam-for-vision-augmented-reality/">Read more about it here</a>. It will need to be modified and requires a visible light filter to only get the IR bands. It is also a great option as a regular RGB cam since it has variable focus and you can <a href="http://peauproductions.com/store/index.php?main_page=product_info&amp;products_id=2">buy extra lenses</a> for it to get wide or narrow angles.

For the next level up, the other common one is the <a href="http://www.ptgrey.com/products/fireflymv/fireflymv_usb_firewire_cmos_camera.asp">Point Grey Firefly</a>. One tip for this one is to go ahead and buy only the monochrome version of this camera, as the color version has the additional color filter layers that can impact image quality and response. I stick with the firewire version of this camera for the bandwidth, but that can limit you on cable length (you can really only get firewire out about 10-15ft without using a repeater or amplifer, so keep that in mind when building equipment lists). The Firefly will also take a range of lenses that give you an insanely large aperture of around 1.4-1.2f and will be able to give you a much brighter image than a standard webcam. You WILL need a visible light filter for the Firefly to only get IR bands though. See Golan Levin's article on <a href="http://www.flong.com/blog/2010/a-brief-note-on-infrared-filters-87-vs-87c/">choosing the right IR filter for your application</a>. In addition to the Point Grey, you can check out these cameras from <a href="http://www.theimagingsource.com/en_US/products/cameras/">Imaging Source</a>.

When choosing these higher end cameras, also make note of their sensor size. A larger sensor will potentially increase your output resolution and decrease sensor noise, but you are left with a smaller range of lens choices. The happy medium seems to be a 1/3" sensor with a CS mount for the widest range of options.

<strong>Connection Types: USB 2 (Playstation Eye or another webcam - modified), USB 3 (Point Grey Flea 3), Kinect's IR cam, Composite/Firewire (old Sonycam's with night vision)</strong>

<strong>Resolution Range:</strong> You can generally get the same resolutions in IR that you can in regular webcams. There are plenty of tutorials out there for modifying standard webcams to only process IR light.

<strong>Range of effectiveness: </strong>Generally the same as a webcam (1ft-50ft or .3-16m). Some IR cams like the Point Grey have a wider range of security camera lenses for various zoom ranges if you need to do tracking from far away.

<strong>Infrared Pros:</strong>

• They cannot see images that are projected or on a screen (some can see content on screens...depends on screen type). IR and projection are a really nice interactive match, but you tend to need a dark space to pull these off. Are you also tired of being relegated to a dark windowless room with these tools?
• Can be used in dark spaces when used with IR emitters.
• Since they can see what the human eye can't, they are most useful for hiding certain elements like lights used for tracking points or illuminating a space.
• Tracking a point of IR light is an incredibly effective and robust tracking method because you can have a bright point of light that is invisible to the human eye.
• Good for tracking a large area like a stage flooded with IR.

<strong>Infrared Cons:</strong>

• Monochrome
• They require a healthy source of infrared light. Don't assume the lights inside will provide the type of light these cameras need to see effectively. You may need IR emitters to properly illuminate the space. People wont be able to see the extra light, but the camera will.
• Sensitive to sunlight and certain stage lights. Some stage lights will be bright enough to throw off tracking on an IR camera because the range of the light and camera overlap enough. There may be problems that the camera can see that you might not have seen with your eyes, so it can be useful to know the complete light profile of a room or to just go there with a camera beforehand.
• Certain clothes and materials look different in IR than in visible light. Can have weird effects sometimes.

<strong>Optimal environment for round the clock reliability</strong>

Room with a steady amount of IR light, either artificial or coming from a point source. Undesired sunlight can blow out an IR cam if the aperture isn't set right or if it doesn't have an automatic adjustment.

<strong>Troublesome environments</strong>

A dark room with insufficient IR light. A lot of normal light bulbs will still show up in IR even if they don't put out enough light to illuminate the IR spectrum, so keep an eye out for those in the background as pesky tracking distractions.

<strong>Further Reading for IR cams</strong>

<a href="http://frieder-weiss.de/eyecon/infrared.html">Frieder Weiss's writeup on IR cameras and equipment</a> -2008

<strong>Other IR camera suggestions: </strong>
Cheap Infrared CCTV cams work well, but you'll need a capture device
<a href="http://www.supercircuits.com/security-cameras/2-megapixel-hdcctv-box-security-camera-hdmi-blk-hdc20&gt;Full HD over HD-SDI or HDMI (needs filter!)&lt;/a&gt;&lt;br /&gt; &lt;a href=">Sony CCTV cam good in low light (needs light filter)</a>
The Sony M183 or M383 are classic low latency cams used for IR sensing, but are now discontinued, but check eBay.

---------------
<h2>4. Depth Cameras</h2>
<a href="http://www.creativeapplications.net/wp-content/uploads/2013/02/depth_sensor_camera_2.jpg"><img class="alignnone size-large wp-image-32562" src="http://www.creativeapplications.net/wp-content/uploads/2013/02/depth_sensor_camera_2-640x634.jpg" alt="depth_sensor_camera_2" width="640" height="634" /></a>

(<a href="http://web.mit.edu/newsoffice/2011/lidar-3d-camera-cellphones-0105.html" target="_blank">image source</a>)

In a way, these are an offshoot of the IR camera category but they involve some form of infrared light projection that gets reassembled as a depth image using a variety of techniques like time-of-flight (TOF) or structured light. These two detection methods are pretty different and have their own pros and cons, in terms of potential speed: <a href="http://www.computervisiononline.com/books/computer-vision/time-flight-cameras">read about their differences here</a>.

The information that comes back in a depth image is much richer than the usual "2D" image captured by the cameras above, and it gives you the ability to more easily and robustly detect things like hands and fingers. Tracking those features would be difficult and require very controlled conditions with just a monochrome 2D image. The depth information makes it easier for you to detect the difference between a person and the background, and therefore assign more meaningful information to the human trying to interact. This is why it is easier for the Kinect to give you a person's skeletal information, something that would be difficult for just a regular 2D IR image.

<iframe src="http://www.youtube.com/embed/7QrnwoO1-8A?rel=0" width="640" height="480" frameborder="0" allowfullscreen="allowfullscreen"></iframe>

There are also other methods of obtaining the same information with a high framerate webcam and a projector (structured light). Another method called <a href="http://en.wikipedia.org/wiki/LIDAR">LIDAR</a> scanning uses lasers and a method of measuring the reflected light to construct a high resolution depth image. LIDAR is usually more effective than other methods at measuring an incredibly large area or the front of a building (for quickly getting a 3D model of the facade for a projection mapping surface).

<strong>Connection types:</strong> Primarily USB2 (<a href="http://www.amazon.co.uk/dp/B0036DDW2G/?tag=creativenet-21" target="_blank">Kinect</a>,<a href="http://www.amazon.co.uk/dp/B005UHB8EK/?tag=creativenet-21" target="_blank"> Asus Xtion</a>, <a href="http://www2.panasonic.biz/es/densetsu/device/3DImageSensor/en/index.html">Panasonic D-Imager</a>, <a href="http://click.intel.com/intelsdk/Creative_Interactive_Gesture_Camera_Developer_Kit-P2061.aspx">Intel/Creative Time of Flight cams</a>), other interfaces in more research oriented/industrial cameras.

<strong>Resolution Range:</strong> This mostly tends to top out around 320x240 @30fps for the more consumer level cameras, mostly for TOF. TOF cameras use different sensors than standard CMOS cams which impacts their speed and resolution. The Kinect is faster and higher resolution because they just use a standard IR cam.  Check the individual camera for it's maximum resolution.

<strong>Range of effectiveness:</strong> Typically less than 10-12ft ( 3-4m).  Some cameras like the Intel/Creative TOF camera are really only designed for desk use and give you about 1m of effective distance, if that. Other TOF cameras like the D-Imager can give you up to 10m of range though. Makes certain sensors not very robust for use on large stages. Requires multiple sensors to cover a large area and thus complicates the CV processing chain and hardware setup. LIDAR can do a large area, but not necessarily in real time.

<strong>Depth Camera Pros:</strong>

• Depth images give you the option of really amazing background subtraction because you can totally ignore everything beyond about 10ft (with a Kinect).
• Processed depth images give you a lot of great tracking information like hand skeleton, body skeleton, shape normals. You can build 3D models of rooms or objects. You can do fairly high quality body and facial motion capture for use in 3D rendering programs.
• Isn't affected by light from a projector. A lot of the same good qualities as standard IR, but they should only be used if you <em>need</em> depth information...they are not preferred over regular IR. Again, do your best to choose right tool for the job.

<strong>Depth Camera Cons:</strong>

• Because of the use of IR, these cameras will also be sensitive to changes in sunlight.
• Do not rely on depth cameras if you need a sharp, clean outline of your subject. You will get jagged artifacts that will need to be blurred or processed to get smooth lines.
• Structured light cameras aren't able to work at an incredibly close range (ie right in front of them). Time of flight cameras are a little more robust in this regard, and are better if you need to use them really close up.
• Certain surfaces will interfere with the ability to produce a good depth image. Shiny surfaces will effectively be invisible or cause strange reflection artifacts in your image.
• Using multiple systems together occasionally requires special consideration. Overlapping structured light from the Kinect (if they are right next to each other) can cause double images to appear due to the extra light grid. If the Kinects are more perpendicular to each other, this negative effect is less likely. You can also use this trick: attach a vibrating motor to one Kinect to make the other sensor's dots blur, and the vibrating sensor's own dots will stay in focus.
• Fairly limited effective range.

<strong>Depth Image Examples:</strong>

LIDAR/Structured light was used to get the massive scans of the spaces in this Radiohead video for House of Cards:

<iframe src="http://www.youtube.com/embed/8nTFjVm9sTQ?rel=0" width="640" height="480" frameborder="0" allowfullscreen="allowfullscreen"></iframe>

Kinect used for skeleton tracking in this interactive DJ piece:

<iframe src="http://www.youtube.com/embed/WOtdH5ECJIo?rel=0" width="640" height="360" frameborder="0" allowfullscreen="allowfullscreen"></iframe>

<strong>Further reading:</strong>

If you're just looking for stereo vision capture that can infer depth info, check out the <a href="http://www.ptgrey.com/products/bumblebee2/bumblebee2_stereo_camera.asp&gt; Point Grey Bumblebee &lt;/a&gt;&lt;/p&gt; &lt;p&gt;&lt;a href=">Readings on structured light and how it works</a>

--
<h2>5. Thermal Cameras</h2>
<a href="http://www.creativeapplications.net/wp-content/uploads/2013/02/thermal.jpg"><img class="alignnone size-large wp-image-32588" src="http://www.creativeapplications.net/wp-content/uploads/2013/02/thermal-640x488.jpg" alt="thermal" width="640" height="488" /></a>

<small>(<a href="http://www.humintell.com/2011/09/truthfulness-detection/thermal/" target="_blank">image source</a>)</small>

<a href="http://en.wikipedia.org/wiki/Thermographic_camera" target="_blank">http://en.wikipedia.org/wiki/Thermographic_camera</a>

These cameras are comparatively rare to see in use in interactive installations because they are still prohibitively expensive compared to most other ones. They aren't totally unobtainable ( roughly $1000-20000) but that higher price tag makes them a little less desirable for early exploration on projects. It's a shame because these cameras offer a lot of abilities that just aren't possible with the other kinds of cameras.

There are various types of cameras to look at in this class, mostly pertaining to which part of the IR spectrum you're trying to see. You have the option of Long Wave IR, Mid Wave IR, and Short Wave IR. For thermal imaging, you'll mostly want to work with Long Wave IR, in the 7000-14000nm range.

I have not personally used one of these cameras yet, but they have some properties that would be really amazing in the tool belt of people making interactive installations.

Check out this guy doing some random demos with a thermal camera:

<iframe src="http://www.youtube.com/embed/6mV4ecEbV1s?rel=0" width="640" height="480" frameborder="0" allowfullscreen="allowfullscreen"></iframe>

<strong>Connection types:</strong> Most are made to be integrated into existing systems and either have proprietary connections or just output composite video. <a href="http://www.thermitrack.com/">Some cameras communicate X/Y position of blobs.</a>

<strong>Resolution range:</strong> Some are very low resolution (the Thermitrack is 16 x 16px) and some are close to a VGA range, but don't expect to find HD thermal for cheap. You also get a variety of frame rates and contrast ranges.

<strong>Thermal Camera Pros:</strong>

• Normal visible light doesn't have much of an effect on a thermal camera.
• Good for tracking a large area like a stage.
• Gives you the ability to more definitely identify people because of their heat signature...whereas other objects and materials may not show up at all if they are warmer.
• Fairly robust for daytime to night time interaction because people will be the same temperature and appear in the proper dynamic range.
• Give you the ability to track invisible phenomena like hot air from breath, or residual heat from something like a hand leaving a warm mark on a surface, or a cold blast of water hitting a warm surface.
• Can see through certain materials and walls.
• Thermal cameras can see through certain kinds of clothing.

<strong>Thermal Camera Cons:</strong>

• As these are occasionally considered military grade equipment, there may be export restrictions, so be wary when planning on traveling abroad.
• Expensive
• Difficult to integrate - require either custom electronics or capture hardware
• Thermal cameras can see through certain kinds of clothing.
• Not all lights are invisible to thermal cameras...if it's producing heat or radiating it, the camera will see it.
• Thermal imaging sometimes results in ghosting of movement due to the sensor method.
• They are unable to see through windows/glass because the range of radiation ends up being reflected before it transmits through the glass to the camera. <a href="http://answers.yahoo.com/question/index?qid=20081001100003AAH2Ouo">See here for a more involved explanation of why</a>.
• Certain hot materials may result in unforeseen difficulties with using thermal imaging in certain environments. Requires a different type of thinking in order to anticipate things that will be overly hot or cold in the space of the installation.

<strong> Further reading:</strong>

<a href="http://en.wikipedia.org/wiki/People_counter">People counters (wiki)</a>

<a href="http://www.dbpharrison.com/tag/thermitrack/">Thermitrack usage</a>

<strong>6. Experimental technologies</strong>

These are cameras that haven't really reached the public market yet, or just haven't had the chance to be explored for interactive installations. This category can also include less conventional means of getting an image or tracking objects, or other tools that can be effected by visible light in the space (for example, the <a href="https://www.leapmotion.com/">Leap Motion</a> controller can be thrown off by excessive amounts of IR light). There are also light field cameras, like the <a href="https://www.lytro.com/">Lytro</a>, that are able to get a different kind of information for shooting a scene than a normal CMOS detector can get. Some of these technologies are either brand new or too expensive or not accessible by most so they don't get a lot of use in interactive installations (yet) but it's only a matter of time for several of them.

Lytro example:

<iframe src="http://pictures.lytro.com/lytroweb/pictures/431128/embed" width="640" height="480" frameborder="0" scrolling="no" allowfullscreen="allowfullscreen"></iframe>

<strong>Notes:</strong>

Huge thanks to <a href="http://kylemcdonald.net/">Kyle McDonald</a>, <a href="http://theowatson.com/">Theo Watson</a>, <a href="http://thesystemis.com/">Zach Lieberman</a> and <a href="http://www.flong.com/">Golan Levin</a> for some great additional tips to help round out some of the suggestions here.

The above information is really from my own experience of using various camera technologies in interactive settings. As usual, try to do your own research first and use this as a guide of someone else's experiences. Some cameras I've used more (webcam), some less or not at all (thermal), so take some of my suggestions with a grain of salt although some pointers I've absorbed from some of the experts in the field.

Also, it would be good to go hit up wikipedia or other more accredited sources for the technical information on the visible light spectrum versus near and far infrared if you need a refresher, I have left most of those details out. Really understanding the science behind how the different cameras work can expand how well you actually use the camera in practice.