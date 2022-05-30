# Ultimate Regex Tutorial

Welcome to this ultimate REGEX tutorial where we do our best to explain REGEX and how it works.

## Summary

Briefly summarize the regex you will be describing and what you will explain. Include a code snippet of the regex. Replace this text with your summary.

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [OR Operator](#or-operator)
- [Character Classes](#character-classes)
- [Flags](#flags)
- [Grouping and Capturing](#grouping-and-capturing)
- [Bracket Expressions](#bracket-expressions)
- [Greedy and Lazy Match](#greedy-and-lazy-match)
- [Boundaries](#boundaries)
- [Back-references](#back-references)
- [Look-ahead and Look-behind](#look-ahead-and-look-behind)

## Regex Components

### Anchors

Anchors have special meaning in regular expressions. They do not match any character. Instead, they match a position before or after characters:

 * ^ – The caret anchor matches the beginning of the text.
   * Example - /^J/ will match true for any string that begins with "J"
 * $ – The dollar anchor matches the end of the text.
   * Example - /t$/ will match true for anty string ending with "t" 
 * ^$ - In combination, will check if a string fully matches a pattern
   * Example - /^[a-z0-9-_]{3,16}$/ will match tru for any string that has a lowercase, number, -, _, and it at least 3 -16 characters long. False, on any other character! 

Informational source: [Regular Expression: Anchors](https://www.javascripttutorial.net/regular-expression-anchors)

### Quantifiers

Quantifiers match a number of instances of a character, group, or character class in a string.

* A number in curly braces {n} is the simplest quantifier.
  * Example - /\d{4}/ matches a four-digit number.
* You can also use range in quantifiers.
  * Example - /\d{2,4}/g will find numbers that have numbers 2-4 digits long.
* Quantifiers also have shorthands which are beneficial to the developer
  * The + is shorthand for 1 0r more: /\d+/g
  * The ? is shorthand for 0 or 1: /colou?r/ will match both color and colour
  * The * means 0 or more: /Java\w*/g will match the string Java followed by any word character.
* Common quantifier examples:
  * Whole Numbers: /^\d+$/
  * Decimal Numbers: /^\d*.\d+$/
  * Both Whole and Decimal Numbers: /^\d*(.\d+)?$/
  * Neagative, Positive(Whole and Decimal) Numbers: /^-?\d*(.\d+)?$/

Informational source: [Regular Expression: Quantifiers](https://www.javascripttutorial.net/regular-expression-quantifiers)

### OR Operator

Alternation is the term in regular expression that is actually a simple “OR”.

* In a regular expression it is denoted with a vertical line character |.
  * Example - /html|php|css|java(script)?/gi will find a match on html or php or css or java or javascript
* Also, To apply alternation to a chosen part of the pattern, we can enclose it in parentheses:
  * Example - I love HTML|CSS matches I love HTML or CSS.
  * Example - I love (HTML|CSS) matches I love HTML or I love CSS.

Informational source: [Regular Expression: OR Operator](https://javascript.info/regexp-alternation)

### Character Classes

A character class allows you to match any symbol from a certain character set. A character class is also called a character set.

* Digit Character - \d match a single digit or a character from 0 to 9.
* White Space - \s match a single whitespace symbol such a space, a tab (\t), a newline (\n).
* Word Character - \w matches the ASCII character including Latin Alphabets, Digits, and the Underscore

There are also Inverse Classes!

* Not Digit - \D matches any character except a digit e.g., a letter.
* Not Whitespace - \S matches any character except a whitespace e.g., a letter
* Not Word Character - \W matches any character except a word character e.g., non-Latin letter or space.

Finally there is the Dot Character. it is a special character class that matches any character except a newline

* Example - /E.6/ will match a pattern of ES6, E16, ... ; But does not match E\n6

Informational source: [Regular Expression: Character Classes](https://www.javascripttutorial.net/javascript-character-classes)

### Flags

Flags are a robust but easy way to alter your search on a given pattern. There are only six of them.

* i - With this flag the search is case-insensitive
* g - With this flag the search looks for all matches, without it – only the first match is returned.
* m - Multiline mode - used for strings with newline, paragraphs, ...
* s - Enables “dotall” mode, that allows a dot . to match newline character \n
* u - Enables full Unicode support. The flag enables correct processing of surrogate pairs.
* y - “Sticky” mode: searching at the exact position in the text

Informational source: [Regular Expression: Flags](https://javascript.info/regexp-introduction#flags)

### Grouping and Capturing

Grouping and Capturing is a way to capture all or portions of a string into an array for use. PLease see the following break-daown:

* Given resource/id or posts/10
  * For /\w+\/\d+/:
    * Where \w+ will give us posts
    * Where \/ will give us /
    * Where \d+ will give us 10
    * The return would give us posts/10
  * For /\w+\/(\d+)/:
    * Where p-arenthesis around digits+
    * The return would give us an array of posts/10 and 10

As you can see we can capture the whole pattern as well as portions of the pattern. You can also use multiple parenthesis within the pattern to capture
as much as a breakdown of a pattern for what use you may need: /(\w+)\/(\d+)/

Informational source: [Regular Expression: Grouping and Capturing](https://www.javascripttutorial.net/javascript-regex/capturing-groups)

### Bracket Expressions

Bracket expressions, also known as Sets and Ranges. Is a robust way to search for values in a string pattern from a-b. Where a = a starting point and b = the ending point.

* The most common would be:
  * Numerical - [0-9] will look for a digit 0-9
  * Lowercase - [a-z] will look for a character a-z
  * Uppercase - [A-Z] will look for a character A-Z
*  Other Uses:
  * /[cbr]ats/g - will return a match where the first character can be c, b, or r; and the following pattern ats.
  * Exclusion - /[^cbr]ats/g will return any first character other than c, b, r and the folling pattern ats.

Informational source: [Regular Expression: Bracket Expressions](https://www.javascripttutorial.net/regular-expression-sets-and-ranges)

### Greedy and Lazy Match

The maiin difference between greedy and lazy match is how explicit you want to be in searching your pattern. In comparison to sql:
It would be the difference of a query using equals vs match. See the following examples:

* Given /".+"/g = Greedy
  * " starts with "
  * . matches any character except the newline
  * + matches the preceding character one or more times
  * " ends with "
  * g flag returns all matches
  * This woulkd be a Greedy match that explicitly looks for that pattern.
  * Returns '<button type="submit" class="btn">Send</button>': "submit" class="btn"
* Given /".+?"/g = Lazy
  * Returns '<button type="submit" class="btn">Send</button>': ["submit", "btn"]

Informational source: [Regular Expression: Greedy and Lazy Match](https://www.javascripttutorial.net/javascript-regex-greedy)

### Boundaries

### Back-references

### Look-ahead and Look-behind

## Author

I am an expeienced Quality Analyst and an aspiring Devedloper. As for Regex: It has been a common tool throughout my career. In cases that requirements state a strict format
on data values. Regex has been a strong tool used to validate data through automation. Although easay to use; it can be difficult to master!

Lucas Zimmerman: [GITHUB](github.com/dolomiteson)	[EMAIL](mailto:zimmerman.lucas@hotmail.com)
