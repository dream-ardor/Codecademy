## Detecting Collisions

We have a platform sprite, we have a player sprite, but they’re not interacting with each other! What’s missing? Remember, our physics plugin determines how GameObjects interact. The way to decide these interactions is to create a Collider object that checks if two GameObjects bump into each other.

To set a Collider object we need to call this.physics.add.collider(). The .collider() method takes three arguments (the last one argument is optional). The first two arguments are the GameObjects (or Group objects) that collide. Here’s an example of a collider with two arguments:
```js
function create() {
  const player = this.physics.add.sprite(100, 100, 'player');
  const platform = this.physics.add.sprite(100, 500, 'platform');
  this.physics.add.collider(player, platform);
}
```
In the example above, we created a Collider object by calling this.physics.add.collider(player, platform). Now, the player and platform objects don’t overlap when they bump into each other.

While we’re on the topic of collisions, we can call the .setCollideWorldBounds(true) for GameObjects that we want to stay inside the screen of the game. For example, calling player.setCollideWorldBounds(true) will make it so the player sprite can’t fall off the screen!

## Instructions

Let’s keep Codey from going off the screen!

In create(), call gameState.player.setCollideWorldBounds(true).

Now let’s create a collider between Codey and the ground platform.

Call this.physics.add.collider() with the following arguments:

    - gameState.player
    - platforms

After you clear this checkpoint you should see Codey land directly on the platform!

## My Code
```js
function preload() {
  this.load.image('bug1', 'https://s3.amazonaws.com/codecademy-content/courses/learn-phaser/physics/bug_1.png');
  this.load.image('bug2', 'https://s3.amazonaws.com/codecademy-content/courses/learn-phaser/physics/bug_2.png');
  this.load.image('bug3', 'https://s3.amazonaws.com/codecademy-content/courses/learn-phaser/physics/bug_3.png');
  this.load.image('platform', 'https://s3.amazonaws.com/codecademy-content/courses/learn-phaser/physics/platform.png');
  this.load.image('codey', 'https://s3.amazonaws.com/codecademy-content/courses/learn-phaser/physics/codey.png');
}

const gameState = {};

function create() {
  gameState.player = this.physics.add.sprite(225, 440, 'codey').setScale(.5);
  
  const platforms = this.physics.add.staticGroup();

  platforms.create(225, 510, 'platform');

  // Add your code below:
  gameState.player.setCollideWorldBounds(true);
  this.physics.add.collider(gameState.player, platforms);
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
      gravity: { y: 200 },
      enableBody: true,
    }
  },
  scene: {
    preload,
    create,
    update
  }
};

const game = new Phaser.Game(config);

```
