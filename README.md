# bxue0412_9103_tut8
This is my Creative Coding Week 8 quiz response.

## Part 1: Imaging Technique Inspiration

This inspiration is a scene from the 2007 film *Ratatouille*. In this scene, the characters eat a piece of cheese and strawberry. The audio and abstract animation visualise how they feel while eating the food. 

[Here is a link to the scene.](https://www.youtube.com/watch?v=rLXYILcRoPQ)

The technique that I find inspiring is **the way that the shapes change in response to the audio.** The animator used a combination of circles, curves, lines, and other shapes to show the character’s mood. This will be helpful to my assignment because it demonstrates how shapes, colour, and audio can be combined to create an engaging and beautiful animation. 

Some screenshots of the scene:
![Screenshot of the scene](readMeImages/Ratatouille1.jpg)
![Another screenshot](readMeImages/Ratatouille2.jpg)

Concept art by animator Michel Gagné. 
He posted his process of creating the scene [here](https://www.gagneint.com/Final%20site/Animation/Pixar/Ratatouille.htm).
![Another screenshot](https://www.gagneint.com/Final%20site/Animation/Pixar/Gagne_fx_designs_130/130_FX_09.jpg)

## Part 1: Coding Technique Exploration
The technique of moving an object along a curve can be used to implement the imaging technique. This technique will make a shape, such as a circle, move along a certain path. In the video, the shapes appeared and moved in a seemingly random way. This coding technique will make any shape move in response to certain stimuli, such as a button being pressed. 

This technique was found in the p5js.org examples website. In this example, a circle is moved in response to a mouse being pressed. 

[Link to p5.js example with code.](https://p5js.org/examples/motion-moving-on-curves.html)

Screenshot of the object moving example found on the website.
![Screenshot](readMeImages/codingTechnique.png)

Code from the example:
```
let beginX = 20.0; // Initial x-coordinate
let beginY = 10.0; // Initial y-coordinate
let endX = 570.0; // Final x-coordinate
let endY = 320.0; // Final y-coordinate
let distX; // X-axis distance to move
let distY; // Y-axis distance to move
let exponent = 4; // Determines the curve
let x = 0.0; // Current x-coordinate
let y = 0.0; // Current y-coordinate
let step = 0.01; // Size of each step along the path
let pct = 0.0; // Percentage traveled (0.0 to 1.0)

function setup() {
  createCanvas(720, 400);
  noStroke();
  distX = endX - beginX;
  distY = endY - beginY;
}

function draw() {
  fill(0, 2);
  rect(0, 0, width, height);
  pct += step;
  if (pct < 1.0) {
    x = beginX + pct * distX;
    y = beginY + pow(pct, exponent) * distY;
  }
  fill(255);
  ellipse(x, y, 20, 20);
}

function mousePressed() {
  pct = 0.0;
  beginX = x;
  beginY = y;
  endX = mouseX;
  endY = mouseY;
  distX = endX - beginX;
  distY = endY - beginY;
}
```