## Changing the Weather

If a long journey goes on for several days, how do we communicate that length to the folks playing our game? We’re going to use a few strategies to add in concepts of ambience, lighting, time of day, and weather to our game to make these same assets feel like the world they’re apart of turns and changes like our own.

The sky’s color is the easiest thing for us to change, by changing the background color of the game. Since we actually want to update the color of the sky multiple times within our single game, we can make a new “background”, a rectangle with the same dimensions as our canvas. We will be able to update the color of our new background with the appropriate color of the sky.

## Instructions

Let’s create the background that’s going to become the sky now! In create(), before making any of our other backgrounds, we want to make gameState.bgColor, a GameObject rectangle (so that we can update it to be different colors).

Give this.add.rectangle() the following arguments, saving the results in gameState.bgColor:
```
0,
0,
config.width,
config.height
```
Then call .setOrigin(0, 0) on it to center it.

We’ve created a .setWeather() method to help update the background and any other changes to our levels we might need. Inside .setWeather() after checking if weather exists, set gameState.bgColor.fillColor equal to bgColor.

In order for this to take effect, we need to add weather information to our Levels! Find where we define Level1 and, inside the constructor, set this.weather to 'afternoon'.

For Level2 set this.weather to 'twilight'.

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

    // Create gameState.bgColor here!

    this.createParallaxBackgrounds();

    gameState.player = this.physics.add.sprite(125, 110, 'codey').setScale(.5);

    gameState.platforms = this.physics.add.staticGroup();

    this.createAnimations();
    this.levelSetup();

    this.cameras.main.setBounds(0, 0, gameState.bg3.width, gameState.bg3.height);
    this.physics.world.setBounds(0, 0, gameState.width, gameState.bg3.height + gameState.player.height);

    this.cameras.main.startFollow(gameState.player, true, 0.5, 0.5)
    gameState.player.setCollideWorldBounds(true);

    this.physics.add.collider(gameState.player, gameState.platforms);
    this.physics.add.collider(gameState.goal, gameState.platforms);

    gameState.cursors = this.input.keyboard.createCursorKeys();
  }

  createPlatform(xIndex, yIndex) {
    // Creates a platform evenly spaced along the two indices.
    // If either is not a number it won't make a platform
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

  createParallaxBackgrounds() {
    gameState.bg1 = this.add.image(0, 0, 'bg1');
    gameState.bg2 = this.add.image(0, 0, 'bg2');
    gameState.bg3 = this.add.image(0, 0, 'bg3');

    gameState.bg1.setOrigin(0, 0);
    gameState.bg2.setOrigin(0, 0);
    gameState.bg3.setOrigin(0, 0);

    const game_width = parseFloat(gameState.bg3.getBounds().width)
    gameState.width = game_width;
    const window_width = config.width

    const bg1_width = gameState.bg1.getBounds().width
    const bg2_width = gameState.bg2.getBounds().width
    const bg3_width = gameState.bg3.getBounds().width

    if (gameState.bgColor) {
    	gameState.bgColor .setScrollFactor(0);
    }
    gameState.bg1.setScrollFactor((bg1_width - window_width) / (game_width - window_width));
    gameState.bg2.setScrollFactor((bg2_width - window_width) / (game_width - window_width));
  }

  levelSetup() {
    for (const [xIndex, yIndex] of this.heights.entries()) {
      this.createPlatform(xIndex, yIndex);
    } 
    
    gameState.goal = this.physics.add.sprite(gameState.width - 40, 100, 'campfire');

    this.physics.add.overlap(gameState.player, gameState.goal, function() {
      this.cameras.main.fade(800, 0, 0, 0, false, function(camera, progress) {
        if (progress > .9) {
          this.scene.stop(this.levelKey);
          this.scene.start(this.nextLevel[this.levelKey]);
        }
      });
    }, null, this);

    this.setWeather(this.weather);
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

      if (gameState.player.y > gameState.bg3.height) {
        this.cameras.main.shake(240, .01, false, function(camera, progress) {
          if (progress > .9) {
            this.scene.restart(this.levelKey);
          }
        });
      }
    }
  }

  setWeather(weather) {
    const weathers = {
      'morning': {
        'bgColor': 0xF8c3aC,
      },

      'afternoon': {
        'bgColor': 0x0571FF,
      },

      'twilight': {
        'bgColor': 0x18235C,
      },

      'night': {
        'bgColor': 0x000000,
      },
    }
    if (weather) {
      let { bgColor } = weathers[weather];
      // Update gameState.bgColor.fillColor here!
      
    }
  }
}

class Level1 extends Level {
  constructor() {
    super('Level1')
    this.heights = [4, 7, 5, null, 5, 4, null, 4, 4];
    // Add Level1 weather here
    this.weather = 'afternoon';
  }
}

class Level2 extends Level {
  constructor() {
    super('Level2')
    this.heights = [5, 4, null, 4, 6, 4, 6, 5, 5];
    // Add Level2 weather here
    this.weather = 'twilight';
    
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
