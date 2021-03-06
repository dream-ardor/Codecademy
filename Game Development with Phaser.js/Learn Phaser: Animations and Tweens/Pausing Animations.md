## Pausing Animations

Learning how to start an animation is one thing, pausing it is another. When it’s game over, or if we decide to include a pause option, we might opt to pause one or all of our animations.

In Phaser, we can call exampleSprite.anims.pause() on the sprite to put a pause on its animation.

We can also call this.anims.pauseAll() to pause all animations in a Scene.

Let’s try out these convenient methods in our own game.

## Instructions

We’ve included animated snowmen in the middle of the main platform. We also added in an Overlap object that checks when Codey comes in contact with a snowman, it works very similarly to a Collider object except it allows the sprites to overlap.

The Overlap object is in the create() method. Inside the callback function of the Overlap object, pause the animation of the snowman when the two sprites come into contact. Do this by calling gameState.enemy.anims.pause().

Test out what happens in the game after you clear this checkpoint!

We’ve paused one snowman animation, but let’s see what happens when we pause all the animations!

Inside the same callback function of the previous step, call this.anims.pauseAll().

## My Code
```js
const gameState = {};

class GameScene extends Phaser.Scene {
  constructor() {
    super({ key: 'GameScene' });
  }

  preload() {
    this.load.image('cave', 'https://s3.amazonaws.com/codecademy-content/courses/learn-phaser/Cave+Crisis/cave_background.png');
    this.load.image('platform', 'https://s3.amazonaws.com/codecademy-content/courses/learn-phaser/Cave+Crisis/platform.png');
    this.load.spritesheet('codey', 'https://s3.amazonaws.com/codecademy-content/courses/learn-phaser/Cave+Crisis/codey_sprite.png', { frameWidth: 72, frameHeight: 90 });

    // Loads in the snowman sprite sheet
    this.load.spritesheet('snowman', 'https://s3.amazonaws.com/codecademy-content/courses/learn-phaser/Cave+Crisis/snowman.png', { frameWidth: 50, frameHeight: 70 });
  }

  create() {
    gameState.active = true;

    this.add.image(0, 0, 'cave').setOrigin(0, 0);

    const platforms = this.physics.add.staticGroup();
    const platPositions = [
      { x: 50, y: 575 }, { x: 250, y: 575 }, { x: 450, y: 575 }, { x: 400, y: 380 }, { x: 100, y: 200 },
    ];
    platPositions.forEach(plat => {
      platforms.create(plat.x, plat.y, 'platform')
    });

    gameState.player = this.physics.add.sprite(50, 500, 'codey').setScale(.8)

    this.physics.add.collider(gameState.player, platforms);
    gameState.player.setCollideWorldBounds(true);

    gameState.cursors = this.input.keyboard.createCursorKeys();

    this.anims.create({
      key: 'run',
      frames: this.anims.generateFrameNumbers('codey', { start: 0, end: 3 }),
      frameRate: 5,
      repeat: -1
    });

    this.anims.create({
      key: 'idle',
      frames: this.anims.generateFrameNumbers('codey', { start: 4, end: 5 }),
      frameRate: 5,
      repeat: -1
    });

    // Creates the snowman sprite
    gameState.enemy = this.physics.add.sprite(225, 500, 'snowman');

    // Creates a Collider Object between the snowman and the platforms
    this.physics.add.collider(gameState.enemy, platforms)

    // Creates an animation using the snowman sprite sheet
    this.anims.create({
      key: 'snowmanAlert',
      frames: this.anims.generateFrameNumbers('snowman', { start: 0, end: 3 }),
      frameRate: 4,
      repeat: -1
    });

    // Plays the snowmanAlert animation
    gameState.enemy.anims.play('snowmanAlert', true)

    // Creates an Overlap object that detects when Codey overlaps with the snowman
    this.physics.add.overlap(gameState.player, gameState.enemy, () => {
      // Add your code below:
			gameState.enemy.anims.pause();
      this.anims.pauseAll();
    });
  }

  update() {
    if (gameState.active) {
      if (gameState.cursors.right.isDown) {
        gameState.player.setVelocityX(350);
        gameState.player.anims.play('run', true);
        gameState.player.flipX = false;
      } else if (gameState.cursors.left.isDown) {
        gameState.player.setVelocityX(-350);
        gameState.player.anims.play('run', true);
        gameState.player.flipX = true;
      } else {
        gameState.player.setVelocityX(0);
        gameState.player.anims.play('idle', true);
      }
    }
  }
}


const config = {
  type: Phaser.AUTO,
  width: 500,
  height: 600,
  physics: {
    default: 'arcade',
    arcade: {
      gravity: { y: 1500 },
      enableBody: true,
    }
  },
  scene: [GameScene]
};

const game = new Phaser.Game(config);

```
