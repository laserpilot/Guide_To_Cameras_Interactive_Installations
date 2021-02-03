# Other RGB cameras
![otherrgb](red.jpg)

[Image source](http://www.brainfarmcinema.com/red.aspx)

[EDIT IN PROGRESS]

Webcams can only go so far in terms of quality. There are various reasons for wanting something in this category. and it usually comes down to needing really high quality and high resolution images at a very low latency. You may also be working with some unusual equipment, capturing input from another computer or image device that isn't a camera or have some other concerns about image input. There are still a ton of things you can do with analog cameras that you simply cannot do yet with all digital setups.

These cameras tend to have the same qualities/pros/cons as the standard webcam does. There are just a few important differences in certain use cases.

Beware of interlacing from analog capture devices. Tracking algorithms will not be a fan of that. Also be aware of anything involving [NTSC versus PAL](https://www.wisegeek.com/what-is-the-difference-between-ntsc-and-pal.htm). You will be able to capture at a higher resolution and full frame rate, sometimes up to 60fps (or higher!) and 1080p and beyond, but that comes at a hefty price tag and will consume a large amount of computational resources. Some capture tools let you do full 4K resolution preview monitoring, but these occasionally need their own software pipes to get something that big into your processor. Check out this &lt;a href=">Black Magic 4K Ultra Studio</a> for an option for getting 4K input.

There are some fantastic options for getting HDMI/SDI input into laptops now via thunderbolt connections, like the <a href="http://www.blackmagicdesign.com/products/ultrastudio/">Blackmagic Ultrastudio</a> or <a href="http://www.blackmagicdesign.com/products/intensity/">Blackmagic Intensity</a>. These capture devices won't always work if you're sending signal from another computer though, so check your video color formats first for compatibility.

Capturing with a <a href="http://www.amazon.co.uk/s/?_encoding=UTF8&amp;camp=1634&amp;creative=19450&amp;field-keywords=DSLR%20cameras&amp;linkCode=ur2&amp;rh=i%3Aaps%2Ck%3ADSLR%20cameras&amp;tag=creativenet-21&amp;url=search-alias%3Daps" target="_blank">DSLR</a> all day would be great because you'll get the best image for the price range, but those cameras are not always designed to be left on for extended durations. DSLR's can easily suffer from heating issues or auto-shutoff if left on for too long. A more robust production camera or a solid DV Cam is more ideal for long running installations that require a really good image (and can't use a webcam for whatever reason), but make sure to do a lengthy test run before installing. Note: if tested and implemented with care, some DSLR's can perform just fine for long installation runs (one person has mentioned one running for 6 months at 7 hours a day with no issues).

DSLR's may need their SDK and some software massaging to work correctly in your environment, although some offer hit or miss HDMI output that would require a capture card. Canon's EDSDK for example has been <a href="https://github.com/kylemcdonald/ofxEdsdk">ported</a> to openFrameworks for easy access, and <a href="http://blairneal.com/blog/canon2syphon-v1-0&gt;&lt;/a&gt;Canon2Syphon&lt;/a&gt; will let you access the camera feed in other video apps via Syphon. You can also play with custom firmware for Canon to expose additional features with the &lt;a href=">Magic Lantern Firmware.</a>

Other high end cameras also enjoy the benefits of working with cables that were designed with long cable runs in mind. Webcams over really long (10m/30ft+) USB cables can cause jitter or some other funky consistency issues, so again...test before installing whenever possible. Production quality cameras can work over HD-SDI for fairly long runs (around 200-500ft depending on who you ask), but for the really far stuff, you're best either going over a network if you don't mind latency, or going over fiber with a converter box. Fiber will get you considerably further, more than 2500ft if you need it. You'll also need a capture card for some of these, occasionally requiring a tower instead of a laptop. Adding length in almost any case is going to add to the potential for problems, so if it is something going over 200 or more feet, try to check your whole chain first.

You're sometimes limited by the capture device and its support on your intended system. Some capture devices need special drivers or other magical mysticism to work within your intended environment, so be warned before going down this path...save your receipts.

**Further Reading:**

<a href="http://frieder-weiss.de/eyecon/equipment.html">Frieder Weiss's writeup on using digital versus analog cameras and the latency issues involved</a> - 2008)
