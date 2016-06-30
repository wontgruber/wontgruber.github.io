<!DOCTYPE html>
<html>
  <head>
    <title>#WUGC2016 Tweets</title>
    <meta name="viewport" content="initial-scale=1.0, user-scalable=no" />
    <meta http-equiv="content-type" content="text/html; charset=UTF-8"/>
    <link rel="shortcut icon" href="https://cartodb.com/assets/favicon.ico" />
    <style>
      html, body, #map {
        height: 100%;
        padding: 0;
        margin: 0;
      }
      #desc {
          position:absolute;
          top:12px;
          right:12px;
          border: 1px solid #999;
          border-radius: 5px;
          width: 125px;
          background: rgba(255,255,255,0.9);
          padding: 0 10px 0 10px;
          font-family: Georgia, serif;
      }
    </style>
    
    <style type="cartocss/text" id="cartocss">
    /** torque visualization */
   Map {
    -torque-frame-count:512;
    -torque-animation-duration:30;
    -torque-time-attribute:"postedtime";tim
    -torque-aggregation-function:"count(cartodb_id)";
    -torque-resolution:2;
    -torque-data-aggregation:linear;
    }
    #twitter_wugc2016{
      comp-op: lighter;
     marker-fill-opacity: 0.9;
     marker-line-color: #FFF;
      marker-line-width: 0;
      marker-line-opacity: 1;
      marker-type: ellipse;
      marker-width: 6;
      marker-fill: #0F3B82;
    }
    #twitter_wugc2016[frame-offset=1] {
    marker-width:8;
    marker-fill-opacity:0.45; 
    }
    #twitter_wugc2016[frame-offset=2] {
    marker-width:10;
    marker-fill-opacity:0.225; 
    }
    #twitter_wugc2016[frame-offset=3] {
    marker-width:12;
    marker-fill-opacity:0.15; 
    }
    #twitter_wugc2016[frame-offset=4] {
    marker-width:14;
    marker-fill-opacity:0.1125; 
    }
    #twitter_wugc2016[frame-offset=5] {
    marker-width:16;
    marker-fill-opacity:0.09; 
    }
    </style>

    <link rel="stylesheet" href="https://cartodb-libs.global.ssl.fastly.net/cartodb.js/v3/3.15/themes/css/cartodb.css" />
  </head>
  <body>
    <div id="map"></div>
    <div id="desc"><h3>#WUGC2016<span id="location"></span></h3></div>

    <script src="https://cartodb-libs.global.ssl.fastly.net/cartodb.js/v3/3.15/cartodb.js"></script>
    
  <script>
  
    function main() {
    // Instantiate new map object, place it in 'map' element
    var map = new L.Map('map', {
      center: [30,15], // Western Egypt
      zoom: 2,
      scrollWheelZoom: false,
      doubleClickZoom: false
      });
  // setup layer
  var layerSource = {
    type: 'torque',
    options: {
      user_name: 'nwilgruber', // replace with your user name
      table_name: 'twitter_wugc2016',
      cartocss: $("#cartocss").html()
    }
  }
  var layer = L.tileLayer('http://{s}.basemaps.cartocdn.com/dark_all/{z}/{x}/{y}.png',{
  attribution: '&copy; <a href="http://www.openstreetmap.org/copyright">OpenStreetMap</a> contributors, &copy; <a href="https://cartodb.com/attributions">CartoDB</a>'
  });
  map.addLayer(layer);
  // put torque layer on top of basemap
  cartodb.createLayer(map, layerSource)
    .addTo(map)
    .done(function(layer) {
      // do stuff
      var torqueLayer = layer;
      // once animation is loaded, automatically play
      torqueLayer.on('load', function() {
      torqueLayer.play();
      });
    })
    .error(function(err) {
      console.log("Error: " + err);
    });
}
window.onload = main;
  </script>
    
  </body>
</html>
