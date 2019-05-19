## Removing Enemies

Our enemy sprites threaten to take over our game if we don’t remove them! We’re going to need to use Phaser’s .destroy() method to remove enemy sprites from our game.

Let’s first take a second to consider when we want our enemies removed. For our game, bugs should disappear when they hit the ground. Therefore, we need a Collider for enemies and platforms. Unlike the one we previously created, this Collider takes a third argument of a callback function.
```js
function create() {
  // … 
  this.physics.add.collider(enemies, platforms, function(singleEnemy) {
    singleEnemy.destroy();
  });
}
```
In our example, we called this.physics.add.collider() with three arguments:

    * The first two arguments are Group objects, enemies and platforms.
    * The third argument is a callback function that has a parameter, singleEnemy:
        - The ordering of the callback function’s parameter corresponds to the ordering of .collider()‘s first two arguments.
        - We call singleEnemy.destroy() which will remove the enemy’s sprite when it collides with a platform.

Let’s use this logic to remove bug sprites as they hit the ground.

## Instructions

Inside create(), call this.physics.add.collider() with the arguments bugs and platforms (in that order!) to create a Collider object to detect collisions between bugs and platforms.

Add a third argument inside .collider(), pass an anonymous function that has one parameter, bug.

Inside the callback function, call bug.destroy().

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
  
  const bugGenLoop = this.time.addEvent({
    delay: 150,
    callback: bugGen,
    callbackScope: this,
    loop: true
  });
  
  // Add your code below:
  this.physics.add.collider(bugs, platforms,function(bug){
    bug.destroy();
    
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
