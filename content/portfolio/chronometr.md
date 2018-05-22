---
title: "Chronometr"
projecttype: "typoexperiment, variable fonts"
layout: "single.experiment"
stylesource: "chronometr.css"
draft: false
index: 15
bgcolor: "#000000"
---

<div id="clockWrapper">
	<h1 id="varClock"><span id="anim1">0</span><span id="anim2">0</span>:<span id="anim3">0</span><span id="anim4">0</span></h1>
</div>

<script>
    function checkTime(i) {
        if (i < 10) {
            i = "0" + i;
        }
        return i;
    }

    function updateTime() {
        date = new Date();
        hours = date.getHours().toString();
        minutes = date.getMinutes().toString();
        hours = checkTime(hours);
        minutes = checkTime(minutes);
        hou = hours.charAt(0);
        rs = hours.charAt(1);
        min = minutes.charAt(0);
        utes = minutes.charAt(1);

        document.getElementById("anim1").innerHTML = hou;
        document.getElementById("anim2").innerHTML = rs;
        document.getElementById("anim3").innerHTML = min;
        document.getElementById("anim4").innerHTML = utes;

        document.getElementById("anim1").style.animationDuration = hou + "s";
        document.getElementById("anim2").style.animationDuration = rs + "s";
        document.getElementById("anim3").style.animationDuration = min + "s";
        document.getElementById("anim4").style.animationDuration = utes + "s";

        setTimeout(updateTime, 1000);
    }

    document.addEventListener('DOMContentLoaded', updateTime());
</script>