# MarvinJ For Angular and Ionic
This is a fork from MarvinJ Framework with minimal adpaptation for use in Angular and Ionic projects. MarvinJ is a pure javascript image processing framework derived from Marvin Framework. You can check all features on the official MarvinJ project [http://marvinj.org/en/index.html]

MarvinJ was created to be the Javascript version of Marvin Image Processing Framework aiming to provide the same features in the web, server and mobile platforms powered by Javascript.

If you are not familiar with Marvin Framework and want to play with MarvinJ, don't worry. The rest of this article shows the basic image processing features of MarvinJ using JSFiddle snippets that you can make your own version and play with it.

### Requirements
Angular >= 12 

### Install
npm install marvinj-angular

### Working with MarvinJ Image Processor
In the case of MarvinJ we load images from URLs and usually use a HTML5 canvas for displaying processed images.

```

import { Marvin, MarvinImage } from "marvinj-angular";

...

strUrlImage = "https://marvinj.org/images/example2.jpg";
const objImg = new Image();
const objCanvas: HTMLCanvasElement = document.createElement("canvas");
const MarvinImage = new MarvinImage();
var image;

imgProcessor.load(strUrlImage, function () {
  
   image = this.clone();

   // Redimensioning proportionally with a scale filter
   Marvin.scale(this, image, 200);

   // Converting with a halftone filter (see more in http://marvinj.org/en/algorithms.html )
   Marvin.halftoneErrorDiffusion(image, image);

   objCanvas.width = image.width;
   objCanvas.height = image.height;
   image.draw(objCanvas);
   objImg.src = objCanvas.toDataURL();
});

```
Continue Reading:

### Know more about others image processor algorithms
[http://marvinj.org/en/algorithms.html]

### "Playing with image processing in Javascript using MarvinJ 1.0 (JSFiddle Examples)"
http://marvinj.org/en/releases/marvinj_1.0.html

