## Adding Enemies

At this point, we have a controllable player sprite, a platform, and a collider set up. Let’s make some enemies!

Unlike the player sprite, we probably want multiple enemies to triumph over. And unlike the platform, we should have physics affect them. Once again, Phaser has a handy method for us, this.physics.add.group() which returns a Group object that we can use to organize multiple enemy sprites. For instance:
```js
function create() {
  const enemies = this.physics.add.group();
  enemies.create(320, 10, 'enemy');  
} 
```
From the example above we called this.physics.add.group() and assigned it to a variable, enemies. Then we call enemies.create(320, 10, 'enemy') to create one sprite centered at the coordinates (320, 10) using the 'enemy' key.

But with our current code, we know that our enemy will always appear at the coordinates (320, 10). That’s not much of challenge. Instead, we can randomize where this enemy’s x-coordinate using Math.random() and multiply that value by the width of the screen. The logic being:

    * Math.random() returns a value from 0 to 1, e.g. 0.12418156798374347.
    * When we multiply the value from Math.random() with the width of the screen (in pixels), we get a value that is between from 0 (left-hand side) to the width of the game(right-hand side).
    * The product is a random x-coordinate that is always on the screen.

Our updated code:
```js
function create() {
  const enemies = this.physics.add.group();
  const xCoordinate = Math.random() * 450;
  enemies.create(xCoordinate, 10, 'enemy');  
} 
```
Since we want to create multiple enemy sprites, we can use a function to house the logic for enemy creation:
```js
function create() {
  const enemies = this.physics.add.group();
  function generateEnemy () {
    const xCoordinate = Math.random() * 450;
    enemies.create(xCoordinate, 10, 'enemy');  
  }
} 
```
With our updated code, we can create an enemy sprite every time we call generateEnemy(). Let’s bring this logic into our game!

## Instructions

Let’s first create an enemy using this.physics.add.group() and assign it to a variable bugs.

Inside create, define an empty bugGen() function that will house the logic for creating enemies.

Inside the function body of bugGen(), create a variable xCoord and assign to it Math.random() * 450.

After defining xCoord, call bugs.create(xCoord, 10, 'bug1').

Test out bugGen()! Inside create(), call bugGen() to see a bug appear on screen. Notice that the bug sprite is affected by gravity!

You can call the function many times to create multiple bugs.

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

	gameState.player.setCollideWorldBounds(true);
  
  this.physics.add.collider(gameState.player, platforms);
 
  gameState.cursors = this.input.keyboard.createCursorKeys();
  
  // Add your code below:
  const bugs = this.physics.add.group();
  function bugGen(){
    const xCoord = Math.random() * 450;
    bugs.create(xCoord, 10, 'bug1');
    
  }
  bugGen();
}

function update() {
  if (gameState.cursors.left.isDown) {
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
