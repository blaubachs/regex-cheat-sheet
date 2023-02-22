# Regex Cheat Sheet

This gist is a quick tutorial/cheat sheet for regex, otherwise known as regular expressions, and how to properly use it in your code.

## Summary

This gist is a quick sheet to look at to help along with learning regex, and using it in JavaScript.

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

Regex anchors do not consume characters. The purpose of these are to assert matching at a specific place.

- ^ is used for the beginning of a string or line.
- $ is used for the end of a string or line.

### Quantifiers

In regex, there are several different types of quantifiers.

- "?" is used for zero or one.
- "*" is used for zero or more.
- "+" is used for one or more.
- "{m}" is used for m times.

### OR Operator

The or operator works very similarly to javascript. This is denoted with a "|".

For example, if we use "gray|grey", this will match any string with gray OR grey inside of it.
Alternatively, we could match just the letter inside of gray like so : gr(a|e)y.

### Character Classes

Character classes are created within square brackets- [ ].

These represent single characters. If we use [abc], it will select a character in that position with EITHER a, b, or c.

### Flags

Flags can be used to change how our matching will occur in our regex.

- i is used for case insensitive matching.
- g is used to look for all matches, without it, only the first match will be returned.
- m is used to cover multiple lines.
- s allows a dot "." to match the new line character "\n".
- u enables full unicode support.

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

Bracket expressions can be used to select a range of characters you would like to use. In our example in the "grouping and capturing" section, this is utilized.

In short, if we had a string that was the full alphabet, but we only wanted the characters from d-r, we would simply wrap square brackets around it like [d-r].

Multiple ranges can be represented if they are in these brackets.

### Greedy and Lazy Match

Greedy:

With greedy matching, the regex algorithm will try to match a pattern at a position for every position in the string.
This can be problematic in some specific circumstances, for example, if we were trying to select from a string with quotes in it-

Our string:
- I "like" to have "fun".

With greedy matching, using /".+"/, it will return ' "like" to have "fun" '.

Lazy:

With lazy matching, the engine will repeat its' search as few times as possible. For our string above, if we use lazy matching, it will have the expected result.
To use lazy matching, we need to use the ? operator after another operator. 

Example:
- Using the same string above, all we need to add is the ? operator after the + operator.

Using /".+?"/ will return "like" and "fun".

### Boundaries

Boundaries can be used to very easily select whole words. These are anchors in a way, as well.

- \w allows you to perform whole word matching. It will just select every word in the string by default.


### Back-references

Back-references refer to a section previous to a matched section of a string.

- back-references are specified with a backslash and a digit. '\1'. 

### Look-ahead and Look-behind
Look-ahead:

The syntax for look-ahead is "a(?=b)". This means "look for a, but match it only if it is *followed by* b". 

Example string:
"3 pieces of cheese cost $40."

If I only wanted to return 40, I could write an expression like "/\d+(?=/.)/". This will search for any number, and then, it looks for anything followed by a ".". This will return 40.

Look-behind:

The syntax for look-behind is "(?<=b)a". This is very similar to look-ahead, but it looks for something to match before a.

Example string:
"3 pieces of cheese cost $40."

If I wanted to return 40, I could write an expression like "/(?<=$)\d+/". This will look for any numbers after $. In our case, it will return 40.
## Author

Written by Ben Laubach, studying full stack web development in the University of Washington.

Github: [blaubachs](https://github.com/blaubachs)