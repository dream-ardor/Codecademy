## Timed Events

Currently, our game creates a few enemy sprites and stops. But we could create a loop to consistently create more enemies to make the game more challenging. To implement this loop we can call this.time.addEvent() and pass in an object with specifications for how we want this loop to run. For instance:
```js
function create() {
  function generateEnemy () { 
    // Code to create an enemy sprite
  }
  const enemyGenLoop = this.time.addEvent({
    callback: generateEnemy,
    delay: 100,
    callbackScope: this,
    loop: true,
  })
} 
```
In our example, we accessed the Scene’s time property and called .addEvent() with an object representing the event we want called. That object has 4 keys that each provide different specifications:

    * callback has a value of generateEnemy which means this event will call generateEnemy() function.
    * delay has a value of 100, which determines, in milliseconds, how long is the delay before executing the callback again.
    * callbackScope has a value of this, which selects the Scene this event is used in.
    * loop has a value of true, which means that this event will continue to execute until we remove it.

For more information about timed events, look over RexRainbow’s comprehensive Phaser documentation!

## Instructions

In create(), in a line under bugGen(), call this.time.addEvent() and assign it to a variable bugGenLoop.

We’ll provide .addEvent() with an argument in the next step.

Pass into .addEvent() an object with the following properties:
```js
delay: 150,
callback: bugGen,
callbackScope: this,
loop: true
```
After you pass this checkpoint, watch the bugs rain from the sky!

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
  
  const bugs = this.physics.add.group();
  
	function bugGen () {
    const xCoord = Math.random() * 450;
    bugs.create(xCoord, 10, 'bug1');
  }
  
  // Add your code below:
  const bugGenLoop = this.time.addEvent({
    delay: 150,
    callback: bugGen,
    callbackScope: this,
    loop: true
  });
 
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
