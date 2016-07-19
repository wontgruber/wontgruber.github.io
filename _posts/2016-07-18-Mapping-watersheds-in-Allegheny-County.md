---
layout: page
#
# Content
#
subheadline: ""
title: "Mapping watersheds in Allegheny County"
teaser: "Playing with user interation for small watersheds"
categories:
  - maps
tags:
  - maps
#
# Styling
#
header:
    image_fullwidth: "watershed_header.jpg"
image:
  title: 
  thumb: ""
  homepage: 
  caption: ""
  url: ""
---

My goals with this map were to successfully apply that hover-over-a-watershed-and-the-polygon-lights-up technique and to create a watershed map that was more interactive than I typically see. I also ended up learning about how water flows through the city. Cool.

### Watersheds
<img src="/images/inPost_watershed_image.jpg" class="img-responsive">
[Veiw the live version of the map](https://bl.ocks.org/wontgruber/raw/a5fb00aa35d140855dacc7337c4f85ec/) |
[Check out the code](https://bl.ocks.org/wontgruber/a5fb00aa35d140855dacc7337c4f85ec/)
 
The goals were visual. Given that, the hue (darkness/lightness) of the small watersheds is basically meaningless. The shading helps differentiate between neighboring polygons, but it is based on the size of the watershed (which is redundant and cartographic bad practice). Instead, I should have had hue based on something that adds information density to the map (e.g. a water quality metric). I didn't do that because I'm trying to keep my projects small, focused, and complete-able for now. The watershed names and shapes are correct. 



