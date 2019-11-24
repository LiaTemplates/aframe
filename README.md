<!--
author:   André Dietrich

email:    andre.dietrich@ovgu.de

version:  0.0.2

language: en

narrator: US English Female

logo:     demo.gif

comment:  Demo of using A-Frame in LiaScript for creating simple 3D scenes and
          add augmented reality movies and images.

script:   https://aframe.io/releases/0.9.0/aframe.min.js
          https://unpkg.com/aframe-text-geometry-component@0.5.1/dist/aframe-text-geometry-component.min.js

-->

# AFrame - Demo

                         --{{0}}--
A demo, that shows how [AFrame](https://aframe.io) can be used in
[LiaScript](https://LiaScript.github.io)

__Try it on LiaScript:__

https://liascript.github.io/course/?https://raw.githubusercontent.com/liaTemplates/aframe/master/README.md

__See the project on Github:__

https://github.com/liaTemplates/aframe

                         --{{1}}--

In contrast to a common LiaScript template, there is no need, to import this
document. Simply copy the code below and paste it into your main comment header,
see the code in the raw file of this document.

                           {{1}}
``` markdown
script: https://aframe.io/releases/0.9.0/aframe.min.js
        https://unpkg.com/aframe-text-geometry-component@0.5.1/dist/aframe-text-geometry-component.min.js
```

                           {{1}}
https://raw.githubusercontent.com/liaTemplates/aframe/master/README.md

## Hello WebVR


<div style="height: 400px; width: 100%">
<a-scene embedded background="color: #ECECEC">
  <a-box position="-1 0.5 -3" rotation="0 45 0" color="#4CC3D9" shadow></a-box>
  <a-sphere position="0 1.25 -5" radius="1.25" color="#EF2D5E" shadow></a-sphere>
  <a-cylinder position="1 0.75 -3" radius="0.5" height="1.5" color="#FFC65D" shadow></a-cylinder>
  <a-plane position="0 0 -4" rotation="-90 0 0" width="4" height="4" color="#7BC8A4" shadow></a-plane>
</a-scene>
</div>


## 360° Image

<div style="height: 400px; width: 100%">
<a-scene embedded>
  <a-sky src="https://raw.githubusercontent.com/aframevr/aframe/v0.9.0/examples/boilerplate/panorama/puydesancy.jpg" rotation="0 -130 0"></a-sky>

  <a-text font="kelsonsans" value="Puy de Sancy, France" width="6" position="-2.5 0.25 -1.5" rotation="0 15 0"></a-text>
</a-scene>
</div>
