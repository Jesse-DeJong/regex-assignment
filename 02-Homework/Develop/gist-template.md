# Reg-exPLAINED

A regular expression or `regex` for short is a combination of defined characters and meta-characters with special functions used to define a search pattern. 

Even the most basic of searches such as hitting `CTRL-F` and searching a specific word can be thought of in terms of regex; referred to as a `literal`, where a word or phrase is defined and that exact text is matched against. 

Regex tends to be used for more complicated and/or agnostic searches where a set of numbers or characters are known to be valid and the expression uses a combination of rules to define what results should be returned.

## Summary 

A commonly used example of this more detailed regex is matching email addresses which can look like this; 
* Matching an Email: `/^([a-z0-9_\.-]+)`@`([\da-z\.-]+)\`.`([a-z\.]{2,6})$/`

Here the regex looks for the appropriate valid characters before and after the `@` symbol and `.` each email contains to filter them from a larger block of text or to assist in confirming them as valid submissions.

Each regex is made up of multiple components which we will explore through this email matching expression. 

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

The `anchors` are used to wrap the regex expression denoting the beginning of the string being matched from the `^`, and the ending of a string `$`. The exact paramaters of what will return a match being defined within these special characters.

* Matching an Email: `/^`([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})`$/`

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

* Matching an Email: /^([a-z0-9_\.-]`+`)@([\da-z\.-]`+`)\.([a-z\.]`{2,6}`)$/

In our example email matching regex this is used to state that only 2-6 characters may be included after the `.` at the end of the domain. It also makes use of the `+` quantifier indicating there should be one or more matches from the criteria.

### Grouping Constructs

A `grouping construct` is used where different sections of the target string must meet different requirements. In our example of the email checking these fall around the `@` and `.` symbols as the valid inputs for each subseqent section vary.

* Matching an Email: /^`(`[a-z0-9_\.-]+`)`@`(`[\da-z\.-]+`)`\.`(`[a-z\.]{2,6}`)`$/

Grouping constructs also have the added functionality of `capturing` (which can be disabled) where a numbered backreference is created. This can be disabled by use of a `?` prefacing the beginning of an expression inside patentheses. 

### Bracket Expressions

A `bracket expression` is simply a series or range contained within `[ ]` comprised of characters that we wish to match.

* Matching an Email: /^(`[`a-z0-9_\.-`]`+)@(`[`\da-z\.-`]`+)\.(`[`a-z\.`]`{2,6})$/

Bracket Expression Examples: 
| Key | Description | Example |
| :---: | :-------: | :--- |
| [a-z] | Lowercase Alphabetic Characters | lowercase `a` to lowercase `z` |
| [A-Z] | Uppercase Alphabetic Characters | uppercase `A` to uppercase `Z` |
| [a-Z] | All Alphabetic Characters | `aAbBcC` or `ab...zAB...Z`
| [0-9] | Numeric Characters | `0, 1, 2, 3, 4...9` |
| [`^`0-9] | `NON`-Numeric Characters | strings of alphabetic characters |

### Character Classes

A `character class` defines a subset or range of criteria that the search should meet similarly but more compactly to bracket expressions.

Character Classes Examples: 

| Key | Description |
| :---: | :-------: |
| `.` | Matches any character except the newline character (\n) |
| `\d` | Matches any Arabic numeral digit. Equivilent to the bracket expression [0-9] |
| `\w` | Matches any alphanumeric character from the basic Latin alphabet including the underscore ( _ ). This class is equivilent to the bracket expression [A-Za-z0-9_] |
| `\s` | Matches a single whitespace character, including tabs and line breaks |

* Matching an Email: /^([a-z0-9_\.-]+)@([`\d`a-z\.-]+)\.([a-z\.]{2,6})$/

### The OR Operator

Pattern logic can be expanded further with an OR operator by inserting `|` between conditions. An OR operator can alter the expression `[abc]` to `(a|b|c)`, the user of the OR condition allows for cases which would fail the former condition such as `acb` to match under the later condition. This feature of regex is not utilised in our email checking instance.

### Flags

Placed at the end of a regex a flag provides additional functionality. Flags can be used separately or together (in any order) and include;

| Key | Description |
| :---: | :-------: |
| `g` | Global Search |
| `i` | Case-`in`sensitive |
| `m` | Multi-line search | 
| `d` | Generate indices for substring matches |
| `s` | Allows `.` to match newline characters |
| `u` | Treat a pattern as a sequence of unicode code points |
| `y` | Perform a sticky search that matches starting at the current position in the target string |

None are used in our email checking example.

### Character Escapes

Special characters which infer an operation such as `{ }` surrounding a minimum or maximum value must be `escaped` to be matched literally rather than as thier special funciton. This is done by inserting a preceeding `\` to tell the regex that the `literal` character is what should return a match.

* Matching an Email: /^([a-z0-9_`\.`-]+)@([\da-z`\.`-]+)`\.`([a-z`\.`]{2,6})$/


## Author

A short section about the author with a link to the author's GitHub profile (replace with your information and a link to your profile)
