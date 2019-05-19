## Resetting A Scene

Once a game ends, we should allow players to restart and try again! Phaser has a convenient method to solve this issue: this.scene.restart().

Like the method’s name implies, this.scene.restart(), restarts the Scene.

We should also consider when we want to restart the scene, each game has different criteria. For our game, we want this option to be available after the player sprite has collided with a bug. We should also give our players an option to restart when they choose to.

One way to implement this logic is to add on to the callback function of the player and bugs Collider object. We’ll add an event listener for a mouse click, or 'pointerup' event. When this event occurs, then we’ll restart the Scene. Let’s add this feature in.
## Instructions


In the callback function of the gameState.player and bugs Collider, add an event listener by calling this.input.on() with the arguments (in the following order):

    - 'pointerup'
    - an empty arrow callback function.

We’ll add to the callback function in the later steps.

Inside the function body of the anonymous callback, let’s reassign gameState.score to 0 for the next playthrough.

Under the reassignment of gameState.score, call this.scene.restart()

After you pass this checkpoint and play Bug Dodger, you’ll be able to restart the game after the game’s over!

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

  this.physics.add.collider(gameState.player, platforms);
  
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
  });
  
  this.physics.add.collider(gameState.player, bugs, () => {
    bugGenLoop.destroy();
    this.physics.pause();
    this.add.text(180, 250, 'Game Over', { fontSize: '15px', fill: '#000000' });
    this.add.text(152, 270, 'Click to Restart', { fontSize: '15px', fill: '#000000' });
    
		// Add your code below:
		this.input.on('pointerup', ()=>{
      gameState.score = 0;
      this.scene.restart();
    });
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
