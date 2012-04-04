##API
###Filter.getImage(url, callback)
Gets an image, sets `this.img` with an image element and calls `callback` when the image loads.

###Filter.putImage([url, x, y, width, height])
Get's an image and put's it onto the canvas at the specified coordinates.

###Filter.get([x, y, width, height])
Get's an `ImageData` at specified coordinates. If none are given, it will return the whole which isn't advisable if you value your browser.

###Filter.generate([height, width] || [CanvasPixelArray])
Create's a dummy `ImageData` for manipulation from existing data or specified height and width.

###Filter.put([width, height])
Puts the current `ImageData` object onto the canvas

###Filter.loop(callback)
Loops through the ImageData within the filter executing the supplied function. Parameters supplied to the callback are the current color value within the data loop, the type of color value (0 = Red, 1 = Blue, 2 = Green, 3 = Alpha), the length of the PixelArray and the current iteration. _NOTE: If no value is returned from the callback, it will have no effect!_

	(new Filter).generate(40, 40).loop(function(colorValue, type, length, i) {
		if(type === 0) return colorValue + 10;
	}).put();

###Filter.new(filterName, callback)
For storage in the filter object. The callback is called when the filter name given wanted. No parameters. `this` is the currently operating filter object.

###Filter.run(filterName)
Runs the filter of the specified name over the current `ImageData` Object

###Filter.convolve(Array2D)
Convolves the image with the specified kernel.

###Filter.pixelate(pixelSize)
Pixelate the image. pixelSize is the size of the pixelated pixels in pixels. What?

###CanvasRenderingContext2D.prototype.filter(filterName)
Filters the whole canvas with the specified filter.
	
	canvas.getContext("2d").filter(filter);


