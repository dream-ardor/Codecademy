## Flipping an Animation

Codey’s animation looks great moving to the right. But if we apply the exact same logic to move left, Codey looks like they’re being blown back by some wind or doing the moonwalk. (While it’s cool, it isn’t exactly what we’re going for).

As a fix, we need to set the .flipX property of the animation to be true or false depending on which direction we want our sprite to turn.
```js
class ExampleScene extends Phaser.Scene {
  // … Previous code
  update() {
    if (gameState.cursors.right.isDown) {
      gameState.exampleSprite.setVelocityX(100);
      gameState.exampleSprite.anims.play('movement', true);
      // The sprite is facing its original direction
      gameState.exampleSprite.flipX = false;
    } else if ( gameState.cursors.left.isDown) {
      gameState.exampleSprite.setVelocityX(-100);
      gameState.exampleSprite.anims.play('movement', true);
      // The sprite is facing its flipped direction
      gameState.exampleSprite.flipX = true;
    }
  }
}
```
When our Sprite is moving to the right, we assign .flipX to false, since our sprite sheet original has the sprite facing the right. Otherwise, when moving left, we assign .flipX to true so that it’s flipped on its x-axis and facing left.

By manipulating .flipX we cam animate our sprite with a sprite sheet that faces one direction!

Let’s now add this into our game!

## Instructions

Let’s first get Codey turning to the left. In the else if condition, assign gameState.player.flipX a value of true.

After you clear this step, make Codey move to the left and then back to the right. It seems like Codey can’t turn back to the right. But don’t worry, we’ll fix this behavior in the next step.

We should allow Codey to turn back to the right when need be.

In the if condition, assign gameState.player.flipX a value of false.

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
    
    // Creates Codey's idle animation
    this.anims.create({
      key: 'idle',
      frames: this.anims.generateFrameNumbers('codey', { start: 4, end: 5 }),
      frameRate: 5,
      repeat: -1
    });
  }

  update() {
    if (gameState.active) {
      if (gameState.cursors.right.isDown) {
        gameState.player.setVelocityX(350);
        gameState.player.anims.play('run', true);
        // Add your code for step 2 below:
        gameState.player.flipX = false;
        
      } else if (gameState.cursors.left.isDown) {
        gameState.player.setVelocityX(-350);
        gameState.player.anims.play('run', true);
        // Add your code for step 1 below:
				gameState.player.flipX = true;
        
      } else {
        gameState.player.setVelocityX(0);
        // Plays the idle animation if no arrow keys are pressed
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
