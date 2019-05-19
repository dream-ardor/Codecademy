## Adding a score

One thing we’re still missing from our game is a scoring system to motivate our players. We can store our score as property in the gameState object and increase it as the game progresses. To display the score we can call this.add.text(). We should also consider when we want to increase the score, e.g. increase the score every 10 seconds, or each time an enemy is generated, or how much the player sprite moves, etc…

For our game, we could increase the score each time the player sprite dodges a bug. When a player dodges a bug, it collides with the platform, so we can add our logic in that Collider object. Let’s do that now!

When a game starts we should set a new property with a key of score and value of 0 in the gameState object like so:
```js
const gameState = { score: 0 };
```
We’ll also need gameState to display the score on screen. In create() we would add:
```js
gameState.scoreText = this.add.text(16, 16, 'Score: 0', { fontSize: '15px', fill: '#000000' })
```
Now we can access gameState.scoreText and change the text to display the increased score. Since we want to increment gameState.score when a bug collides with the ground platform, we need to add that logic to our ColliderObject:
```js
this.physics.add.collider(bugs, platforms, function (bug){
  bug.destroy();

  gameState.score += 10;
  gameState.scoreText.setText(`Score: ${gameState.score}`)
})
```
Let’s incorporate this into our game!
## Instructions

Locate the gameState object and add a score key with a 0 value. You’ll use this property to keep track of the game’s score.

In create(), inside the callback of the bugs and platforms Collider object, increase gameState.score by 10 every time a bug collides with the ground platform.

Notice that at the center of the platform there is a displayed score! That’s because in create(), we added gameState.scoreText. And it is assigned this.add.text(16, 16, 'Score: 0', { fontSize: '15px', fill: '#000000' }). Since that the score is going to change, you need to change gameState.scoreText.

Call .setText(`Score: ${gameState.score}`) on gameState.scoreText.

Once you pass this checkpoint and play the game, you’ll see the updated score displayed on screen!

```js
function preload() {
  this.load.image('bug1', 'https://s3.amazonaws.com/codecademy-content/courses/learn-phaser/physics/bug_1.png')
  this.load.image('bug2', 'https://s3.amazonaws.com/codecademy-content/courses/learn-phaser/physics/bug_2.png')
  this.load.image('bug3', 'https://s3.amazonaws.com/codecademy-content/courses/learn-phaser/physics/bug_3.png')
  this.load.image('platform', 'https://s3.amazonaws.com/codecademy-content/courses/learn-phaser/physics/platform.png')
  this.load.image('codey', 'https://s3.amazonaws.com/codecademy-content/courses/learn-phaser/physics/codey.png')
}

const gameState = {
  // Add the score property below: 
  score: 0
};

function create() {
  gameState.player = this.physics.add.sprite(225, 450, 'codey').setScale(.5);
  
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
    delay: 100,
    callback: bugGen,
    callbackScope: this,
    loop: true,
  });
  
  // Displays initial Score: 0 text
  gameState.scoreText = this.add.text(195, 485, 'Score: 0', { fontSize: '15px', fill: '#000000' });

  this.physics.add.collider(bugs, platforms, function (bug) {
    bug.destroy();
	  // Add your code below:
    gameState.score += 10;
    gameState.scoreText.setText(`Score: ${gameState.score}`);
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
}

const game = new Phaser.Game(config)

```
