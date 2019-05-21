## Animating

✓ Load in sprite sheet
✓ Create the sprite obect
✓ Create animation from sprite sheet
☐ Animate sprite

We have everything else set up, now let’s bring our sprite to life!

Inside update(), we can include our logic for controlling our sprite and animating it however we want.
```js
class ExampleScene extends Phaser.Scene {
  // … Previous code
  update() {
    if (gameState.cursors.right.isDown) {
      gameState.exampleSprite.setVelocityX(100);
      gameState.exampleSprite.anims.play('movement', true);
    }
  }
}
```
In the code above, if the right arrow key is pressed gameState.exampleSprite moves to the right. Then we play the animation by calling gameState.exampleSprite.anims.play('movement', true):

* gameState.exampleSprite.anims allows us to access all the animations we created.
* anims.play() will play all the animations, or a single animation if passed an argument.

We provide .anims.play() with two arguments:
* the first is an animation key, in this case it’s the movement animation.
* the second is a boolean, which won’t play the animation from the start, if it’s already in progress.
Let’s animate Codey!

## Instructions

In update(), there is an if statement already set up that moves Codey to the right.

Inside that if statement, call anims.play() on gameState.player. Pass the arguments 'run' and true to .play().

After passing this checkpoint, while in game, press your right arrow key to move Codey and see the current state of animation.

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

    this.anims.create({
      key: 'run',
      frames: this.anims.generateFrameNumbers('codey', { start: 0, end: 3 }),
      frameRate: 5,
      repeat: -1
    });

    this.physics.add.collider(gameState.player, platforms);
    gameState.player.setCollideWorldBounds(true);

    // Creates the Cursor object to check for arrow key presses
    gameState.cursors = this.input.keyboard.createCursorKeys();
  }

  update() {
    if (gameState.active) {
      if (gameState.cursors.right.isDown) {
        gameState.player.setVelocityX(350);
        // Add your code below:
				gameState.player.anims.play('run',true);    
      }
    }
  }
}


const config = {
  type: Phaser.AUTO,
  width: 500,
  height: 600,
  backgroundColor: "b9eaff",
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
