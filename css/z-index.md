#z-index

Today, I spent hours trying to get a Boostrap panel to sit on top of a Google map. Part of the issue had to do with too many container classes in my application layout, but even after I got that straightened out, I was struggling to get the panel to float on top of, and not beneath, the map canvas.

Turns out the trick is a little CSS element called z-index, which can be used to stack elements on the page. By adding a negative value to the z-index of my map canvas, I was able to push it down and float the panel over it.

```#map-canvas {
  height: 700px;
  width: 100%;
  margin-bottom: 20px;
  max-width: none;
  z-index: -1;
}```

 I'm pretty sure there is a lot more to z-index than what I learned today, so here's an article for a rainy day. [What You May Not Know About the Z-Index Property](http://webdesign.tutsplus.com/articles/what-you-may-not-know-about-the-z-index-property--webdesign-16892).