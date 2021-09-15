# RegexPLAINED

Introductory paragraph (replace this with your text)

## Summary

Briefly summarize the regex you will be describing and what you will explain. Include a code snippet of the regex. Replace this text with your summary.

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

### Quantifiers

A `quantifier` is a symbol or expression used after a character or group which specifies how often that element is allowed to occur to have met the search conditions.

#### Quantifiers include:

| Key | Description | Expression | Example |
| :---: | :-----------: | :---: | :--- |
| ? | zero or once | `colou?r` | matches both "color" and "colour" |
| * | zero or more | `ab*c` | matches "ac", "abc", "abbc" etc |
| + | one or more | `ab+c` | matches "abc", "abbc" etc, but not "ac" |
| {n} | *n* times | `ab{2}c` | matches only "abbc" |
| {min,} | *min* times | `ab{2,}c` | matches "abbc", "abbbc" etc |
| {min,max} | *min* & *max* times | `ab{1,2}c` | matches "abc" and "abbc" |


### Grouping Constructs

### Bracket Expressions

### Character Classes

A `character class` defines a subset or range of criteria that the search should meet. 

Character Classes include: 
>but are not limited to.

| Key | Description | Example |
| :---: | :-------: | :--- |
| [a-z] | Lowercase Alphabetic Characters | lowercase `a` to lowercase `z` |
| [A-Z] | Uppercase Alphabetic Characters | uppercase `A` to uppercase `Z` |
| [a-Z] | All Alphabetic Characters | `aAbBcC` or `ab...zAB...Z`
| [0-9] | Numeric Characters | `0, 1, 2, 3, 4...9` |
| [`^`0-9] | `NON`-Numeric Characters | strings of alphabetic characters


### The OR Operator

### Flags

### Character Escapes

## Author

A short section about the author with a link to the author's GitHub profile (replace with your information and a link to your profile)
