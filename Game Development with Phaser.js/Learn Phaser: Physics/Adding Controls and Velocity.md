## Adding Controls and Velocity

Until we can telepathically instruct characters in games, we need physical controls to direct our player characters on how to move.

One way we can implement controls is by using Phaser’s this.input.keyboard.createCursorKeys() method to create a useful object for keyboard inputs. The created object has properties up, down, left, right, space, and shift that are directly related to the keyboard keys. We can also access the .isDown property to the key to see if it is pressed. If the key is pressed, we can change the horizontal velocity of a GameObject by using the .setVelocityX() method. For instance:
```js
function create() {
  // Previous code ...
  gameState.cursors = this.input.keyboard.createCursorKeys();
}

function update() {
  if (gameState.cursors.left.isDown) {
    heroSprite.setVelocityX(-160);
  } else if (gameState.cursors.right.isDown) {
    heroSprite.setVelocityX(160);
  } else {
    heroSprite.setVelocityX(0);
  }
}
```
In our update() function, we created the cursors object using this.input.keyboard.createCursorKeys(). Then, we added conditionals to check if the left arrow key is being pressed (cursors.left.isDown) or if the right arrow key is being pressed (cursors.right.isDown). If the left arrow key is pressed we set the horizontal velocity using setVelocityX() with an argument of -160 to move the sprite left. The opposite happens when the right arrow key is pressed, we call .setVelocityX(160) on heroSprite and it moves to the right. If neither keys are pressed, we set the velocity to zero and the sprite does not move.

## Instructions

In the create() function, create the cursor keys and assign it to gameState.cursors.

We’ll be using the gameState.cursors properties to check when the left or right arrow keys are pressed.

Look at the create() function take note of gameState.player, it is our player sprite.

In the update() function, add an if statement to check if the left arrow key is pressed. Use cursors.left.isDown which returns true if the left arrow key is down and false if it’s not.

If the condition is true, then call gameState.player.setVelocityX(-160). This way we move the player sprite to the left when the left arrow key is pressed.

Add an else if statement that checks cursors.right.isDown. And if that condition is true, then call gameState.player.setVelocityX(160). Now our sprite will move to the right when the right arrow key is pressed.

Lastly, we need to add an else condition, and if neither key is pressed, call gameState.player.setVelocityX(0).

This way, Codey will not move when neither the left or right arrow key is down.

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

	gameState.player.setCollideWorldBounds(true);
  
  this.physics.add.collider(gameState.player, platforms);
  
	// Assign gameState.cursors below: 
  gameState.cursors = this.input.keyboard.createCursorKeys();
}

function update() {
  // Add your conditional statements below:
  if(gameState.cursors.left.isDown) {
  	gameState.player.setVelocityX(-160);
	} else if (gameState.cursors.right.isDown) {
 		gameState.player.setVelocityX(160);
	} else {
    gameState.player.setVelocityX(0);
  }
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
