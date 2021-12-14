<!--
author:   André Dietrich

email:    andre.dietrich@ovgu.de

version:  0.0.5

language: en

narrator: US English Female

logo:     demo.gif

comment:  Demo of using A-Frame in LiaScript for creating simple 3D scenes and
          add augmented reality movies and images.


@AFRAME.model
``` html @AFRAME.scene
<a-scene>
  <a-assets>
    <a-asset-item id="glbtestmodel" src="@0"></a-asset-item>
  </a-assets>

  <a-entity id="glbtest" gltf-model="#glbtestmodel" position="0 1 -2"></a-entity>
</a-scene>
```
@end

@AFRAME.scene: @AFRAME.sceneWithStyle(`width:100%; height:500px; border: 0px`,```@0```)

@AFRAME.modelWithStyle
``` html @AFRAME.sceneWithStyle(@0)
<a-scene>
  <a-assets>
    <a-asset-item id="glbtestmodel" src="@1"></a-asset-item>
  </a-assets>

  <a-entity id="glbtest" gltf-model="#glbtestmodel" position="0 1 -2"></a-entity>
</a-scene>
```
@end

@AFRAME.sceneWithStyle
<lia-keep>
<iframe style="@0" srcdoc='<!DOCTYPE html>
<html>
  <head>
    <script src="https://aframe.io/releases/1.2.0/aframe.min.js"></script>
    <script src="https://unpkg.com/aframe-extras@3.3.0/dist/aframe-extras.min.js"></script>
  </head>
  <body>
  @1
  </body>
</html>'></iframe>
</lia-keep>
@end


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
script: https://cdn.jsdelivr.net/npm/aframe@1.0.4/dist/aframe-master.min.js
```

                           {{1}}
https://raw.githubusercontent.com/liaTemplates/aframe/master/README.md

## `@AFRAME.scene`

```html @AFRAME.scene
<a-scene>
  <a-box position="-1 0.5 -3" rotation="0 45 0" color="#4CC3D9"></a-box>
  <a-sphere position="0 1.25 -5" radius="1.25" color="#EF2D5E"></a-sphere>
  <a-cylinder position="1 0.75 -3" radius="0.5" height="1.5" color="#FFC65D"></a-cylinder>
  <a-plane position="0 0 -4" rotation="-90 0 0" width="4" height="4" color="#7BC8A4"></a-plane>
  <a-sky color="#ECECEC"></a-sky>
</a-scene>
```

## 360° Image

```html @AFRAME.scene
<a-scene>
  <a-sky src="https://raw.githubusercontent.com/aframevr/aframe/v0.9.0/examples/boilerplate/panorama/puydesancy.jpg" rotation="0 -130 0"></a-sky>

  <a-text font="kelsonsans" value="Puy de Sancy, France" width="6" position="-2.5 0.25 -1.5"
  rotation="0 15 0"></a-text>
</a-scene>
```

## `@AFRAME.model`

@[AFRAME.model](model/Stein_texture.glb "this is simply a model of a stonde")
