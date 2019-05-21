## Sprite Sheets

One common tool used to create animations is a sprite sheet that contains all the images that depict how a sprite can move. Take for instance:

sprite sheet of four frames showing Codey walking
As we move through the frames (individual images) of the sprite sheet, Codey starts walking!

To implement an animation in our game we need to:

* Load in the sprite sheet.
* Create the sprite object.
* Create the animation by selecting specific frames from the sprite sheet.
* Play the animation.

Let’s focus first on loading in our sprite sheet:
```js
class ExampleScene extends Phaser.Scene {
  preload() {
    this.load.spritesheet( 'spriteKey' , 'spriteSheet.png', { frameWidth: 100, frameHeight: 100 });
  }
}
```
this.load.spritesheet() takes three arguments: the sprite’s key as a string, the location of the sprite sheet, and an object with the properties frameWidth and frameHeight these properties indicate how many pixels wide and tall the individual frames are. Be sure to use accurate values since inaccurate frameWidth or frameHeight values will result in a misshaped sprite or a nonfunctioning animation!

Now, let’s load in Codey’s sprite sheet!

## Instructions

In game.js, inside GameScene‘s preload() method, call this.load.spritesheet() with these arguments in the following order:

'codey'
'https://s3.amazonaws.com/codecademy-content/courses/learn-phaser/Cave+Crisis/codey_sprite.png'
{ frameWidth: 72, frameHeight: 90 }

We won’t see anything until the next exercise, but we’re off to a great start!

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

    // Load in the sprite sheet below:
		this.load.spritesheet('codey', 'https://s3.amazonaws.com/codecademy-content/courses/learn-phaser/Cave+Crisis/codey_sprite.png', { frameWidth: 72, frameHeight: 90 } );
    
  }


  create() {
    // gameState.active is true if the game is playble (not game over)
    gameState.active = true;

    // Creates the background image
    this.add.image(0, 0, 'cave').setOrigin(0, 0);

    // Creates platforms group
    const platforms = this.physics.add.staticGroup();
    // An array of platform positions that is iterated over to create the platforms 
    const platPositions = [
      { x: 50, y: 575 }, { x: 250, y: 575 }, { x: 450, y: 575 }, { x: 400, y: 380 }, { x: 100, y: 200 },
    ];
    platPositions.forEach(plat => {
      platforms.create(plat.x, plat.y, 'platform');
    });    
  }

  update() {
    
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
