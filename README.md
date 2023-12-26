# CoffeCounter
Displays amount of coffe brewings on a 2.9" OEPL Screen
<br><img src="brewertag.jpg" width="50%" alt="BrewerTag for 2.9">

<h2>Requirements</h2> 
Home Assistant and a working <a href="https://openepaperlink.de/">OpenEpaper</a> setup
<br>with <a href="https://github.com/jonasniesner/open_epaper_link_homeassistant">HA Integration</a>

<h2>Hardware Setup Prerequisites</h2> 
<ul>
  <li>1 Coffe machine... duh</li>
  <li>1 power plug with power metering functionality</li>
</ul>

<h2>Home Assistant Setup Prerequisites</h2> 
<ul>
  <li>1 counter entity (create a helper)</li>  
  <ul>
    <li>Min count: 0</li> 
    <li>Max count: You decide </li> 
  </ul>
  <li>1 binary template sensor (create a helper) </li>
  <ul>
    <li>binary sensor should be true when power is above your selected treshold</li> 
    <li>Adjust the 100 below accordingly </li> 
    <li>{{ states('sensor.YourPowerPlugPowerSensor') > 100 }} </li> 
  </ul>
</ul>

<h2>Yaml file edit</h2>
Edit my yaml to fit in the names of your sensors and counter
<br><br>
<b>Use search and replace for </b>
<br>The counter: counter.kaffebryggningar
<br>The binary sensor: binary_sensor.kaffebryggning
<br><br>
Monitor your power plug and watch how long it takes for
<br>it to brew a serving (# of cups) of choice then calculate the 
<br>"time per cups" in seconds.
<br>Edit variable <b>boil_tpc</b> to your calculated time per cups
<br>
<br>Make sure to download the fonts or edit the variables to your own fonts and 
<br>their respective paths
