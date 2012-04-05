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

###Filter.loop(callback, overrideReplacingValues)
Loop over a pixel array in a nice way. It iterates y axis and for every y iteration, it iterates over the x axis. It supplies the color values and the x and y position as parameters (see example below). If an array of rgba color values are returned it inputs them into the current image data. To override this (i.e. stop it from replaceing the values and the currentImage data) set the override param to `true`.

	(new Filter).get().loop(function(rgba, x, y) {
		var r = rgba[0],
		    g = rgba[1],
		    b = rgba[2],
		    a = rgba[3];

		return [r * 10, g * 10, b * 10, 255];
	}).put();

###Filter.new(filterName, callback)
For storage in the filter object. The callback is called when the filter name given wanted. No parameters. `this` is the currently operating filter object.

###Filter.blur()
Blur the current `imageData` object

	(new Filter).get().blur();

###Filter.convolve(Array2D)
Convolves the image with the specified kernel.

###Filter.pixelate(pixelSize)
Pixelate the image. pixelSize is the size of the pixelated pixels in pixels. What?


