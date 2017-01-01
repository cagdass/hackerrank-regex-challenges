# Hackerrank Regular Expression Challenges

Solutions to Hackerrank's Regular Expression Challenges at [https://www.hackerrank.com/domains/regex/](https://www.hackerrank.com/domains/regex/)

**Last revision:** 1 January 2017

* [Introduction](#sub1) *Filming*
* [Character Class](#sub2) *Pre-production*
* [Repetitions](#sub3) *Pre-production*
* [Grouping and Capturing](#sub4) *Pre-production*
* [Backreferences](#sub5) *Pre-production*
* [Assertions](#sub6) *Pre-production*
* [Applications](#sub7) *Pre-production*

## Introduction

* [Matching Specific String](#s1q1)
* [Matching Anything But a Newline](#s1q2)
* [Matching Digits & Non-Digit Characters](#s1q3)
* [Matching Whitespace & Non-Whitespace Character](#s1q4)
* [Matching Word & Non-Word Character](#s1q5)
* [Matching Start & End](#s1q6)

### Matching Specific String

View on [Hackerrank](https://www.hackerrank.com/challenges/matching-specific-string)

#### Task
You have a test string *S*. Your task is to match the string `hackerrank`. This is case sensitive.

#### Solution
~~~python
# Use a regex made up of the given string.
# In Python, if your string is treated as a Regex if it has an "r" before the first quote.
Regex_Pattern = r'hackerrank'	
~~~

### Matching Anything But a Newline

View on [Hackerrank](https://www.hackerrank.com/challenges/matching-anything-but-new-line)

#### Task
You have a test string *S*.
 
Your task is to match the pattern `abc.def.ghi.jkx`, where each variable `a,b,c,d,e,f,g,h,i,j,k,x` can be any single character except the newline.

#### Solution
~~~python
# The caret, ^, matches the start of the line.
# And similarly, the dollar sign, $, matches the end of the line.
# A dot matches anything except for a newline character.
# And to match a dot we need to escape it using a backslash, like this: \.

# So the following regex matches:
# A line that has 3 non-newline characters, followed by a dot, 3 non-newline characters again,
# then a dot, 3 non-newline characters again a dot and then 3 non-newline characters and nothing else.
regex_pattern = r'^...\....\....\....$'
~~~

### Matching Digits & Non-Digit Characters

View on [Hackerrank](https://www.hackerrank.com/challenges/matching-digits-non-digit-character)

#### Task
You have a test string *S*. Your task is to match the pattern `xxXxxXxxxx`
Here `x` denotes a digit character, and `X` denotes a non-digit character.

#### Solution
~~~python
# \d matches a digit character [0,1,2,3,4,5,6,7,8,9]
# \D matches a non-digit character.

# So the following regex matches a sequence of
# 2 digits, 1 non-digit, 2 digit, 1 non-digit and 4 digits.
Regex_Pattern = r'\d\d\D\d\d\D\d\d\d\d'
~~~

## Character Class

## Repetitions

## Grouping and Capturing

## Backreferences

## Assertions

## Applications

