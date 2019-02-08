
## SLOTS

Interaction Model: Slot Types

In this lesson, you will create a skill that accepts a language user input, interprets it, and responds accordingly. There are two possible dialogues, but each will start with:

Alexa: What is Codecademy's most popular language?
User: Is it {language}?
The {language} value above is a slot. It is like a variable that holds the input from the user. In our case the user input may be: Ruby, Python, Java, JavaScript, HTML, or CSS.

Based on the user response, the Alexa-powered device will respond with different answers based on whether the user is correct or incorrect:

Alexa (Correct): Nice Job! Python is Codecademy's most popular language.

Alexa (Incorrect): Sorry, Python is Codecademy's most popular language.
Add slots
The first step in adding a slot to your interaction model is determining the type of data you are trying to capture from users.

For example: When a user says, “Alexa, ask History Buff what happened on June third”. In this statement, “June third” is the value of a date slot.

Built-in Slots
Alexa provides a list of pre-built slot types, like AMAZON.DATE, AMAZON.NUMBER, AMAZON.DURATION, and more. Within the Skill Builder, you can browse these existing types to see if there is a match for the information you are trying to collect.

Custom Slots
While it is always a good idea to check the list of built-in slots, sometimes the type of values you are trying to collect from the user will not be available as a built-in slot. In these cases, you will want to create a custom slot.

For example, there is no programmingLanguageType built-in slot, so we need to create a custom slot for our interaction model. We will provide our custom programmingLanguageType slot the following values: Ruby, Python, Java, JavaScript, HTML, or CSS.

It is important to note that these values act as training data for Alexa's machine learning algorithms. Alexa will still attempt to interpret user input that doesn't exactly match the values listed above. Providing these sample values improves the chances of Alexa getting the user input accurately.

Once you've created a custom slot type you can reuse it in any of your skill's intents.
