## SLOTS

Slots: Passing Values to Lambda Functions

With the slot now defined as part of the utterance, let's see how it is passed to the Lambda function. Recall that Alexa operates on JSON objects. Using the simulator on the right, we can see the underlying JSON passed to the Lambda function from Alexa.

Go ahead and type a guess, like How about ruby?, in the text box to the right and select ask code academy.

You can see what JSON is passed to the Lambda function on the right side of the simulator. Note the portion with the intents:
```
"intent": {
  "name": "LanguageIntent",
  "slots": {
    "language": {
      "name": "language",
      "value": "ruby"
     }
   }
}
```
Our guess, "ruby", is contained within the "value" key.
