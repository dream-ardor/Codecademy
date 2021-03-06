## Tweens

While animations allow us to play through the frames of a sprite sheet, tweens help refine the transition from frame to frame. By creating in-between frames, sprites undergoing changes like their size and positions appear smoother.

One common usage of tweens is to convey movement, for instance:
```js
class ExampleScene extends Phaser.Scene {
  // … Previous code
  create () {
    gameState.exampleSprite = this.physics.sprite.add(0, 100, 'example');

    gameState.moveTween = this.tweens.add({
      targets: gameState.exampleSprite,
      x: 300,
      ease: 'Linear',
      duration: 3000,
      repeat: -1,
      yoyo: true
    });

    gameState.moveTween.play();

    // Later on … 
    gameState.moveTween.stop();
  }
}
```
In the code above we called this.tweens.add() to create a tween saved to gameState.moveTween. The object that we provided as an argument:

* targets determines which Sprites are affected (we could’ve also used an array)
* x determines the final x-coordinate of gameState.exampleSprite.
* ease describes how the tween plays.

We provided a value of Linear which means it plays at a constant speed. But if we wanted some variation, we could have provided another easing function.
* duration determines how long the tween lasts (in milliseconds).
* repeat is how many times the tween runs (use -1 to continuously play).
* yoyo is a true or false value, if it’s true, the tween plays in reverse for the Sprite to return back to its original state (size, position, angle, etc.) before the tween started. If it’s false, then the Sprite will remain as is after the tween finishes.

To play the tween, we call .play() on gameState.moveTween.
To stop playing the tween, we call .stop() on gameState.moveTween.

Let’s see this for ourselves!

## Instructions

Let’s add the tween inside our create() method. Since our tween will be related to our enemy sprite, assign gameState.enemy.move a value of this.tweens.add().

Supply this.tweens.add() an argument of an object will make the tween:
```
targets gameState.enemy.
moves the sprite to the 320 x-coordinate.
have an ease of 'Linear'.
lasts ( or has a duration) for 1800 milliseconds.
continuously repeat.
yoyo back and forth.
```
We’ve got the tween playing, but we should also include a means of stopping it.

In create(), locate the Overlap object of Codey and the exit. Inside the callback function of that Overlap object, call gameState.enemy.move.stop().

After clearing this checkpoint, see what happens when Codey reaches the exit!

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
    this.load.spritesheet('snowman', 'https://s3.amazonaws.com/codecademy-content/courses/learn-phaser/Cave+Crisis/snowman.png', { frameWidth: 50, frameHeight: 70 });
    // Loads exit sprite sheet 
    this.load.spritesheet('exit', 'https://s3.amazonaws.com/codecademy-content/courses/learn-phaser/Cave+Crisis/cave_exit.png', { frameWidth: 60, frameHeight: 70 });
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

    gameState.enemy = this.physics.add.sprite(480, 300, 'snowman');

    platforms
    this.physics.add.collider(gameState.enemy, platforms);
    
    this.anims.create({
      key: 'snowmanAlert',
      frames: this.anims.generateFrameNumbers('snowman', { start: 0, end: 3 }),
      frameRate: 4,
      repeat: -1
    });
    
    gameState.enemy.anims.play('snowmanAlert', true);

    this.physics.add.overlap(gameState.player, gameState.enemy, () => {
      // Executes code to end to game when Codey and the snowman overlap
      this.add.text(150, 50, '      Game Over...\n  Click to play again.', { fontFamily: 'Arial', fontSize: 36, color: '#ffffff' });
      this.physics.pause();
      gameState.active = false;
      this.anims.pauseAll();
      // Restarts the scene if a mouse click is detected
      this.input.on('pointerup', () => {
        this.scene.restart();
      })
    });

    gameState.exit = this.physics.add.sprite(50, 142, 'exit');
    this.anims.create({
      key: 'glow',
      frames: this.anims.generateFrameNumbers('exit', { start: 0, end: 5 }),
      frameRate: 4,
      repeat: -1
    });
    this.physics.add.collider(gameState.exit, platforms);
    gameState.exit.anims.play('glow', true);

    // Adds a win condition
    this.physics.add.overlap(gameState.player, gameState.exit, () => {
      this.add.text(150, 50, 'You reached the exit!\n  Click to play again.', { fontFamily: 'Arial', fontSize: 36, color: '#ffffff' });
      this.physics.pause();
      gameState.active = false;
      this.anims.pauseAll();
      // Add your code below for step 2:
      
      gameState.enemy.move.stop();
      
      
      this.input.on('pointerup', () => {
        this.anims.resumeAll();
        this.scene.restart();
      })
    })
    
    // Add your code below for step 1:
    gameState.enemy.move = this.tweens.add(
    {
      targets: gameState.enemy,
      x: 320,
      ease: 'Linear',
      duration: 1800,
      repeat: -1,
      yoyo: true,  
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
      // Codey jumps if they are touching the ground and either the space bar or up arrow key is pressed
      if ((gameState.cursors.space.isDown || gameState.cursors.up.isDown)&& gameState.player.body.touching.down) {
        gameState.player.anims.play('jump', true);
        gameState.player.setVelocityY(-800);
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
