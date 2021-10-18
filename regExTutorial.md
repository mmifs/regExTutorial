![APM](https://img.shields.io/apm/l/vim-mode?style=plastic)
# regExTutorial 

## Intro

This document is meant to serve as a tutorial for Regular Expressions, also known as RegEx.

Regular Expressions, or RegEx is a syntax for most common programming languages used primarily for identifying patterns in text using specific parameters, such as lower case letters, numbers, and meta characters such as "`~!@#$%'. This is especially useful when dealing with large amounts of data or information. For the sake of this document, I will be summarizing the regular expression used to identify email addresses, as seen below.

/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/

## Table of Contents

* [Intro](#intro)
* [Anchors](#anchors)
* [Quantifiers](#quantifiers)
* [License](#license)
* [Classes](#classes)
* [Tests](#tests)
* [Questions](#questions)


## Anchors

Anchors are used to assert a position before, after or between characters.

^ The 'caret' symbol is used to signify the beginning of a string, and will identify patterns based on additional parameters.

$ Similar to the caret, the dollar symbol will capture a string that ends with a particular set of characters.

These symbols can be seen wrapping the expression to identify emails, as to indicate that it is the beginning and end of the string that is being identified.

## Quantifiers

Quantifiers are used to assert the amount of characters that are being searched for given particular parameters.

"*" The asterisk (star) symbol is used to match with all (zero or more) of a given search parameter.

"+" one or more

"?" zero or one

{4} exactly a 4, or any other given number
{4,} 4 or more
{4,7} atleast 4 up to 7

| the vertical bar acts as an "or" operator, meaning any characters wrapping the bar will be matched in a similar fashion

[] signifies a character set, to be used with other regex. Put simply, everything in the character set can be considered within an overarching "or" statement

() separate addition regex expressions within a particular query

/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/

In the regex used to identify emails, you will find three character sets, as follows.

([a-z0-9_\.-]+)
([\da-z\.-]+)
([a-z\.]{2,6})

For these sets, they give character parameters (more on that later) within the square brackets to indicate a set of characters to match with. They are also wrapped with parentheses to indicate they are separate match queries.

For the first two, they include a plus sign in order to match with strings with one or more characters in this position. In other words, it will match with any email address at any domain that fit within the character sets with up to unlimited characters in the address or domain.

For the third set, it will only match with addresses with a domain extension that contain the given character set but only up to 6 characters, as indicated by the curly brackets {2,6}.

## Classes

. any character except a new line

\d single digit characters (numbers) (0-9)

\D not digits/numbers (0-9)

\w word character/letter (a-z, A-Z, 0-9)

\W not a word character

\s white space characters (space, tab, line break)

\S not white space

As stated previously, the email address regex is broken up into three character sets.

a-z0-9_\.-
\da-z\.-
a-z\.

The first set will search for any lowercase letters a-z, any numbers 0-9 in addition to the given symbols "_\.-".

Similarly, the second set will search for any digit character, any lowercase letter a-z, and the symbols "\.-".

The third will search only for lowercase a-z as well as the symbol ".".

## Summary

/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/

The simplest way to understand the regex to identify emails is to break it down by its character grouping, as has been done throughout this document. 

([a-z0-9_\.-]+) The first grouping is to match with the actual address of the email, the section prior to the "@" symbol. This includes a character set a-z, 0-9, symbols _\.- with the plus symbol used to match with this token between one and infinite times.

([\da-z\.-]+) The second section is to match with the actual domain name for the email address, such as outlook, gmail, hotmail, yahoo, etc. This includes a character set with any digit character, any lowercase letter a-z, symbols \.- with the plus symbol used to match with this token between one and infinite times.

([a-z\.]{2,6}) The third section is used to match with the domain extension, such as com, net, ca, gov, etc. The character set includes letters a-z, symbols .\. The curly brackets are to indicate only tokens with between 2 and 6 characters.

In addition to the groupings, the entire expression is wrapped in a caret (^) to start, and a dollar sign ($) to end as an indication of the start and end of a string. 

Each character grouping is separated into parentheses as to not interfere with one another, and each character set is wrapped in square brackets to indicate the start and end of the set. The entire expression is wrapped in back slashes (\\) to signify the beginning and end of the expression.

## License

This project is protected by an MIT license. For more information, please contact the author.


## Questions

Github: https://github.com/mmifs

Please forward any additional questions to my email: place@holder.com