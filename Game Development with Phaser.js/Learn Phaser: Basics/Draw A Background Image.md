## Draw A Background Image

Now that we’ve covered drawing a sprite, let’s talk about drawing a background image. A background image is not a sprite — usually the player will not interact with the background at all. Because of this, we don’t need a sprite object for our background images. We still need to load in the image in our preload() function but we can use this.add.image() instead of this.add.sprite():
```js
function preload() {
  this.load.image('bg', 'assets/images/bg.png');
}

function create() {
  this.add.image(200, 200, 'bg');
}
```
Above, we load in our background image from the path assets/images/bg.png and use the key bg to refer to it. In create() we add the image, centered at (200, 200) — 200 pixels to the right of the left edge and 200 pixels down from the top edge.

## Instructions

In preload(), load in our Sky background image from 'https://s3.amazonaws.com/codecademy-content/courses/learn-phaser/sky.jpg' and give it the key 'sky'.

In create() add our background image by calling this.add.image() with an x value, a y value, and our key 'sky'.

Notice how the x and y values dictate the center of the image. Try giving negative values for both and see how much of the image you can see!

## My Code
```js
function preload() {
  // Load in the background image here!
this.load.image('sky','https://s3.amazonaws.com/codecademy-content/courses/learn-phaser/sky.jpg');
}


function create() {
  // Put the background image in the scene here!
this.add.image(200,200,'sky');
}


const config = {
	type: Phaser.AUTO,
	width: 450,
	height: 600,
	backgroundColor: "#5f2a55",
	scene: {
    create,
    preload
	}
}

const game = new Phaser.Game(config)
```
