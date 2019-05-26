## Fading Out

Fading out of a Scene seems like a fitting transition. A cue taken from the film industry, fade-out offers a much softer effect than the shake but is as concise in Phaser. .fade() is a camera method that takes the following arguments:

* duration, the length of the fade in milliseconds.
* red, the 0-255 integer value of how red the fadeout color is.
* green, the 0-255 integer value of how green the fadeout color is.
* blue, the 0-255 integer value of how blue the fadeout color is.
* force, starts the fadeout over if it’s already been started.
* callback, the callback to use during the fadeout effect.
* context, the context to use for the callback function (defaults to the Scene the camera is in).
We can call:
```js
this.cameras.main.fade(100, 255, 255, 255, false, function(camera, progress) {
  if (progress > .5) {
    gameState.player.x = 5;
  }
});
```
In the above code the camera fades to white very quickly. Halfway through the fadeout, the gameState.player gets moved 5 pixels from the left edge of the game.

## Instructions

In order to transition from one level to another, we need something to indicate the end of the level. In Codey IV: Tundra Terror we’re going to use a video game staple: the bonfire! What we need to do is add in a new bonfire sprite to our physics engine. Then, when Codey interacts with the bonfire, we fade out the level and put Codey in the new one!

Within .levelSetup() we’ve created our bonfire and started writing a overlap function for it. Let’s implement what happens when we get to the bonfire.

Within the callback in this.physics.overlap(), fade the camera to black by calling this.cameras.main.fade() with the following arguments:
```
800 (the duration)
0 (redness – black has (0, 0, 0) RGB or red-green-blue value)
0 (blueness)
0 (greenness)
false (don’t replay the fadeout)
function(camera, progress) {} (our callback function that we’ll fill in next checkpoint)
```
Inside the callback within our fadeout check if the fade is more than 90% done with progress > .9. If it is, start the next scene by calling this.scene.start(this.nextLevel[this.levelKey]).

## My Code
```js
class Level extends Phaser.Scene {
  constructor(key) {
    super({key});
    this.levelKey = key
    this.nextLevel = {
      'Level1': 'Level2',
      'Level2': 'Level3',
      'Level3': 'Level4',
    }
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

    gameState.player = this.physics.add.sprite(125, 110, 'codey').setScale(.5);

    gameState.platforms = this.physics.add.staticGroup();

    this.createAnimations();
    this.levelSetup();

    this.cameras.main.setBounds(0, 0, gameState.width, gameState.height);
    this.physics.world.setBounds(0, 0, gameState.width, gameState.height + gameState.player.height);

    this.cameras.main.startFollow(gameState.player, true, 0.5, 0.5)
    gameState.player.setCollideWorldBounds(true);

    this.physics.add.collider(gameState.player, gameState.platforms);
    this.physics.add.collider(gameState.goal, gameState.platforms);

    gameState.cursors = this.input.keyboard.createCursorKeys();
  }

  createPlatform(xIndex, yIndex) {
      if (typeof yIndex === 'number' && typeof xIndex === 'number') {
        gameState.platforms.create((220 * xIndex),  yIndex * 70, 'platform').setOrigin(0, 0.5).refreshBody();
      }
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

  levelSetup() {
    for (const [xIndex, yIndex] of this.heights.entries()) {
      this.createPlatform(xIndex, yIndex);
    } 
    
    gameState.goal = this.physics.add.sprite(gameState.width - 40, 100, 'campfire');

    this.physics.add.overlap(gameState.player, gameState.goal, function() {
      // Add in the collider that will fade out to the next level here
this.cameras.main.fade(800,0,0,0,false,function(camera,progress) {
  if (progress > .9) {
    this.scene.start(this.nextLevel[this.levelKey])
    
  }
})
      
    }, null, this)
  }

  update() {
    if(gameState.active){
      gameState.goal.anims.play('fire', true);
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

      if (Phaser.Input.Keyboard.JustDown(gameState.cursors.space) && gameState.player.body.touching.down) {
        gameState.player.anims.play('jump', true);
        gameState.player.setVelocityY(-500);
      }

      if (!gameState.player.body.touching.down){
        gameState.player.anims.play('jump', true);
      }

      if (gameState.player.y > gameState.height) {
        this.cameras.main.shake(240, .01, false, function(camera, progress) {
          if (progress > .9) {
            this.scene.restart(this.levelKey);
          }
        });
      }
    }
  }
}

class Level1 extends Level {
  constructor() {
    super('Level1')
    this.heights = [4, 7, 5, null, 5, 4, null, 4, 4];
  }
}

class Level2 extends Level {
  constructor() {
    super('Level2')
    this.heights = [5, 4, null, 4, 6, 4, 6, 5, 5];
  }
}

class Level3 extends Level {
  constructor() {
    super('Level3')
    this.heights = [6, null, 6, 4, 6, 4, 5, null, 4];
  }
}

class Level4 extends Level {
  constructor() {
    super('Level4')
    this.heights = [4, null, 3, 6, null, 6, null, 5, 4];
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
  scene: [Level1, Level2, Level3, Level4]
};

const game = new Phaser.Game(config);

```
