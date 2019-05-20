## Using Classes in Phaser (ES6)

In this exercise, we’re going to refactor the code from the Learn Phaser: Physics Lesson.

One major change that we’re going to implement is the inclusion of JavaScript’s class syntax. Each class will represent a Scene and contain the familiar preload(), create(), and update() functions. We’re going to refer to these functions as methods since they’re functions that belong to a class. Below is a sample template:
```js
class ExampleScene extends Phaser.Scene {
  constructor(){
    super({ key: 'ExampleScene' });
  }
  preload() {
    // ...
  }
  create() {
    // ...
  }
  update() {
    // ...
  }
}
```
Our ExampleScene class is a subclass of Phaser.Scene:

* It has a constructor() method that is used to create an initialize the Scene object.
* Inside the constructor() method, we call super() which calls the constructor() of the Phaser.Scene.
* We provide super() with the object { key: 'ExampleScene' } so that we can refer to this class in our config object.
preload(), create(), and update() are included but are now methods, notice the lack of the function keyword.
* In order for our Phaser game to know about this class, we’ll also need to change the config object:
```js
const config = {
  // …
  scene: [ExampleScene]
};
```
In the code above, our config object’s scene property has a value of an array. While the only element currently inside the array is ExampleScene, we can later add more scenes to this array.

By refactoring our code, we’re laying the groundwork to include more scenes in this existing game. In later exercises, we can add scenes for starting and ending the game!

## Instructions

Create a new class called GameScene that extends Phaser.Scene

Inside the class you just created, add a constructor() method.

With our constructor set up, we need a way to reference GameScene.

Inside the constructor() method, call super() with the argument { key: 'GameScene' }

We can now move all the preload(), create(), and update() functions into the GameScene class.

## My Code
```js
const gameState = {
	score: 0
};

// Create your GameScene class below:
class GameScene extends Phaser.Scene{
  constructor(){
    super({key:'GameScene'})
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
    const xCoord = Math.random() * 640;
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
	scene: [GameScene]
};

const game = new Phaser.Game(config);
```

After copying the 3 functions into the GameScene class, remove each method’s function keyword.

At this point we will NOT have the global preload(), create(), and update() functions. That code exists ONLY inside the GameScene class. That also means that our game won’t work now, but we’ll fix this in the next step!

5.
To be able to use GameScene, locate the config object and its scene property. Delete the scene‘s current value and replace it with an array containing GameScene.
