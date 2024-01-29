# Regex Hex Value Tutorial

Regular expressions, or regex for short, are a series of special characters that define a search pattern. Regex can be used in many ways to validate information that normally would be limited direct matches. Regex can return direct matches or any series of characters that match the specified pattern the expression. 

## Summary

In this tutorial we will be using a regex to validate a hex value.

`/^#?([a-f0-9]{6}|[a-f0-9]{3})$/`

Examples: `#355C7D` `#6C5B7B` OR `#C06` `#F67`

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

The characters ^ and $ are both considered to be anchors. The character ^ will match the beginning of a string. The character $ will match the end of a string.

/`^`#?([a-f0-9]{6}|[a-f0-9]{3})`$`/

### Quantifiers

The quantifiers in this specific regex are {6} and {3}. The length of each of these codes is 6 characters or 3 characters, not counting the # symbol. Curly brackets can provide three different ways to set limits for a match: 
- { n }—Matches the pattern exactly n number of times.
- { n, }—Matches the pattern at least n number of times.
- { n, x }—Matches the pattern from a minimum of n number of times to a maximum of x number of times.

/^#?([a-f0-9]`{6}`|[a-f0-9]`{3}`)$/

### Grouping Constructs

As regular expressions grow more complicated, you may check multiple parts of a string to determine that different sections fulfill different requirements. To break these sections up, you'll need to use grouping constructs.

The primary way you group a section of a regex is by using parentheses (()). Each section within parentheses is known as a subexpression. Unlike bracket expressions, subexpressions look for an exact match unless they're told to do otherwise. Grouping constructs have two primary categories: capturing and non-capturing. The important thing to understand is that capturing groups capture the matched character sequences for possible re-use (including a numbered backreference) while non-capturing groups do not. A grouping construct can be made non-capturing by adding the characters ?: at the beginning of an expression inside the parentheses.

/^#?`(`[a-f0-9]{6}|[a-f0-9]{3}`)`$/

### Bracket Expressions

Anything inside a set of square brackets ([]) represents a range of characters that we want to match. These patterns are known as bracket expressions, but they are also known as a positive character group, because they outline the characters we want to include.

/^#?(`[`a-f0-9`]`{6}|`[`a-f0-9`]`{3})$/

### Character Classes

A character class in a regex defines a set of characters, any one of which can occur in an input string to fulfill a match. Here are some of the common character classes:
- .—Matches any character except the newline character (\n)
- \d—Matches any Arabic numeral digit. This class is equivalent to the bracket expression [0-9].
- \w—Matches any alphanumeric character from the basic Latin alphabet, including the underscore (_). This class is equivalent to the bracket expression [A-Za-z0-9_].
- \s—Matches a single whitespace character, including tabs and line breaks

/^#?([`a-f0-9`]{6}|[`a-f0-9`]{3})$/

### The OR Operator

Much like the pipe operator in Javascript, | is used to signify "OR" in a regex. The | disjunction adds an option to our regex. We want a 6-character hex code that includes capital letters A-F and numbers 0-9, OR we can also accept 3-character hex code that includes capital letters A-F and numbers 0-9.

/^#?([a-f0-9]{6}`|`[a-f0-9]{3})$/

### Flags

Flags are placed at the end of a regex, after the second slash, and they define additional functionality or limits for the regex. There are six optional flags that can be used, either separately or together and in any order. There are six optional flags that can be used, either separately or together and in any order, but these are the three you're most likely to encounter:
- g—Global search: the regex should be tested against all possible matches in a string.
- i—Case-insensitive search: case should be ignored while attempting a match in a string
- m—Multi-line search: a multi-line input string should be treated as multiple lines

### Character Escapes

The backslash (\) in a regex escapes a character that otherwise would be interpreted literally. For example, the open curly brace ({) is used to begin a quantifier, but adding a backslash before the open curly brace (\{) means that the regex should look for the open curly brace character instead of beginning to define a quantifier. 

It's important to note that all special characters, including the backslash (\), lose their special significance inside bracket expressions.

## Author

Thank you for visiting my gist! I hope you have found my egular expression hex value tutorial helpful. For more of my work check out my GitHub at: 
- https://github.com/jakewilly14

Or you can contact me by email at:
- jakewilly14@gmail.com
