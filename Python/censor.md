PRACTICE MAKES PERFECT<br>
censor<br>

You're doing great with these string function challenges. Last one!

**Instructions:**
Write a function called censor that takes two strings, text and word, as input. It should return the text with the word you chose replaced with asterisks. For example:
```python
censor("this hack is wack hack", "hack")
```
should return:
```python
"this **** is wack ****"
```
Assume your input strings won't contain punctuation or upper case letters.
The number of asterisks you put should correspond to the number of letters in the censored word.

**SOLUTION:**
```python
 def censor(text, word):
    if word in text:
        text = text.replace(word, "*" * len(word))
    return text
```
