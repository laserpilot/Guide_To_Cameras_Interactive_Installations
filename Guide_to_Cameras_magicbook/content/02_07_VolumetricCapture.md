# Volumetric Capture

Volumetric capture is another specialized approach that is very similar to motion capture systems, and the two are often used in tandem, particularly for modern cinematic video game animations.  In its simplest form, volumetric capture is really a hybrid image capture approach that uses a regular camera matched with a depth camera, often in large 360º arrays of both, that allows the creation of 3D content. The more general term for volumetric capture is [photogrammetry](https://en.wikipedia.org/wiki/Photogrammetry). There are also systems that just use large arrays of regular cameras instead of matching them with depth cameras. "Portrait" mode on modern smartphones is also a form of volumetric capture that combines two photos from two different lenses.

Most of these professional systems require dozens of precisely cameras and an array of computers to ingest the massive amounts of data coming in. This data is then processed and turned into point clouds or meshes that can then be viewed in 3D rendering software or game engines. As of this writing, there are several systems and vendors out there that can achieve volumetric capture. Building a high quality full 360º system yourself would take considerable planning and budget. 

[Depthkit](https://www.depthkit.tv) is probably the most well known and accessible system for doing volumetric filmmaking. Depthkit, at its most basic, involves mounting a DSLR and a depth sensing camera together and doing some pre-alignment steps with their software system. As you capture both depth and color information, software is able to combine those two feeds into 3D content. Depthkit can be used by a wider group of people due to the lower barrier of entry on equipment and setup. The main trade offs are that the most common setup usually involves a single camera which means you typically get a limited amount of 3D information from the front surface of whatever you're filming.

Larger "volcap" systems involve whole studios (although there are some systems that can be moved around). [Microsoft's Mixed Reality Capture Studio](https://www.microsoft.com/en-us/mixed-reality/capture-studios) is one example of the high end of these sorts of offerings. One version of their system uses 106 cameras to capture.

Mention Volucams (https://twitter.com/BenSchwartzXR/status/1311704650475884545)

[Volucam](http://www.ioindustries.com/volucam.html)

Re-lighting, scene size limitations, complex scene limitations, movement limitations, bandwidth of final assets (mesh+color data per frame)

[WIP]