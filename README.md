<!DOCTYPE html>
<html>
  <!-- The following code has been developed by students and/or researchers of the Freshman Research Initiative DIY Diagnostics Stream at The University of Texas at Austin.  This code is shared for demonstration purposes and should not be considered a product -- it is for entertainment purposes only.  Any user of this code does so at their own risk. Members of the DIY Stream, FRI, and The University of Texas system are not liable for anything related to this code.

Authors in chronological order of contribution:
Christine Yu
 
Further Information:
http://cns.utexas.edu/fri
 
Research Educator:
Timothy Riedel
triedel@utexas.edu
 
Brief Description of Goal of Code:
To create an app for the user to determine geolocation during use
 
Known Issues:


https://www.w3schools.com/html/html5_geolocation.asp
-->

  	
   <head> 
      <title>Hello World</title>  
      <meta name="viewport" content="width=device-width, initial-scale=1">
      <meta name="apple-mobile-web-app-capable" content="yes">
      <link rel="stylesheet" href="w3.css">
      <link rel="stylesheet" href="w3-colors-flat.css">
   </head> 
  
<body>

<p>Click the button to get your coordinates!</p> <!--text for user to read-->
<button onclick="getLocation()">Here!</button> <!--button for user for demonstration-->
<p id="demo"></p>

<script>
var x = document.getElementById("demo");
function getLocation() {
  if (navigator.geolocation) {
    navigator.geolocation.getCurrentPosition(showPosition);
  } else {
    x.innerHTML = "Geolocation is not supported by this browser.";
  }
}

function showPosition(position) {
  x.innerHTML = "Latitude: " + position.coords.latitude + 
  "<br>Longitude: " + position.coords.longitude; 
}
  
  <!-- this part of the script is to let user know if there is an error in retrieivng coordinates of location -->
  function showError(error) {
  switch(error.code) {
    case error.PERMISSION_DENIED:
      x.innerHTML = "User denied the request for Geolocation."
      break;
    case error.POSITION_UNAVAILABLE:
      x.innerHTML = "Location information is unavailable."
      break;
    case error.TIMEOUT:
      x.innerHTML = "The request to get user location timed out."
      break;
    case error.UNKNOWN_ERROR:
      x.innerHTML = "An unknown error occurred."
      break;
  }
}
</script>

</body>
</html>
