---
layout: page
title: Integrator
permalink: /integrator/
---


<html>
<head>
<meta name="viewport" content="width=device-width, initial-scale=1" />
<style>
/* Popup container - can be anything you want */
.popup {
    position: relative;
    display: inline-block;
    cursor: pointer;
    -webkit-user-select: none;
    -moz-user-select: none;
    -ms-user-select: none;
    user-select: none;
}

/* The actual popup */
.popup .popuptext {
    visibility: hidden;
    width: 360px;
    background-color: #555;
    color: #fff;
    text-align: left;
    border-radius: 12px;
    padding: 8px 10;
    position: absolute;
    z-index: 1;
    top: 125%;
    left: 100%;
    margin-left: -80px;
}


/* Toggle this class - hide and show the popup */
.popup .show {
    visibility: visible;
    -webkit-animation: fadeIn 1s;
    animation: fadeIn 1s;
}

/* Add animation (fade in the popup) */
@-webkit-keyframes fadeIn {
    from {opacity: 0;} 
    to {opacity: 1;}
}

@keyframes fadeIn {
    from {opacity: 0;}
    to {opacity:1 ;}
}
</style>
</head>
<body>

<b>Runge Kutta integrator</b> <br><br>

<p>Function:</p>
<div lang="latex">
    \\\ddot{x}=f(x,\dot{x}) \\
    x(t_0) = x_0\\
    \dot{x}(t_0) = \dot{x}_0\\
  </div>

  <span lang="latex">f</span>: <input id="functionField" type="text">
  <span lang="latex">x_0</span>: <input id="x0Field" type="text">
  <span lang="latex">\dot{x}_0</span>: <input id="p0Field" type="text"> <br><br>
  <span lang="latex">t_0</span>: <input id="t0Field" type="text">
  <span lang="latex">t_1</span>: <input id="t1Field" type="text">
  <span lang="latex">dt</span>: <input id="dtField" type="text"> <br><br>
    
    <b> Note: </b> In the definition of the function, please denote <span lang="latex" display="inline">\dot{x}</span> with  <i>x1</i> <br>
  <button id="reloadButton">Go</button> <br><br>
  <div class="popup" onclick="myFunction()">API
  <span class="popuptext" id="API">
  	<b>Api</b> <br><br>
  Example: <br>
  <i>
  {
	"x0Val":"0.0",
	"p0Val":"1.0",
	"t0Val":"0.0",
	"t1Val":"5.0",
	"dtVal":"0.1",
	"functionVal":"-x^2"
}
    </i>
  Note: the ratio <i>(t_1-t_2)/dt</i> cannot be larger than 5000. The parameter <i>dt</i> is rescaled in order to satifsy such constraint.

  </span>
</div>

<script>
// When the user clicks on div, open the popup
function myFunction() {
    var popup = document.getElementById("API");
    popup.classList.toggle("show");
}
</script>


  <div class="image">
  </div>


<script type="text/javascript" src="https://latex.codecogs.com/latexit.js"></script>
<script src="https://ajax.googleapis.com/ajax/libs/jquery/3.1.1/jquery.min.js"></script>
<script src="../js/script.js"></script>

</body>
</html>