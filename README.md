# Challenge Seventeen Expressions Tutorial

This walk through written tutorial is intended to explain what a regular expression is and the proper way to use it.  THese expressions, known as a "Regex Expression" are used when the user or client is needing to match certain character combinations within a string.  This allows the individual to pull out information from a certain part of a body of code known as as "code snippet".  This information can then be used to help the user or client match said information with an email or other important information.

## Summary

This gist tutorial will use a specific string of code to explain and give specific examples of parts of the code and how they can be used and interpreted.  The code displayed is used in order to match emails.  The code allows a user or client to verify that an email follows a certain and correct format.

/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [Grouping Constructs](#grouping-constructs)
- [Bracket Expressions](#bracket-expressions)
- [Character Classes](#character-classes)
- [The OR Operator](#the-or-operator)
- [Flags](#flags)
- [Character Escapes](#character-escapes)

## Regex Components

### Anchors

An Anchor is used to start and end the regular expression, for example in this line of code:

/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/

The anchors are ^ and $.  Other common anchors are \b and \B.  The ^ anchor at the beginning specifically indicates that a certain combination of characters are required to be at the beginning, whereas the $ anchor indicates a specific combination of characters needs to be at the end.

### Quantifiers

Quantifiers are used to indicate how many times a certain specific character and/or group of characters are required to have a match.  Certain common quantifiers are ?, *, and +.  In our code we have three quantifiers that we will break down and explain.

The first quantifier used is the + quantifier located in the first portion of our regex code.  This particiular quantifier indicates that multiple occurances of the matching character pattern are allowed in this case.

The second quantifier is actually the same one as the first, the + quantifier.  Again, this will allow for the same function as the first quantifier allowing for multiple matching character patterns.

The final quantifier is located near the end of the entire code, indicated as {2, 6}.  This quantifier allows for a minimum and maximum amount of characters allowed to be accepted into the pattern.  The numbers indicate the minimum of 2 and the maximum of 6.

### Grouping Constructs

Utlization of grouping constructs together will allow us to apply specific quantifiers to a group of characters.  Much like our quantifiers, we have 3 groups of constructs in our regex.  In this instance the groupings are indicated by being within a set of paranthesis.

The first grouping is using a search function, specifically looking for the alphabetical characters A through Z, the individual numbers of 0 through 9, and finally a specific grouping of special characters that are allowed within the email username.  This is indicated in this part of the regex: ([a-z0-9_\.-]+)

The second grouping is used to indicate what is allowed or expected in the domain name portion of the email address.  One specific requirement indicated by this grouping is that the domain name characters should be concluded with a . character.  Also, the \da-z\ indicates the requirement of alphabetical characters. This is indicated in this part of the regex: ([\da-z\.-]+)

The final grouping is used to indicate the ending of the email address which should always end with a suffix after the . symbol and has to be within the minimum character requirement of 2 and the mad character of 6.  This is often seen as a ".com" or ".gov" and so in.  This isi indicated in the last part of the regex: ([a-z\.]{2,6})

### Bracket Expressions

The use of square brackets in an expression and indicates the character set you want to make sure matches.  As with our quantifiers and our constructs there are three specific sets of expression in brackets in this example.  These being [a-z0-9_\.-] , [\da-z\.-], and [a-z\.].

### Character Classes

The user of character classes indicates what specific characters will be allowed within our search.  For example, the a-z seen multiple times in our regex indicates that the alphabetical characters a to z are allowed.  Similarly the 0-9 class indicates the single digit numbers of 0 through 9 are allowed.  When these classes are placed together they make a combination indicating both classes are allowed.  Finally, certain classes indicate that specific special characters can be allowed, such as the _\.- class.

### The OR Operator

OR Operators are useful but not used in this specific example.  Quite literally the | translates to an "or" statement that can be used to combine searches for specific words, for example "moons|stars" will search for either moons or stars in the document.

### Flags

Flags are not used in our specific example either.  They can be used to perform specific search functions that eliminate or expand search parameters.  For example, the i flag will indicate "ignore".

### Character Escapes

With regard to special characters, character escapes indicate the allows of those specific characters.  Our regex has a "_\.-" that allows for the characters . and -

## Author

Written by Bridgett Rice 