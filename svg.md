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

## Basic shapes

### rectangle
The <rect> element draws a rectangle on the screen.
There are 6 basic attributes that control the position and shape of the rectangles on screen.
The one on the right has its rx and ry parameters set, giving it rounded corners.
If they're not set, they default to 0.
``` svg
<rect x="10" y="10" width="30" height="30"/>
<rect x="60" y="10" rx="10" ry="10" width="30" height="30"/>
```
- x - The x position of the top left corner of the rectangle.
- y - The y position of the top left corner of the rectangle.
- width - The width of the rectangle
- height - The height of the rectangle
- rx - The x radius of the corners of the rectangle
- ry - The y radius of the corners of the rectangle

### circle
The <circle> element draws a circle on the screen.
It takes 3 basic parameters to determine the shape and size of the element.
``` SVG
<circle cx="25" cy="75" r="20"/>
```
- r - The radius of the circle.
- cx - The x position of the center of the circle.
- cy - The y position of the center of the circle.

### Ellipse
An <ellipse> is a more general form of the <circle> element, where you can scale the x and y radius
(commonly referred to as the semimajor and semiminor axes in maths) of the circle separately.
``` svg
<ellipse cx="75" cy="75" rx="20" ry="5"/>
```
- rx - The x radius of the ellipse.
- ry - The y radius of the ellipse.
- cx - The x position of the center of the ellipse.
- cy - The y position of the center of the ellipse.

### Line
The <line> element takes the positions of two points as parameters and draws a straight line between them.
``` svg
<line x1="10" x2="50" y1="110" y2="150" stroke="black" stroke-width="5"/>
```
- x1 - The x position of point 1.
- y1 - The y position of point 1.
- x2 - The x position of point 2.
- y2 - The y position of point 2.

### Polyline
A <polyline> is a group of connected straight lines. Since the list of points can get quite long, all the points are included in one attribute:
``` svg
<polyline points="60, 110 65, 120 70, 115 75, 130 80, 125 85, 140 90, 135 95, 150 100, 145"/>
```

### Polygon
A <polygon> is similar to a <polyline>, in that it is composed of straight line segments connecting a list of points. For polygons though, the path automatically connects the last point with the first, creating a closed shape.
``` svg
<polygon points="50, 160 55, 180 70, 180 60, 190 65, 205 50, 195 35, 205 40, 190 30, 180 45, 180"/>
```
