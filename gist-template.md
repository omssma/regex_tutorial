# Regex Tutorial: Mathcing an Email

The porpose of this tutorial is to describe the different parts that make up a regeular expression. Also known as regex. Regex is a sequence of characters that define a search pattern and when included in code or search algorithms, they can be used to find certain patterns of characters within a string. They are also used to validate user inputs.

## Summary

This tutorial will examine the regex below to search for an valid email address.

``/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/``

The first part of the above regex expression uses an ^ to start the string. The expression, then, is broken into three parts:-

Part 1: ([a-z0-9_\.-]+) – This part of the expression matches one or more lowercase letters between a-z, numbers between 0-9, underscores, periods, and hyphens. The expression is then followed by the @ sign.

Part 2: ([\da-z\.-]+) – The domain name must be matched so it can use one or more digits, letters between a-z, periods, and hyphens. The domain name is then followed by a period \..

Part 3: ([a-z\.]{2,6}) – The third part matches the top level domain. This section searches for any group of letters or dots that are 2-6 characters long. This can also account for region-specific top level domains.

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

Examples of anchors in regex are the beginning of a string, signified by ``^`` and the end of a string signified by ``$``. 

### Quantifiers

Quantifiers indicate the number of characters or expressions to match. This regex has two quantifiers ``+`` and ``{}``. The ``+`` is looking for one or more of the expressions existing in ``[]``. The ``{2,6}`` which signifies between 2 and 6 instances of the character class ``[a-z\.]`` that comes before it.

### OR Operator

The pipe | is considered an alternation. It matches the expression that comes before or aftet it. This quantifier can also affect specific characters, or a whole expression.

### Character Classes

Character Classes are used to find (a) specific character(s). The character class in this example is ``/d`` which looks for any digit in the string. Other examples of character classes are ``/w``, which looks for a word, ``/s`` looks for any whitespace character such as a space, tab or line break, and ``.`` looks for anything.

### Flags

Flags are "optional parameters that we can add to a plain expression to make it
search in a different way" (https://www.codeguage.com/courses/regexp/flags) by
modifying the expressions behavior. Flags are indicated by a single alphabetic
character and multiple flags can be used by writing them one after another.
Flags used in email matching are: \*`(m)`: if enabled, matches the end of the line instead of the end of the string
(indicated by '$'),

### Grouping and Capturing

You can group and capture strings by using ``()``. Any text between the ``()`` is considered a group. Grouping allows us to extract the groups characters for validations. In this case we have three groups. The first, ``([a-z0-9_\.-]+)``, the second ``([\da-z\.-]+)`` and the third ``([a-z\.]{2,6})``. 

### Bracket Expressions

Bracket expressions are used to define a set of characters that can be matched. Bracket expressions go between ``[]``. This regex example has three bracket expressions that define the character classes.
``[a-z0-9_\.-]``
``[\da-z\.-]``
``[a-z\.]``

### Greedy and Lazy Match

Greedy and lazy qualifiers allow you to find the longest and shortest match. We have two greedy qualifiers in this example, ``+`` and ``{}``. These attempt to expand the match as far as they can go. If you want to find the shortest match, you can add a ``?`` to make them lazy.

### Boundaries

There are also variations of this regex which can be done by using a pair of word boundaries. When this is implemented, the regex would search for email addresses in large text files instead of checking whether the input as a whole is an email address. 
<br><br> If the user would like to implement this, they would replace both `^` and `$` anchors with `\b` so the new regular expression would be:
<br> `\b([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})\b`

### Back-references

Backreferences match the same text as previously matched by a capturing group.

### Look-ahead and Look-behind

Lookahead and lookbehind, collectively called “lookaround”, are zero-length assertions just like the start and end of line, and start and end of word anchors explained earlier in this tutorial. The difference is that lookaround actually matches characters, but then gives up the match, returning only the result: match or no match.

## Author

For any questions, please contact me at omar@email.com or at https://github.com/omssma/regex_tutorial
