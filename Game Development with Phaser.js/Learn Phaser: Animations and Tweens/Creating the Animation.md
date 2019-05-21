## Creating the Animation

With our sprite sheet loaded in, we can now create our sprite object and the animation sequence.

This logic goes inside our create() method:
```js
class ExampleScene extends Phaser.Scene {
  // … Previous code
  create() {
    gameState.exampleSprite = this.physics.add.sprite(100, 600, 'spriteKey');
  }
} 
```
The code above should look familiar, it’s the same way we create a sprite object from a single image. When our sprite loads in game, it’ll show the first frame of our sprite sheet.

We can now use this.anims.create() to create our animations:
```js
class ExampleScene extends Phaser.Scene {
  create() {
    gameState.exampleSprite = this.physics.add.sprite(100, 600, 'spriteKey');

    this.anims.create({
      key: 'movement',
      frames: this.anims.generateFrameNumbers('spriteKey', { start: 0, end: 5 }),
      frameRate: 10,
      repeat: -1
    });
  }
} 
```
this.anims.create() takes an object as an argument that has several properties. In the example above we included:

* key - how this animation will be referenced.
* frames - which frames of the sprite sheet we’re using
* this.anims.generateFrameNumbers('spriteKey', { start: 0, end: 5 }) is a Phaser method that returns an array of a sprite sheet’s frames from start up to (and including) end.
* frameRate - how many frames play per second (it will default to 24 if frameRate is not provided).
* repeat - how many times the animation repeats, use -1 to continuously repeat the animation.

To see what other properties we could include check out RexRainbow’s Phaser animation documentation

Let’s see how this looks in our own code!

## Instructions

In the create() method, first make the sprite object.

Assign gameState.player the value of calling this.physics.add.sprite() with the arguments:
```
255
500
'codey'
```
Still inside create(), call this.anims.create() and pass in the following object:
```js
{
  key: 'run',
  frames: this.anims.generateFrameNumbers('codey', { start: 0, end: 3 }),
  frameRate: 5,
  repeat: -1
}
```
Our animation’s now set up! In our next exercise, we’ll have Codey running!

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

    // Add your code below:
    gameState.player = this.physics.add.sprite(255,500,'codey');
    
    this.anims.create({
  key: 'run',
  frames: this.anims.generateFrameNumbers('codey', { start: 0, end: 3 }),
  frameRate: 5,
  repeat: -1
});
    

    // Collider object so Codey doesn't slip through the platforms
    this.physics.add.collider(gameState.player, platforms);
  }

  update() {

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
