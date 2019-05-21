## Separate Files

Having two Scenes, a gameState object, and our config object in the same file can make our code feel cluttered. As we add more Scenes, this file will continue to grow and it can become difficult to maintain.

One way to remedy our growing code is to reorganize our code into different files and import them into the same game using <script> elements inside our index.html file.

Currently, the <body> of index.html looks like:
```js
<body>
  <script src="https://cdn.jsdelivr.net/npm/phaser@3.16.2/dist/phaser.min.js"></script>
  <script src="game.js"></script>
</body>
We can break up the code in game.js into files, each one containing code for a specific scene so that our <body> looks more like:

<body>
  <script src="https://cdn.jsdelivr.net/npm/phaser@3.16.2/dist/phaser.min.js"></script>

  <script src="firstScene.js"></script>
  <script src="secondScene.js"></script>
  <script src="thirdScene.js"></script>
  <script src="game.js"></script>
</body>
```
We’ll keep each Scene’s code inside separate files to make it easier to maintain our growing code and avoid the need to scroll through a single gigantic game file.

## Instructions

We’ve already provided new blank files, StartScene.js and GameScene.js.

To include these files in our game, in index.html add two <script> elements BELOW the <script> element that links to the Phaser CDN.

One of the <script> will have a src attribute of "StartScene.js" and the other a src attribute of "GameScene.js".

Copy the entire code for the StartScene class from game.js and paste the code into the StartScene.js file.

Remove the code for the StartScene class from game.js.

Like we did for StartScene, transfer the GameScene scene code to the GameScene.js. Make sure that the game.js no longer has the GameScene code.

## My Code
```js
// Paste in ONLY the GameScene class below:


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
  
```
