## New Scenes

Since we’re now using the class syntax in our Phaser game, we can add another class that will render a start screen for our players. This start screen will give our players a chance to ready themselves before actually playing the game.

Recall the template for creating a Scene:
```js
class FirstScene extends Phaser.Scene {
  constructor(){
    super({ key: 'FirstScene' });
  }
  // ...
}
```
Notice we supplied super() with the key of 'FirstScene'. We’ll then reference this key in our config:
```js
const config = {
  // …
  scene: [FirstScene, AnotherScene]
};
```
This time around, we have two elements inside scene‘s array. The ordering is important in determining which Scene the game plays first. For the example above, the game will play FirstScene and not play AnotherScene until prompted.

Let’s add a simple start screen to our game!

## Instructions

Add a class named StartScene that extends Phaser.Scene.

Inside the class you just created, add a constructor() method.

Inside the constructor() method, call super() with the argument: { key: 'StartScene' }.

Let’s keep our start screen simple, add a create() method to the StartScene class.

Inside create() call this.add.text( x, y, textArg):

* replace x and y with numbers for the x- and y-coordinates respectively.
* replace textArg with a string to tell players to start the game.
* In our next exercise, we’ll go over how to transition from one Scene to another.

Locate config and its scene property.

Inside the scene array, add StartScene to the start of the array BEFORE GameScene.

Notice how the ordering of the Scenes in the scene property affects which Scene plays first.

## My Code
```js
const gameState = {
	score: 0
};

// Add your code below:
class StartScene extends Phaser.Scene {
  constructor(){
    super( {key: 'StartScene' })
  }
  create() {
    this.add.text(200,200,'Start the Game!')
  }
}

class GameScene extends Phaser.Scene {
	constructor(){
		super({ key: 'GameScene' })
	}

	preload() {
		this.load.image('bug1', 'https://s3.amazonaws.com/codecademy-content/courses/learn-phaser/physics/bug_1.png');
		this.load.image('bug2', 'https://s3.amazonaws.com/codecademy-content/courses/learn-phaser/physics/bug_2.png');
		this.load.image('bug3', 'https://s3.amazonaws.com/codecademy-content/courses/learn-phaser/physics/bug_3.png');
		this.load.image('platform', 'https://s3.amazonaws.com/codecademy-content/courses/learn-phaser/physics/platform.png');
		this.load.image('codey', 'https://s3.amazonaws.com/codecademy-content/courses/learn-phaser/physics/codey.png');
	}


	create() {
		gameState.player = this.physics.add.sprite(225, 450, 'codey').setScale(.5);

		const platforms = this.physics.add.staticGroup();

		platforms.create(225, 490, 'platform').setScale(1, .3).refreshBody();

		gameState.scoreText = this.add.text(195, 485, 'Score: 0', { fontSize: '15px', fill: '#000000' });

		gameState.player.setCollideWorldBounds(true);

		this.physics.add.collider(gameState.player, platforms);

		gameState.cursors = this.input.keyboard.createCursorKeys();

		const bugs = this.physics.add.group();

		const bugGen = () => {
			const xCoord = Math.random() * 640
			bugs.create(xCoord, 10, 'bug1')
		}

		const bugGenLoop = this.time.addEvent({
			delay: 100,
			callback: bugGen,
			callbackScope: this,
			loop: true,
		});

		this.physics.add.collider(bugs, platforms,  bug => {
			bug.destroy();
			gameState.score += 10;
			gameState.scoreText.setText(`Score: ${gameState.score}`);
		})

		this.physics.add.collider(gameState.player, bugs, () => {
			bugGenLoop.destroy();
			this.physics.pause();
			this.add.text(180, 250, 'Game Over', { fontSize: '15px', fill: '#000000' });
			this.add.text(152, 270, 'Click to Restart', { fontSize: '15px', fill: '#000000' });

			this.input.on('pointerup', () => {
				gameState.score = 0;
				this.scene.restart();
			});
		});
	}

	update() {
		if (gameState.cursors.left.isDown) {
			gameState.player.setVelocityX(-160);
		} else if (gameState.cursors.right.isDown) {
			gameState.player.setVelocityX(160);
		} else {
			gameState.player.setVelocityX(0);
		}
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
	scene: [StartScene,GameScene]
};

const game = new Phaser.Game(config);

```
