---
layout: page
#
# Content
#
subheadline: ""
title: "Mapping watersheds in Allegheny County"
teaser: "Playing with user interation for small watersheds plus more from twitter"
categories:
  - maps
tags:
  - maps
#
# Styling
#
image:
  title: ""
  thumb: ""
  homepage: 
  caption: ""
  url: ""
---


 ### Watersheds 
 <iframe width="100%" height="520" frameborder="0" src="https://bl.ocks.org/wontgruber/raw/a5fb00aa35d140855dacc7337c4f85ec/" allowfullscreen webkitallowfullscreen mozallowfullscreen oallowfullscreen msallowfullscreen></iframe>
 [Check out the code for this map here](https://bl.ocks.org/wontgruber/a5fb00aa35d140855dacc7337c4f85ec)
 
My goals with this map were to successfully apply that hover-over-a-watershed-and-the-polygon-lights-up technique and to create a watershed map that was more interactive than I typically see. I also ended up learning about how water flows through the city. Cool. The map is searchable, so you can find your house and see what watershed you live in. 
 
 The goals were visual. Given that, the hue (darkness/lightness) of the small watershed is basically meaningless. The shading helps differentiate between neighboring polygons, but it is based on the size of the watershed (which is redundant and is cartographic bad practice). Instead, I should have had hue based on something that adds more information density to the map (e.g. a water quality metric). I did not do that because I'm trying to keep my projects small, focused, and complete-able for now. The watershed names and shapes are correct. 

