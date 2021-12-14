<!--
author:   André Dietrich

email:    LiaScript@web.de

version:  0.0.5

language: en

narrator: US English Female

logo:     demo.gif

comment:  Template for using A-Frame in LiaScript for creating simple 3D scenes
          and add augmented reality movies and images.


@AFRAME.style: width:100%; height:500px; border: 0px

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

@AFRAME.image
``` html @AFRAME.scene
<a-scene>
  <a-sky src="@0" rotation="0 -130 0"></a-sky>
</a-scene>
```
@end

@AFRAME.imageWithStyle
``` html @AFRAME.sceneWithStyle(@0)
<a-scene>
  <a-sky src="@1" rotation="0 -130 0"></a-sky>
</a-scene>
```
@end

@AFRAME.scene: @AFRAME.sceneWithStyle(@AFRAME.style,```@0```)

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

# AFrame - Template

                         --{{0}}--
This library implements some macros for [AFrame](https://aframe.io), which allow
to load 3D scenes, models or videos into [LiaScript](https://LiaScript.github.io)

__Try it on LiaScript:__

https://liascript.github.io/course/?https://raw.githubusercontent.com/LiaTemplates/aframe/0.0.5/README.md

__See the project on Github:__

https://github.com/liaTemplates/aframe

                         --{{1}}--
There are three ways to use this template. The easiest way is to use the
`import` statement and the URL of the raw text-file of this course or any other
branch or version. But you can also copy the required functionionality directly
into the header of your Markdown document, see therefor the Implementation. And
of course, you could also clone this project and change it, as you wish.

     {{1}}
1. Load the macros via

   `import: https://raw.githubusercontent.com/LiaTemplates/aframe/0.0.5/README.md`

2. Copy the definitions into your Project

3. Clone this repository on GitHub

## Macros

### `@AFRAME.scene`

    --{{0}}--
The most basic macro is `@AFRAME.scene`. Add this to thead of your Markdown
code-block in order to indicate to LiaScript, that this code-snippet should be
interpreted as an entire scene and rendered approrpiately.

```` markdown
```html @AFRAME.scene
<a-scene>
  <a-box position="-1 0.5 -3" rotation="0 45 0" color="#4CC3D9"></a-box>
  <a-sphere position="0 1.25 -5" radius="1.25" color="#EF2D5E"></a-sphere>
  <a-cylinder position="1 0.75 -3" radius="0.5" height="1.5" color="#FFC65D"></a-cylinder>
  <a-plane position="0 0 -4" rotation="-90 0 0" width="4" height="4" color="#7BC8A4"></a-plane>
  <a-sky color="#ECECEC"></a-sky>
</a-scene>
```
````

**Result:**

```html @AFRAME.scene
<a-scene>
  <a-box position="-1 0.5 -3" rotation="0 45 0" color="#4CC3D9"></a-box>
  <a-sphere position="0 1.25 -5" radius="1.25" color="#EF2D5E"></a-sphere>
  <a-cylinder position="1 0.75 -3" radius="0.5" height="1.5" color="#FFC65D"></a-cylinder>
  <a-plane position="0 0 -4" rotation="-90 0 0" width="4" height="4" color="#7BC8A4"></a-plane>
  <a-sky color="#ECECEC"></a-sky>
</a-scene>
```

### `@AFRAME.sceneWithStyle`

    --{{0}}--
However, the previous example used the default styling method, which is defined
by the macro `@AFRAME.style`. By using this macro, it is possible to overwrite
these settings, change the widht and height properties or to add a border. Note,
the backticks around the style-definition are optional, as long as there is no
comma within your definition, this will work. But if you have commas within
your parameters, LiaScript will separate them by commas, to prevent this use
backticks.

```` markdown
```html @AFRAME.sceneWithStyle(`width: 100%; height: 70vh`)
<a-scene>
  <a-sky src="https://raw.githubusercontent.com/aframevr/aframe/v0.9.0/examples/boilerplate/panorama/puydesancy.jpg" rotation="0 -130 0"></a-sky>

  <a-text font="kelsonsans" value="Puy de Sancy, France" width="6" position="-2.5 0.25 -1.5"
  rotation="0 15 0"></a-text>
</a-scene>
```
````

```html @AFRAME.sceneWithStyle(width: 100%; height: 55vh)
<a-scene>
  <a-sky src="https://raw.githubusercontent.com/aframevr/aframe/v0.9.0/examples/boilerplate/panorama/puydesancy.jpg" rotation="0 -130 0"></a-sky>

  <a-text font="kelsonsans" value="Puy de Sancy, France" width="6" position="-2.5 0.25 -1.5"
  rotation="0 15 0"></a-text>
</a-scene>
```

### `@AFRAME.model`

     --{{0}}--
Somethimes it might be convenient to load only a model, for this purpose you can
make use of a reference-macro. All the last two macro-calls are identical and
would work perfectly for absolute URLs. However, if you use the first type,
which looks like a Markdown-reference, your resource will still be treated as a
link by other Markdown-interpreters. And most importantly, LiaScript knows that
the parameter you pass, is a URL, and it will handle the URL translation for
relative URLs. The title optional and a way for you, to provide some information
about the content of, but LiaScript will ignore this at the moment.

```` markdown
@[AFRAME.model](model/Stein_texture.glb "simply a model of a stone")

similar to

@AFRAME.model(model/Stein_texture.glb)

or

``` html @AFRAME.model
model/Stein_texture.glb
```
````

**Result:**

@[AFRAME.model](model/Stein_texture.glb "simply a model of a stone")


### `@AFRAME.modelWithStyle`

     --{{0}}--
Similar the the scene macros, you can also provide your own styling withi this
macro. The first parameter passed within brackets, is again the new styling
definition, whereby the URL of the model is passed as the seconde one. LiaScript
again, will handle the approrpiate URL translation of relative paths.

```
@[AFRAME.modelWithStyle(`width: 50%`)](model/Stein_texture.glb "a model of a stone")
```

**Result:**

@[AFRAME.modelWithStyle(`width: 50%`)](model/Stein_texture.glb "a model of a stone")


### `@AFRAME.image`

This macro will load an image as a 360 degree image and display it.

``` markdown
@[AFRAME.image](model/puydesancy.jpg "360 Degree image of Puy de Sancy, France")
```

**Result:**

@[AFRAME.image](model/puydesancy.jpg "360 Degree image of Puy de Sancy, France")

### `@AFRAME.imageWithStyle`

    --{{0}}--
Similar to all previous elements, load a 360 Degree image with custom styling.

``` markdown
@[AFRAME.imageWithStyle(width: 350px; height: 350px)](model/puydesancy.jpg)
```

**Result:**

@[AFRAME.imageWithStyle(width: 350px; height: 350px)](model/puydesancy.jpg)

### `@AFRAME.style`
<!--
@AFRAME.style: width:100%; height:60vh; border: 3px dashed red;
-->

    --{{0}}--
The basic `@AFRAME.style` macro defines the default styling properties, which
are used as long as you do not use a `macroWithStyle`. You can still overwrite
this macro and define your own default style, such that it is not required to
come up with the custom styling again, again, and agian.

```` markdown
<!--
import: https://raw.githubusercontent.com/liaTemplates/aframe/master/README.md

@AFRAME.style: width:100%; height:60vh; border: 3px dashed red;
-->

# Title

...

## Section
<!--
@AFRAME.style: width:100%; height:60vh; border: 3px dashed red;
-->
````

    --{{1}}--
This can be done either globally, within the main definitions or per slide,
simply by adding an HTML macro directly to the title of the section.


    {{1}}
@[AFRAME.model](model/Stein_texture.glb "simply a model of a stone")

### Define your own
<!--
@custom_sphere
``` html @AFRAME.scene
<a-scene>
  <a-sphere position="0 1.25 -5" radius="@0" color="#EF2D5E"></a-sphere>
  <a-plane position="0 0 -4" rotation="-90 0 0" width="4" height="4" color="#7BC8A4"></a-plane>
  <a-sky color="#ECECEC"></a-sky>
</a-scene>
```
@end
-->

    --{{0}}--
Of course, it is also possible to define other custom macros, which are based on
the macro set, that you have loaded. The example below shows, how a new macro
`@custom_sphere` is defined. Everything within the body, which ranges from
`@custom_sphere` to `@end` will be injected, whereever it appears within the
document. The only thing that is parameterized here, is the radius of the
sphere. The position of the internal parameters is marked via `@0` to `@9`.
These markers will be replaced by the the user defined parameters, before
injection.


```` markdown
### Define your own
<!--
@custom_sphere
``` html @AFRAME.scene
<a-scene>
  <a-sphere position="0 1.25 -5" radius="@0" color="#EF2D5E"></a-sphere>
  <a-plane position="0 0 -4" rotation="-90 0 0" width="4" height="4" color="#7BC8A4"></a-plane>
  <a-sky color="#ECECEC"></a-sky>
</a-scene>
```
@end
-->

You can also have a look at the next slide, to see how the other macros were
defined.

@custom_sphere(1.5)

---

@custom_sphere(3.141592)
````

@custom_sphere(1.5)

---

@custom_sphere(3.141592)


## Implementation

All defined macros are basically exentsion the the most general
`@AFRAME.sceneWithStyle`. This macro only loads an `ìframe` and adds some user
defined code to the body.

```` html
@AFRAME.style: width:100%; height:500px; border: 0px

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

@AFRAME.image
``` html @AFRAME.scene
<a-scene>
  <a-sky src="@0" rotation="0 -130 0"></a-sky>
</a-scene>
```
@end

@AFRAME.imageWithStyle
``` html @AFRAME.sceneWithStyle(@0)
<a-scene>
  <a-sky src="@1" rotation="0 -130 0"></a-sky>
</a-scene>
```
@end


@AFRAME.scene: @AFRAME.sceneWithStyle(@AFRAME.style,```@0```)

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
````
