## Cameras

In order to grant the joy of exploration and discovery it becomes important for the game world to be larger than what a player immediately sees upon entering the game. A useful way to convince the player of your game of this is by employing the use of cameras. A camera is a view of the game world. Some games (those with mini-maps, for instance) employ multiple cameras, but we will be focusing on just using one.

Phaser creates a camera by default, which we have so far been using without any customization. Its bounds are set to be the same as the dimensions for your Game given in config. It also does not move at all, but we will be changing both of those things for our platformer.
```js
create() {
  gameState.player = this.physics.add.sprite(100, 100, 'codey');
  this.cameras.main.setBounds(0, 0, 2000, 600);
  this.cameras.main.startFollow(gameState.player);
}
```
Above we modified the default camera, this.cameras.main, to make it aware that the world is larger than our current window. We do this by calling .setBounds() and giving bounds larger than our config width and height. We also tell the camera to follow along our main player by calling .startFollow() and passing it the sprite we want to follow.

The .startFollow() method also has several additional optional arguments you can pass which we can use to customize how fast the camera locks-on to its target and whether the target should be in the center of the screen exactly or offset somewhat. Here are the arguments for .startFollow(): (target, roundPixels, lerpX, lerpY, offsetX, offsetY).

* target is the sprite for the camera to follow
* roundPixels is a boolean that effects rendering, set it to true if you’re experiencing camera jitter.
* lerpX and lerpY are the speed (between 0 and 1, defaults to 1) with which the camera locks on to the target. A lower lerp * * speed will have the effect that your character is moving much faster than the camera.
* offsetX and offsetY is the offset for the camera. Set offsetX to something like -200 will keep Codey on the left side of the screen (so that more of the level ahead is on the screen).
## Instructions

We've created a snowy background for Codey to run through. Let’s set up the camera to run through it with them! Inside our Level’s create() function, after the call to .createAnimations() start by setting the bounds of the camera by calling this.cameras.main.setBounds() with the following arguments:
```
0
0
gameState.width
gameState.height
```

Now set the boundaries of the world to be the same as the boundaries of the camera by calling this.physics.world.setBounds() with the same arguments.

Now follow Codey around by calling this.cameras.main.startFollow() with the following arguments:

gameState.player (the sprite the camera should follow)
true (keep away from camera jitter)
0.5 (don’t lock on, but follow fairly quickly in the x direction)
0.5 (as above, for the y direction)

## My Code
```js
class Level extends Phaser.Scene {
  constructor() {
    super()
  }

  preload() {
    this.load.image('platform', 'https://s3.amazonaws.com/codecademy-content/courses/learn-phaser/Codey+Tundra/platform.png');
    this.load.image('snowflake', 'https://s3.amazonaws.com/codecademy-content/courses/learn-phaser/Codey+Tundra/snowflake.png');
    this.load.spritesheet('campfire', 'https://s3.amazonaws.com/codecademy-content/courses/learn-phaser/Codey+Tundra/campfire.png',
      { frameWidth: 32, frameHeight: 32});
    this.load.spritesheet('codey', 'https://s3.amazonaws.com/codecademy-content/courses/learn-phaser/Codey+Tundra/codey.png', { frameWidth: 72, frameHeight: 90})

    this.load.image('bg1', 'https://s3.amazonaws.com/codecademy-content/courses/learn-phaser/Codey+Tundra/mountain.png');
    this.load.image('bg2', 'https://s3.amazonaws.com/codecademy-content/courses/learn-phaser/Codey+Tundra/trees.png');
    this.load.image('bg3', 'https://s3.amazonaws.com/codecademy-content/courses/learn-phaser/Codey+Tundra/snowdunes.png');
  }

  create() {
    gameState.active = true

    gameState.bg3 = this.add.image(0, 0, 'bg3').setOrigin(0)

    gameState.player = this.physics.add.sprite(125, 110, 'codey').setScale(.5);

    gameState.platforms = this.physics.add.staticGroup();

    this.createAnimations();

    // set Cameras here
    this.cameras.main.setBounds(0, 0, gameState.width, gameState.height)
    this.physics.world.setBounds(0, 0, gameState.width, gameState.height);
    this.cameras.main.startFollow(gameState.player, true, 0.5, 0.5);
    
    gameState.player.setCollideWorldBounds(true);

    this.physics.add.collider(gameState.player, gameState.platforms);

    gameState.cursors = this.input.keyboard.createCursorKeys();
  }

  createAnimations() {
    this.anims.create({
      key: 'run',
      frames: this.anims.generateFrameNumbers('codey', { start: 0, end: 3 }),
      frameRate: 10,
      repeat: -1
    });

    this.anims.create({
      key: 'idle',
      frames: this.anims.generateFrameNumbers('codey', { start: 4, end: 5 }),
      frameRate: 10,
      repeat: -1
    });

    this.anims.create({
      key: 'jump',
      frames: this.anims.generateFrameNumbers('codey', { start: 2, end: 3 }),
      frameRate: 10,
      repeat: -1
    })

    this.anims.create({
      key: 'fire',
      frames: this.anims.generateFrameNumbers('campfire'),
      frameRate: 10,
      repeat: -1
    })
  }

  update() {
    if(gameState.active){
      if (gameState.cursors.right.isDown) {
        gameState.player.flipX = false;
        gameState.player.setVelocityX(gameState.speed);
        gameState.player.anims.play('run', true);
      } else if (gameState.cursors.left.isDown) {
        gameState.player.flipX = true;
        gameState.player.setVelocityX(-gameState.speed);
        gameState.player.anims.play('run', true);
      } else {
        gameState.player.setVelocityX(0);
        gameState.player.anims.play('idle', true);
      }
    }
  }
}

const gameState = {
  speed: 240,
  ups: 380,
  width: 2000,
  height: 600,
};

const config = {
  type: Phaser.AUTO,
  width: 500,
  height: 600,
  fps: {target: 60},
  backgroundColor: "b9baff",
  physics: {
    default: 'arcade',
    arcade: {
      gravity: { y: 800 },
      enableBody: true,

    }
  },
  scene: [Level]
};

const game = new Phaser.Game(config);

```
