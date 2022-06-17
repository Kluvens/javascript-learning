# SVG

SVG is an XML language, similar to XTML, whcih can be used to draw vector graphics.
It can be used to create an image either by specifying all the lines and shapes necessary, by modifying already existing raster images,
or by a combination of both.

A simple SVG document consists of nothing more than the ```<svg>``` root element and several basic shapes that build a graphic together.
In addition there is the ```<g>``` element, which is used to group several basic shapes together.

A simple example:
``` svg
<svg version="1.1"
     width="300" height="200"
     xmlns="http://www.w3.org/2000/svg">

  <rect width="100%" height="100%" fill="red" />

  <circle cx="150" cy="100" r="80" fill="green" />

  <text x="150" y="125" font-size="60" text-anchor="middle" fill="white">SVG</text>

</svg>
```
Explains:
- We start with the <svg> root element
- The background is set to red by drawing a rectangle <rect> taht covers the complete image area.
- A green circle ```<circle>``` with a radius of 80px is drwan atop the center of the red rectangle.
- The text "SVG" is drawn. The interior of each letter is filled in with white. The text is positioned by setting an anchor where we want the midpoint to be: in this case, the midpoint should correspond to the center of the green circle.

## Position
The grid: the top left corner of the document is considered to be the point (0,0), or point of origin.
Positions are then measured in pixels from the top left corner, with the positive x direction being to the right, and the positive y direction being to the bottom.

Example:
The element ```<rect x="0" y="0" width="100" height="100" />``` 
defines a rectangle from the upper left corner, that spans from there 100px to the right and to the bottom.
  
