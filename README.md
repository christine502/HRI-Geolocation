
<html>
<body>

<p>Click the button to get your coordinates!</p> //text for user to read
<button onclick="getLocation()">Here!</button> //button for user for demonstration
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
</script>

</body>
</html>
