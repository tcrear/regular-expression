# Using Regular Expression (Regex) for URL Validation

Regular Expression, commonly known as regex, is a combination of numbers, letters, and characters. By using a specified combination, you
are able to search text (ex: programming, word documents, search engines, etc) for validation and pattern. Common validations regex is used for are: usernames, 
email addresses, phone numbers, URL's, etc. Regex formual's are beneficial to validate the user is inputing the expected data.

## Summary

The following tutorial will cover regex for URL validation. This will be broken down into several parts to show how it works. 
The snippet of the regex I will be covering in this tutorial is for:

* Matching a URL: `/^(https?:\/\/)?([\da-z\.-]+)\.([a-z\.]{2,6})([\/\w \.-]*)*\/?$/`

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [Grouping Constructs](#grouping-constructs)
- [Bracket Expressions](#bracket-expressions)
- [Character Classes and Escapes](#character-classes-and-escapes)
- [Flags](#flags)

## Regex Components

### Anchors
When looking at the regex to validate the URL, you will see a ^ and $. These are called anchors and identify the beginning '^' and end '$' of the sequence.
These are important features of the sequence because the anchors allow the program when to start looking and when to stop.

### Quantifiers
For URL matching, there are three common quantifier.

'?' - this quantifier is used to allow a user to access the website using regex even if they don't enter the full website URL.
This can occur if the user types in facebook.com instead of https://facebook.com. The user will still end up on the correct website.

'*' - this quantifier is used to match a string extension that allows the user to access websites that have one or more 
extensions/pages that you would like to move to view additional information. This can be google.com/maps, google.com/flights, 
google.com/news, etc. Code snippet: '([\/\w \.-]*)*\/?$/`' 

`{2,6}` - this quantifier is used to match a string of characters from a-z between 2 and 6 characters. This is often the .com 
extension that completes the URL for the inital site load. Code snippet: '([a-z\.]{2,6})'

### Grouping Constructs
There are four main groups for URL Regex - lets break it down by https://www.facebook.com/login
'/^(https?:\/\/)?' - this section pulls in the https part of the URL.
'([\da-z\.-]+)\.' - this section would pull in the website name such as facebook.
'([a-z\.]{2,6})'  - this section pulls in the '.com' in the URL string.
'([\/\w \.-]*)*\/?$/' - this section pulls in the /login part of the URL.

### Bracket Expressions
The reason they are broken down into thirds is to create smaller ranges that can be matched. The URL regex can be broken down into three bracket expressions:
`[\da-z\.-]` - this section can match a single character the range listed, plus numbers.
`[a-z\.]` - this section can match characters between a-z.
`[\/\w \.-]` - this section can match any word/character. 

### Character Classes and Escapes
There are two character classes that we see when matching a URL. 

The first one is ‘\d’ which matches a single character that is a digit. 
   Code from /regex/ `[\da-z\.-]`. 

The other one is ‘\w’ which can match any word, alphanumeric, or underscore.
   Code from /regex/ `[\/\w \.-]`

### Flags
Flags are used in regex at the beginning and end of the string with backslashes '/' and are on the outside of the anchors. 
The search function can change based on the three /regex/ below: 
- insensitive (i)
- global (g)
- multi-line (m)

## Author

I am currently taking the Full Stack Development Bootcamp out of the University of MN. I formerly worked in the financial 
services industry, and have chosen to pivot my career and learn a new skill. Please checkout my GitHub profile at 
https://github.com/tcrear. 