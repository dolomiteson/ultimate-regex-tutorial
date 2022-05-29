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

### OR Operator

### Character Classes

### Flags

### Grouping and Capturing

### Bracket Expressions

### Greedy and Lazy Match

### Boundaries

### Back-references

### Look-ahead and Look-behind

## Author

I am an expeienced Quality Analyst and an aspiring Devedloper. As for Regex: It has been a common tool throughout my career. In cases that requirements state a strict format
on data values. Regex has been a strong tool used to validate data through automation. Although easay to use; it can be difficult to master!

Lucas Zimmerman: [GITHUB](github.com/dolomiteson)	[EMAIL](mailto:zimmerman.lucas@hotmail.com)
