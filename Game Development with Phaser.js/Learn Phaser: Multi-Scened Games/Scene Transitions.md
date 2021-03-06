## Scene Transitions

Phaser has built-in methods that make it easy for us to transition from one Scene to another. For us to transition between Scenes we have to .stop() the playing of a Scene and .start() the next Scene.

To stop a Scene, call this.scene.stop('keyOfScene').

Then, to start a Scene, call this.scene.start('keyOfAnotherScene').

The .stop() and .start() methods take in a string that has the value of a Scene’s key. Like the name of the methods imply, .stop() will stop the Scene and start() will start playing the Scene.

Let’s see this in action!

## Instructions

For our game, we want to start the next scene after a player clicks on the game screen.

In the StartScene class, there is an event handler in create() for 'pointerup' events. Inside the callback of the event handler, call this.scene.stop('StartScene').

Still inside the callback function, call this.scene.start('GameScene').

With this functionality in, players can click anyone on the start screen and transition to playing the game!

## My Code
```js
const gameState = {
	score: 0
};

class StartScene extends Phaser.Scene {
	constructor(){
		super({ key: 'StartScene' });
	}
  
  create() {
    this.add.text(95, 250, 'Click to Start!', { fontSize: '30px', fill: '#000000' });
    
    this.input.on('pointerup', () => {
      // Add your code below:
      this.scene.stop('StartScene');
      this.scene.start('GameScene');
    });
  }
}

class GameScene extends Phaser.Scene {
	constructor(){
		super({ key: 'GameScene' });
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

		this.physics.add.collider(bugs, platforms, bug => {
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
	scene: [StartScene, GameScene]
};

const game = new Phaser.Game(config);


```
