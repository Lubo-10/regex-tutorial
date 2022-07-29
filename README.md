# Regex Tutorial For Matching an Email

Regular Expressions, or Regex, are helpful tools used across many programming languages to find a specified combination of characters. Regex allows the programmer to search for any variation of a string matching a pattern instead of being limited to a specific, or "literal", query. For example, in a large database with multiple email address entries, a Regex pattern search of [any name]@[any domain].[any extension] will easily find all email addresses.

* View the Gist Page at [GitHub Gist](https://gist.github.com/Amir-Hackett/c7bc1597bd3fef8336207ff6adc59722).

## Contents
* [Usage](#Usage)
* [Summary](#Summary)
* [Credits](#Credits)

## Usage

GIVEN a regex tutorial
- WHEN I open the tutorial
  - THEN I see a descriptive title and introductory paragraph explaining the purpose of the tutorial, a summary describing the regex featured in the tutorial, a table of contents linking to different sections that break down each component of the regex and explain what it does, and a section about the author with a link to the author’s GitHub profile
- WHEN I click on the links in the table of contents
  - THEN I am taken to the corresponding sections of the tutorial
- WHEN I read through each section of the tutorial
  - THEN I find a detailed explanation of what a specific component of the regex does
- WHEN I reach the end of the tutorial
  - THEN I find a section about the author and a link to the author’s GitHub profile

## Summary

This tutorial explains the different components in the following regex:

**Matching an Email**

```regexp
/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/
```
**Two ways to define a regular expression**

```javascript
let regexp = new RegExp("pattern", "flags");

let regexp = /pattern/; // no flags
let regexp = /pattern/gmi; // with flags g,m and i
```

- Slashes `/.../` tell JavaScript that we are creating a regular expression. They play the same role as quotes for strings
- `^` is an anchor that matches from the start of input
-`a-z` matches lowercase alpha characters
- `0-9` matches the numeric characters
- `_` matches the literal '_' character
- `.` matches the literal '.' character
- `-` matches the literal '-' character
- `@` matches the special character `@`
- `\.` matches the literal `.` 
- `$` is an anchor that matches to the end of the string

**Note**

*A dot `.` on its own represents any character. In order to search for a dot within a string we need to 'escape' search by preponing the search for a dot with the backslash character. By using the `\` it will make the following character a literal instead of a special character*

```text
Explanation for [a-z0-9_\.-] 

- matches all lowercase characters from a to z
- matches all numeric characters from 0 to 9
- matches special characters such as `_`, `-`, and `.`
```

```text
Explanation for [\da-z\.-]

- `\d` matches for any decimal digit
- matches all lowercase characters from a to z
- matches special characters such as `.` and `-`
```

```text
Explanation for [a-z\.]

- matches all lowercase characters from a to z
- matches special character, `.`
```
