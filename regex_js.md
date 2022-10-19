## <p align="center">Javascript Regex</p>

### **Methods**

**Test** - return true/false if string contains the pattern
~~~javascript
let testStr = "freeCodeCamp";
let testRegex = /Code/;
testRegex.test(testStr);
// OR
/Code/.test("freeCodeCamp")
~~~

**Match** - returns the actual match if found
~~~javascript
"Hello, World".match(/Hello/);
//this would return ["Hello"]
~~~

**Replace** - search and replace text in string
~~~javascript
let wrongText = "The sky is silver.";
let silverRegex = /silver/;
wrongText.replace(silverRegex, "blue");
// You can also access capture groups in the replacement string with $
"Code Camp".replace(/(\w+)\s(\w+)/, '$2 $1'); // Turns Code Camp into Camp Code

~~~


### **Flags**

```javascipt
\sometext\flagflagflag
```

i : ignore case

g : global search flag - return all matches

### **General**

- **|**: Lets you search with multiple constraints. Ex: "/yes|no/"
- **.** : The wildcard character "." matches any one character
    - Using the regex ```/hu./```will match with hum, hug, hub, etc
- **[]**: Restrict wildcard matches a little by using classes
    - Using the regex ```/hu[mg]/``` will match with hum and hug and nothing else
- **-** : Define a range of characters to match
    - find words beginning in a-e and ending in "at" -> ```/[a-e]at/```
    - You can search for a range of letters and numbers in one line: ```/a-e0-5/```
- **^**: Using match, defines a range of characters you don't want to match with
    - to match with everything but vowels: ```/^aeiou/```
    - Using test, it'll return true if the pattern is at the beginning of the string
- **+**: 1 or more. Used to check how many times a character appears, excluding repeats use.
    - Using ```/a+/``` would return 1 match for 'a' and 'aa' and two matches for 'abab'.
    - ```^[a-z]+[0-9]*$``` makes sure there is 1 or more a-z letters in front (^) and 0 or more numbers in the back ($).
- **\***: 0 or more. It's like longest common subsequence, but the last character can stretch abit.
    - Using ```/go*/``` on 'goooal' would return 'gooo' and on 'gut stuff' it'd return 'g'. There'd need to be a g to qualify as a match.
    - ```[a-z]+[0-9]*```: at least 1 letter and 0 or more numbers.
- **?**: To return the smallest match, use '?'. Reluctant instead of greedy
    - ```/t[a-z]*i/``` would match to 'titani' but ```/t[a-z]*?i/``` would return 'ti'
    - 0 or 1
- **$**: With test, it's used to see if a pattern appears at the end of a a string.
    - ```/mint$/.test("minty mint")``` returns true but ```/mint$/.test("minty yep")``` returns false.
- **()**: Capture groups. Substrings matched to the group are saved to a temp variable/
  - Numbered by the position of their opening parentheses
  - ex: ```/(\w+) \1 \1)/``` matches a word that occurs thrice seperated by spaces.
#### Quantifiers
- **?**: 0 or 1
- **\***: 0 or more.
- **+**: 1 or more.
- **{2}**: exactly 2. Used like '+' or '*'
- **{2,}**: 2 or more
- **(?=.{2}$)**: exactly 2 charcters in string. 
  - Looks to make sure the condition is met, before looking at the rest of the regex.
- **(?!...)**: Looks to make sure a pattern is not there.

#### Shortcuts
<em>Capitalize to invert</em>
- **\w**: One letter/number. matches to all letters and numbers. 
    - Equivalent to ```/[A-Za-z0-9_]/```
- **\W**: is the opposite of \w.
    - Equivalent to ```/[^A-Za-z0-9_]/``` using match
- **\d**: One digit. matches all numbers
    - is equivalent to ```/[0-9]/```
- **\D**: matches all non numbers
    - equivalent to ```/[^0-9]/```
- **\s**: Match whitespace
- **\r**: Match returns
- **\t**: Match tabs
- **\f**: match for meeds
- **\n**: match new line characters