# Regex Tutorial for HTML

I have made a tutorial explaining a specifics of regex so that we can understand the search pattern and how it works.

## Summary

Regex or regular expression is a sequence of characters that define a search pattern. These patterns are used by string-searching algorithms for "find" or "find and replace" operations on strings. It also looks for input validations on strings.

We will look a a string of code with regex, this code looks for a match HTML tag.

Example: `/^<([a-z]+)([^<]+)*(?:>(.*)<\/\1>|\s+\/>)$/`

The content below will explain each section of this code.

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

* `^abc$`	-^ start / $ end of the string
    * `^` Matches the beginning of the string, or the beginning of a line if the multiline flag (m) is enabled.This matches a position, not a character.
    * `$` Matches the end of the string, or the end of a line if the multiline flag (m) is enabled. This matches a position, not a character.

* `\b\B`	- word, not a word boundary
    * `\b` Matches a word boundary position between a word character and non-word character or position (start / end of string).
    * `\B` Matches any position that is not a word boundary. This matches a position, not a character.

### Quantifiers

Quantifiers indicate that the preceding token must be matched a certain number of times.

* `a*a+a?`	-0 or more, 1 or more, 0 or 1
    * "+" Matches 1 or more of the preceding token.
    * "*" Matches 0 or more of the preceding token.
    * "?" Matches 0 or 1 of the preceding token, making it optional.
    * "?" Makes the preceding quantifier lazy, causing it to match as few characters as possible. By default, quantifiers are greedy, and will match as many characters as possible.

### OR Operator

* `|` Acts like boolean OR. Matches the expression before or after the |.

### Character Classes

Character classes match a character from a specific set.

* `[ABC]` Characters inside brakets will match any character in the set.
* `[^ABC]` Adding a ^ will match any character that is not in the set.
* `[A-Z]` Add a dash between two characters will select a Range.
* `.` Will Match any characters expect linebreaks. Its like a wildcard and will accpet any input.
* `[\s\S]` A character set that can be used to match any character, including line breaks, without the dotall flag.
* `\w` Matches any word character (alphanumeric & underscore). Only matches low-ascii characters (no accented or non-roman characters).
* `\W` Matches any character that is not a word character (alphanumeric & underscore).
* `\d` Matches any digit character (0-9)
* `\p` Matches a character in the specified unicode category.

### Flags

Expression flags change how the expression is interpreted. Flags follow the closing forward slash of the expression.

* `i` Ignores case
* `g` Global search retain the index of the last match, allowing subsequent searches to start from the end of the previous match. Without the global flag, subsequent searches will return the same match.
* `m` Multiline flag When the multiline flag is enabled, beginning and end anchors (^ and $) will match the start and end of a line, instead of the start and end of the whole string.
* `u` Unicode
* `y` The expression will only match from its lastIndex position and ignores the global (g) flag if set. Because each search in RegExr is discrete, this flag has no further impact on the displayed results.
* `s` Dot (.) will match any character, including newline.

### Grouping and Capturing
* `(ABC)` Capturing groups multiple tokens together and creates a capture group for extracting a substring or using a backreference.
* `(?<name>ABC)` Named capturing group captures groups of a specific name.
* `\1` is a numeric Referance
* `(?:ABC)` Groups multiple tokens together without creating a capture group.

### Bracket Expressions

A bracket expression enclosed in square brackets is a regular expression that matches a single character, or collating element.

### Greedy and Lazy Match

* 'Greedy' means matching the longest possible string.
    A Greedy quantifier tells the engine to match as many instances of its quantified token or subpattern as possible.

* 'Lazy' means matching the shortest possible string.
    A lazy quantifier tells the engine to match as few of the quantified tokens as needed possible.

### Boundaries

The `\b` is an anchor like the ^ and the $ sign. It matches at a position that is called a “word boundary”.

### Back-references

Backreferences match the same text as previously matched by a capturing group. Suppose you want to match a pair of opening and closing HTML tags, and the text in between. Putting the opening tag into a backreference, we can reuse the name of the tag for the closing tag.

### Look-ahead and Look-behind

Lookaheads and lookbehinds forces the main expressions to be what you have defined it as. Without it being exactly what it is it will not be accepted as a valid input.

## Author

Andy Nguyen
My Github [github] https://github.com/andy-sd-858

