## Implementing Physics

In the previous exercise, we saw our sprite carried away by our game’s gravity. The reason we were able to implement gravity was through the use of a physics plugin which decide how GameObjects interact with each other. The plugin we’re going to use is Phaser’s Arcade physics plugin — this plugin is great for adding gravity to our game and detecting collisions.

To add the Arcade physics plugin to our config object, we need to add a physics property and provide additional specifications in its value:
```js
const config = {
  // ...
  physics: {
    default: 'arcade',
    arcade: {
      gravity: { y: 300 },
      debug: true
    }
  }
};
```
Notice that in the value of our physics property, our object has two keys, default and arcade.

    * default has a value of 'arcade' which tells Phaser to use the Arcade physics plugin.
    * arcade is another object that contains details about how we want the Arcade physics to work. The arcade object has two keys:
     * gravity which is set to { y: 300 } to assign a downward gravity. (The value 300 is based on personal preference, the higher the number, the stronger the effect of gravity is)
     * debug with a value of true to see the outline of objects in our game and their velocity.

When we call this.physics.add.sprite(), we’re actually telling Phaser’s physics plugin to create our sprite for us and have this sprite follow the physics the game.

## Instructions

In the config object, add a new property that has a key of physics and a value of an empty object.

Populate the physics object with the following key-value pairs:

    * a default key with a value of 'arcade'.
    * an arcade key with a value of an object.

Inside arcade‘s object, add the following key-value pairs:

    * gravity with a value of { y: 300 }.
    * debug with a value of true.

Now that we have physics in our game, we can uncomment the following line in the create():
```js
// this.physics.add.sprite(150, 100, 'player');
```
Run your code after you uncomment the line and see your player sprite fall again, but this time we also see a green line that indicates its directional velocity and a purple box that shows the object’s outline!

## My Code
```js
function preload() {
  this.load.image('bug1', 'https://s3.amazonaws.com/codecademy-content/courses/learn-phaser/physics/bug_1.png');
  this.load.image('bug2', 'https://s3.amazonaws.com/codecademy-content/courses/learn-phaser/physics/bug_2.png');
  this.load.image('bug3', 'https://s3.amazonaws.com/codecademy-content/courses/learn-phaser/physics/bug_3.png');
  this.load.image('platform', 'https://s3.amazonaws.com/codecademy-content/courses/learn-phaser/physics/platform.png');
  this.load.image('codey', 'https://s3.amazonaws.com/codecademy-content/courses/learn-phaser/physics/codey.png');
}

function create() {
	this.physics.add.sprite(150, 100, 'codey');
}

function update() {
}

const config = {
  type: Phaser.AUTO,
  width: 450,
  height: 500,
  backgroundColor: "b9eaff",
  physics: {
    default: 'arcade',
    arcade: {
      gravity: { y: 300 },
      debug: true,   
    }, 
  },
  scene: {
    preload,
    create,
    update
  },
  // Add the physics property below: 
  
};

const game = new Phaser.Game(config);

```
