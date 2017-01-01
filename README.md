# Hackerrank Regular Expression Challenges

Solutions to Hackerrank's Regular Expression Challenges at [https://www.hackerrank.com/domains/regex/](https://www.hackerrank.com/domains/regex/)

**Last revision:** 1 January 2017

* [Introduction](#Introduction) *Complete*
* [Character Class](#Character-Class) *Pre-production*
* [Repetitions](#Repetitions) *Pre-production*
* [Grouping and Capturing](#Grouping-and-Capturing) *Pre-production*
* [Backreferences](#Backreferences) *Pre-production*
* [Assertions](#Assertions) *Pre-production*
* [Applications](#Applications) *Pre-production*

## Introduction

* [Matching Specific String](#Matching-Specific-String)
* [Matching Anything But a Newline](#Matching-Anything-But-a-Newline)
* [Matching Digits & Non-Digit Characters](#Matching-Digits-\&-Non\-Digit-Characters)
* [Matching Whitespace & Non-Whitespace Character](#Matching-Whitespace-\&-Non\-Whitespace-Character)
* [Matching Word & Non-Word Character](#Matching-Word-\&-Non\-Word-Character)
* [Matching Start & End](#Matching-Start-\&-End)

### Matching Specific String

View on [Hackerrank](https://www.hackerrank.com/challenges/matching-specific-string)

#### Task
You have a test string *S*. Your task is to match the string `hackerrank`. This is case sensitive.

#### Solution
~~~python
# Use a regex made up of the given string.
# In Python, if your string is treated as a Regex if it has an "r" before the first quote.
Regex_Pattern = r"hackerrank"	
~~~

### Matching Anything But a Newline

View on [Hackerrank](https://www.hackerrank.com/challenges/matching-anything-but-new-line)

#### Task
You have a test string *S*.
 
Your task is to match the pattern `abc.def.ghi.jkx`

where each variable `a,b,c,d,e,f,g,h,i,j,k,x` can be any single character except the newline.

#### Solution
~~~python
# The caret, ^, matches the start of the line.
# And similarly, the dollar sign, $, matches the end of the line.
# A dot matches anything except for a newline character.
# And to match a dot we need to escape it using a backslash, like this: \.

# So the following regex matches:
# A line that has 3 non-newline characters, followed by a dot, 3 non-newline characters again,
# then a dot, 3 non-newline characters again a dot and then 3 non-newline characters and nothing else.
regex_pattern = r"^...\....\....\....$"
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
Regex_Pattern = r"\d\d\D\d\d\D\d\d\d\d"
~~~

### Matching Whitespace & Non-Whitespace Character

View on [Hackerrank](https://www.hackerrank.com/challenges/matching-whitespace-non-whitespace-character)

#### Task
You have a test string *S*. Your task is to match the pattern `XXxXXxXX`

Here, `x` denotes whitespace characters, and `X` denotes non-white space characters.

#### Solution
~~~python
# \s matches a whitespace character, one of [ \r \n \t \f ]
# \S matches a non-whitespace character.

# So the following regex matches a sequence of
# 2 Non-white space characters, a whitespace character,
# 2 Non-white space characters, a whitespace character,
# 2 Non-white space characters.
Regex_Pattern = r"\S\S\s\S\S\s\S\S"
~~~

### Matching Word & Non-Word Character

View on [Hackerrank](https://www.hackerrank.com/challenges/matching-word-non-word)

#### Task

You have a test string *S*. Your task is to match the pattern `xxxXxxxxxxxxxxXxxx`

Here `x` denotes any word character and `X` denotes any non-word character.

#### Solution
~~~python
# \w matches a word character, it could be a letter, a digit or an underscore.
# And \w matches a non-word character, anything that other than what \w matches.

# The following regex uses a trick though,
# While for instance \w matches 1 word character,
# \w{2} matches 2 word characters, and \w{n} matches
# n word characters.

# So the following pattern matches
# 3 word characters, 1 non-words, 10 word characters,
# 1 non-word character and finally 3 word characters.
Regex_Pattern = r"\w{3}\W\w{10}\W\w{3}"

# Alternatively
# Regex_Pattern = r"\w\w\w\W\w\w\w\w\w\w\w\w\w\w\W\w\w\w"
~~~

### Matching Start & End

View on [Hackerrank](https://www.hackerrank.com/challenges/matching-start-end)

#### Task

You have a test string *S*. Your task is to match the pattern `Xxxxx.`

Here, `x` denotes a word character, and `X` denotes a digit. 

*S* must start with a digit `X` and end with `.` symbol. 

*S* should be 6 characters long only.

#### Solution

~~~python
# ^ matches the line start.
# There is 1 digit following the line start.
# Which is followed by 4 word characters.
# Then there is a dot, which is escaped using a backslash.
# Then the regex matches the line end.
Regex_Pattern = r"^\d\w{4}\.$"
~~~

## Character Class

## Repetitions

## Grouping and Capturing

## Backreferences

## Assertions

## Applications

