## SLOTS

Interaction Model: Associating Slots with Intents

Now that we have a programmingLanguageType slot, we need to link it to our LanguageIntent.

Imagine if our utterances were hard-coded names of common guesses, such as:

Is it Ruby
Is it Python
Is it JavaScript
Is it Java

We want to replace these hard-coded utterances with the language slot. We can use {} to specify which portion of a user's utterance to capture as the slot.

All of the utterances above could be captured with the following utterance:

Is it {language}
The steps in the instructions below will guide you through the process of adding sample utterances to your LanguageIntent.

The video on the right walks you through the steps to associate a slot with the LanguageIntent.

Create LanguageIntent
Since you have already created the custom programmingLanguageType slot, you can add a few utterances to a new intent using the following steps:

Create a new intent called LanguageIntent
* Add Is it {language} as a sample utterance to the LanguageIntent and press enter
* On the right side of the screen, and under Intent Slots, select Choose a slot type... and select programmingLanguageType
* Add a few more utterances. See below for examples:
Could it be {language}

I think it's {language}

Select Build Model when you're done
