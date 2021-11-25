# Regex Rundown

Welcome to the Regex Rundown. A complete reference guide.

## Summary

Regex is a great way of performing a very specific search or setting requirement criteria 

Let us use and email as an example. 
The following line can be used to used to set requirements for a valid email.
/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/

Take a look at the example email below.
Example@regex.com

If we section this off it starts to look similiar
(Example)@(regex).(com) is starting to look closer to the line we see above but what does it mean?
everything within the () may be different however we want the @ and the . to be exactly the same.

The first part of the email before the @ symbol is defined in ([a-z0-9_\.-]+) which matches any lowercase letter or digit 0-9 or underscores.

The @ symbol is a required for a valid email.

After the @ we have ([\da-z\.-]+) which matches one or more digits, letters, periods and hypens.

The . is also required so nothing will take its place.

After the period it requires any lowercase letter between 2 and 6 characters([a-z\.]{2,6})$

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
- ^ the caret anchor matches the beginning of the text.
- $ the dollar anchor matches the end of the text.

### Quantifiers

Quantifiers match a number of instances of a character, group, or character class in a string.

Exact {n} \d{4} - match four digits  
Range {n, m} \d{2,4}/g - match two, three, or four digits

### OR Operator

The symbol | is used to indicate OR 

I like (dogs|penguins)

It would match a string like "I like dogs" OR "I like penguins",
but not "I like cats" and not "I like dogs or pengiuins" 

### Character Classes

A character class allows you to match any symbol from a certain character set. A character class is also called a character set. Suppose that you have a phone number like this:

+1-(336)-123-5566
And you want to turn it into a plain number:

13361235566

let phone = '+1-(336)-123-5566';  
let re = /\d/g;

let numbers = phone.match(re);  
let phoneNo = numbers.join('');

console.log(phoneNo);

### Flags
Flags allow you to define where you are seaching for the information.
g allows a global search
i is a case-insensitive search
s allows . to match a newline characters

### Grouping and Capturing

Grouping is assigned by parentheses, it unifies a pattern or string to be matched in a complete block.

### Bracket Expressions

[a-z0-9_\.-] a-z indicates we are looking for lowercase a through z, 0-9 indicates we are looking for 0 through 9, and we literal match special characters "_" underscore, "\." dot, and "-" hyphen.  
[\da-z\.-] indicates we are looking for "\d" 0 through 9, "a-z" a through z, "\." dot, and "-" hyphen.  
[a-z\.] indicates we are looking for "a-z" a through z, and "\." dot.

### Greedy and Lazy Match

Greedy search
To find a match, regex uses the following pattern:

For every position in the string
Try to match the pattern at that position.
If there’s no match, go to the next position.

This can cause long matches like
the "dog" chased the "cat"
with an expression like  ".+"
the result would find the first and last ""
Resulting in the string = "dog" chased the "cat"

Lazy Match 
Uses a ? in order to indicate it will use the shortest possible result that matches
Using the previous example if we use  ".+?"
This would result in "dog" "cat"

### Boundaries

The \b is an anchor. The following three positions qualify as boundaries:  
1. Before the last character in a string if the first character is a word character.
2. After the last character in a string if the last character is a word character.
3. Between two characters in a string if one is a word character and the other is not.

### Back-references

Back-references allow you to match a pair of opening and closing tags.

### Look-ahead and Look-behind

These allow you to use the first and last line.

## Author

Zachary Blanks
Practicing code, currently posting code on GitHub
https://github.com/Nativeblanks

Gist page
https://gist.github.com/Nativeblanks/303145cc339db045a68b032947805f0a
