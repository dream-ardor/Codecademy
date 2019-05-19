## Losing Condition

It’s great to see our score increase, but it doesn’t mean much if there’s no way to lose. One common losing condition is when a player sprite collides with an enemy sprite. This means we need to include another Collider object with a callback in create():
```js
this.physics.add.collider(player, enemies, () => {
  // Logic to end the game
});
```
For our game, it ends when the player sprite a bug collide. When this event happens we also want certain things to stop. For instance, we don’t want our game to continue creating bugs. We could call .destroy() on the loop that creates our bugs. Another thing we would want to stop is the physics of our game. To put a pause on physics, we call this.physics.pause().

In the code example above, notice the use of an arrow function (() => {}) for a callback instead of anonymous function (function() {}). The reason for using an arrow function is that it implicitly binds this. We know that we want to call this.physics.pause() and we need this to reference the Scene object. Therefore, we use an arrow function to bind this as the Scene object. To read more about arrow functions and this, check out MDN’s arrow function documentation

Let’s see how this works in our code!
## Instructions

In create(), create a Collider object using this.physics.add.collider(). The method call has the following arguments and in the following order:
```js
    gameState.player
    bugs
    an empty arrow callback function, e.g. () => {}
```

Inside the callback function, you need to call .destroy() on bugGenLoop to stop the Timer event that creates the falling bugs!

Inside the same callback function, under bugGen.destroy(), call this.physics.pause().

Lastly, still inside the callback, add the text for players to know that the game is over.

The text should:

    Be at coordinates of your choosing.
    read 'Game Over'
    have a font size of 15 pixels
    have a fill of '#000000'
    
## My Code
```js
function preload() {
  this.load.image('bug1', 'https://s3.amazonaws.com/codecademy-content/courses/learn-phaser/physics/bug_1.png')
  this.load.image('bug2', 'https://s3.amazonaws.com/codecademy-content/courses/learn-phaser/physics/bug_2.png')
  this.load.image('bug3', 'https://s3.amazonaws.com/codecademy-content/courses/learn-phaser/physics/bug_3.png')
  this.load.image('platform', 'https://s3.amazonaws.com/codecademy-content/courses/learn-phaser/physics/platform.png')
  this.load.image('codey', 'https://s3.amazonaws.com/codecademy-content/courses/learn-phaser/physics/codey.png')
}

const gameState = {
  score: 0
};

function create() {
  gameState.player = this.physics.add.sprite(225, 450, 'codey').setScale(.5);
  
  const platforms = this.physics.add.staticGroup();

  platforms.create(225, 510, 'platform');

  gameState.scoreText = this.add.text(195, 485, 'Score: 0', { fontSize: '15px', fill: '#000000' })

  gameState.player.setCollideWorldBounds(true);

  this.physics.add.collider(gameState.player, platforms)
  
  	gameState.cursors = this.input.keyboard.createCursorKeys();

  const bugs = this.physics.add.group();

  function bugGen () {
    const xCoord = Math.random() * 450;
    bugs.create(xCoord, 10, 'bug1');
  }

  const bugGenLoop = this.time.addEvent({
    delay: 100,
    callback: bugGen,
    callbackScope: this,
    loop: true,
  });

  this.physics.add.collider(bugs, platforms, function (bug) {
    bug.destroy();
    gameState.score += 10;
    gameState.scoreText.setText(`Score: ${gameState.score}`)
  })
  
  // Add your code below:
	this.physics.add.collider(gameState.player, bugs, () => {
  bugGenLoop.destroy();
  this.physics.pause();
  this.add.text(200,200, 'Game Over', { fontSize: '15px', fill: '#000000'})
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

