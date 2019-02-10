## SESSION ATTRIBUTES

Review

Congratulations! You now know how to persist data throughout an Alexa session. Let’s review what you learned:

* We define session attributes using key: value pair syntax.
* You can modify session attributes by assigning new values to them (e.g. this.attributes["numberCorrect"]++)
* You can access a slot, such as answer, from the JSON response, like:
```js
this.event.request.intent.slots.answer.value
```
* You can combine session attribute values with other strings to generate a custom speech output, like:
```js
this.response.listen('Hello, ' +
     this.attributes['name'] + 
     '. What is your favorite language?');
```
It's a good idea to refactor your code by saving session attributes to variables.
```js
var name = this.attributes['name'];
```
It’s important to note that session attributes persist throughout the session, but if we were to open the skill again, those same attributes would be reset.

In a later lesson, we’ll show you how to preserve your values across sessions using an AWS DynamoDB database, where you will learn how to give Alexa "long-term memory".

**Instructions:**
Now that you've finished, test your skill on echosim.io! If you're looking to do more, think about what additional features or game logic this skill could have. For example, what would happen if a user reached the end of the deck? How could we relate a user’s progress to their current language?

If Echosim isn't working, try opening it in a new tab by clicking here.
