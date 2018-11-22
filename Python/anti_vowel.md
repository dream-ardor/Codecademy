PRACTICE MAKES PERFECT<br>
anti_vowel<br>
Nice work. Next up: vowels!

**Instructions:**
Define a function called anti_vowel that takes one string, text, as input and returns the text with all of the vowels removed.

For example: anti_vowel("Hey You!") should return "Hy Y!". Don't count Y as a vowel. Make sure to remove lowercase and uppercase vowels.

**SOLUTION:**
```python
def anti_vowel(text):
  for i in "aeiouAEIOU":
     text=text.replace(i,"")
  return text
```  
    
