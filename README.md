# Regex Cheat Sheet

This gist is a quick tutorial/cheat sheet for regex, otherwise known as regular expressions, and how to properly use it in your code.

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

There are several different types of components when using regular expressions. 

Single characters such as "^ . [ $ ( ) | * + ? { \" are called operator characters. 

### Anchors

Say we have three strings: "abc", "bac", and "cba".

- ^ is used to match at the beginning of the target string.
If I write "^a", this will only match the string "abc" and not the others. It is looking for the first part of that string.

- $ is used to end the selection.

### Quantifiers

### OR Operator

The or operator works very similarly to javascript. This is denoted with a "|".



### Character Classes

### Flags

### Grouping and Capturing

Grouping allows us to grab a specific part of a string, and allows us to exclude parts we do not want.

For example:
Say we have several file names we are trying to access.
- cool_js.js
- best_js.js
- bad.js.notarealfile

To use a group to extract just the names of the files, we would want to use paranthesis to grab what we wanted, and outside, we can use certain characters to exclude.

For our example above, if I use "^([a-z_]+)\.js$", it will only select the first two file names. In our case, it will capture "cool_js" and "best_js", and ignore the one with ".notarealfile".

### Bracket Expressions

### Greedy and Lazy Match

### Boundaries

### Back-references

### Look-ahead and Look-behind

## Author

A short section about the author with a link to the author's GitHub profile (replace with your information and a link to your profile)