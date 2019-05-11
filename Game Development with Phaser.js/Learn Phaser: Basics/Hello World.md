## Hello World

Welcome to Learn Phaser! Phaser.js is a game framework built with JavaScript that you can use to make video games on the web! Phaser gives us a set of utilities that we can use so that we don’t have to start from scratch when we want to make a game. In this lesson we’re going to cover how we can use Phaser to do the following things:

* Draw shapes and images
* Play sounds and music
* Add realism with animations
* Introduce interactivity with the mouse

All in a way that can be quickly transitioned into a website that you can share with anyone! We’re also going to cover setting up a basic Phaser project. Along the way we’ll learn about what Phaser is and what it does for us so that we can add more complex logic to our games later!

This course is going to cover Phaser 3, older versions of Phaser (most notably Phaser 2/Phaser CE) will not work in this course. Experienced JavaScripters may notice the function keyword frequently used instead of the newer arrow syntax — this and other choices are for compatibility and simplicity with Phaser’s design. In all other cases we’ll be using up-to-date JavaScript features to allow you to carry the skills you learn here with you in the future.

This course will not be covering JavaScript syntax, so you might be interested in brushing up on our JavaScript course before taking the plunge here. We’ll try to keep everything accessible no matter what level programmer you are, so you might prefer to wait until you get stuck before you explore more about the language itself. As the saying goes: “All roads lead to [developing a series of awesome browser games with Phaser]”.

In order to stay up-to-date with Phaser related news, consider subscribing to the official Phaser World newsletter, run by the original creator and maintainer of Phaser.

## Instructions

A good game needs a good title screen! We’re going to cover all the code in this example in this lesson, but first let’s see if we can create the title screen for a new game.

Change the text in the first call of this.add.text(), the title, from “Codey’s Adventures in Codeworld” to the name of your game!

Now change the attribution from "by Codecademy" to your name or the name of your publisher!

By the way, you might want to work on getting a publisher, because you’re well on the way to creating your first game!

## My Code
```js
  // Change "Codey's Adventures\n  in Code World" to the name of your game
  this.add.text(50, 100, "Dan's Adventures in Coding", { font: "40px Times New Roman", fill: "#ffa0d0"});

  // Change "by Codecademy" to your name!
  this.add.text(130, 300, "by Dan Barrick", { font: "20px Times New Roman", fill: "#ffa0d0"});
}

const config = {
	type: Phaser.AUTO,
	width: 450,
	height: 600,
	backgroundColor: "#5f2a55",
	scene: {
    create
	}
};


const game = new Phaser.Game(config);
```
