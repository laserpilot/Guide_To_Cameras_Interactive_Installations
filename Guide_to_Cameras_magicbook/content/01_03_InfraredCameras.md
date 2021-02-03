# Infrared Cameras
![infraredimage](infrared.jpg)

Infrared cameras have historically been one of the most important tools for artists working with interactive installations. In earlier years, an abundance of installations were set up in dark spaces for either aesthetic reasons or due to the technological limitations of display technology - aka dim projectors. In recent years, as installations move into well lit spaces and tracking algorithms improve, infrared camera relevance has started to shift. However, they still have some unique capabilities that come in handy for certain types of installations.

As a quick primer, visible light goes from 400-700nm, but certain cameras have the ability to see infrared light from 700-900nm. This allows you to capture things that are not visible to the human eye, like IR tracking lights or a dark space illuminated by infrared light. Most cameras that aren't marketed as exclusively IR capable have infrared filters that block IR light, but in some cases, that filter can be manually removed. In order to limit a camera's ability to only see in infrared light, some may need filters that block all visible light - more info on that [here](http://www.flong.com/blog/2010/a-brief-note-on-infrared-filters-87-vs-87c/)

There isn't a specific go-to camera for infrared these days. You can modify certain RGB cameras by removing their infrared filter..................[WIP]

For the next level up, the other common one is the <a href="http://www.ptgrey.com/products/fireflymv/fireflymv_usb_firewire_cmos_camera.asp">Point Grey Firefly</a>. One tip for this one is to go ahead and buy only the monochrome version of this camera, as the color version has the additional color filter layers that can impact image quality and response. I stick with the firewire version of this camera for the bandwidth, but that can limit you on cable length (you can really only get firewire out about 10-15ft without using a repeater or amplifer, so keep that in mind when building equipment lists). The Firefly will also take a range of lenses that give you an insanely large aperture of around 1.4-1.2f and will be able to give you a much brighter image than a standard webcam. You WILL need a visible light filter for the Firefly to only get IR bands though. See Golan Levin's article on <a href="http://www.flong.com/blog/2010/a-brief-note-on-infrared-filters-87-vs-87c/">choosing the right IR filter for your application</a>. In addition to the Point Grey, you can check out these cameras from <a href="http://www.theimagingsource.com/en_US/products/cameras/">Imaging Source</a>.


**Connection Types:** USB 2 (Playstation Eye or another webcam - modified), USB 3 (Point Grey Flea 3), Kinect's IR cam, Composite/Firewire (old Sonycam's with night vision)

**Resolution Range:** You can generally get the same resolutions in IR that you can in regular webcams. There are plenty of tutorials out there for modifying standard webcams to only process IR light.

**Range of effectiveness:**Generally the same as a webcam (1ft-50ft or .3-16m). Some IR cams like the Point Grey have a wider range of security camera lenses for various zoom ranges if you need to do tracking from far away.

**Infrared Pros:**

- They cannot see images that are projected or on a screen (some can see content on screens...depends on screen type). IR and projection are a really nice interactive match, but you tend to need a dark space to pull these off. Are you also tired of being relegated to a dark windowless room with these tools?
- Can be used in dark spaces when used with IR emitters.
- Since they can see what the human eye can't, they are most useful for hiding certain elements like lights used for tracking points or illuminating a space.
- Tracking a point of IR light is an incredibly effective and robust tracking method because you can have a bright point of light that is invisible to the human eye.
- Good for tracking a large area like a stage flooded with IR.

**Infrared Cons:**

- Monochrome
- They require a healthy source of infrared light. Don't assume the lights inside will provide the type of light these cameras need to see effectively. You may need IR emitters to properly illuminate the space. People wont be able to see the extra light, but the camera will.
- Sensitive to sunlight and certain stage lights. Some stage lights will be bright enough to throw off tracking on an IR camera because the range of the light and camera overlap enough. There may be problems that the camera can see that you might not have seen with your eyes, so it can be useful to know the complete light profile of a room or to just go there with a camera beforehand.
- Certain clothes and materials look different in IR than in visible light. Can have weird effects sometimes.

**Optimal environment for round the clock reliability**

Room with a steady amount of IR light, either artificial or coming from a point source. Undesired sunlight can blow out an IR cam if the aperture isn't set right or if it doesn't have an automatic adjustment.

**Troublesome environments**

A dark room with insufficient IR light. A lot of normal light bulbs will still show up in IR even if they don't put out enough light to illuminate the IR spectrum, so keep an eye out for those in the background as pesky tracking distractions.

**Further Reading for IR cams**

<a href="http://frieder-weiss.de/eyecon/infrared.html">Frieder Weiss's writeup on IR cameras and equipment</a> -2008

**Other IR camera suggestions:**
Cheap Infrared CCTV cams work well, but you'll need a capture device
<a href="http://www.supercircuits.com/security-cameras/2-megapixel-hdcctv-box-security-camera-hdmi-blk-hdc20&gt;Full HD over HD-SDI or HDMI (needs filter!)&lt;/a&gt;&lt;br /&gt; &lt;a href=">Sony CCTV cam good in low light (needs light filter)</a>
The Sony M183 or M383 are classic low latency cams used for IR sensing, but are now discontinued, but check eBay.
