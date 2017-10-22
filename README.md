# Hackerrank Regular Expression Challenges

Solutions to Hackerrank's Regular Expression Challenges at [https://www.hackerrank.com/domains/regex/](https://www.hackerrank.com/domains/regex/)

**Last revision:** 22 October 2017

* [Introduction](#introduction)
* [Character Class](#character-class)
* [Repetitions](#repetitions) *Pre-production*
* [Grouping and Capturing](#grouping-and-capturing) *Pre-production*
* [Backreferences](#backreferences) *Pre-production*
* [Assertions](#assertions) *Pre-production*
* [Applications](#applications) *Pre-production*

## Introduction

* [Matching Specific String](#matching-specific-string)
* [Matching Anything But a Newline](#matching-anything-but-a-newline)
* [Matching Digits & Non-Digit Characters](#matching-digits--non-digit-characters)
* [Matching Whitespace & Non-Whitespace Character](#matching-whitespace--non-whitespace-character)
* [Matching Word & Non-Word Character](#matching-word--non-word-character)
* [Matching Start & End](#matching-start--end)

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
 
Your task is to match the pattern `abc.def.ghi.jkx`, and only exact strings that follow this pattern

where each variable `a,b,c,d,e,f,g,h,i,j,k,x` can be any single character except the newline.

#### Solution
~~~python
# Because we want to match exact patterns in the string, we'll have
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

# It's time to use a trick though now,
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
# Then there is a period, which is escaped with a backslash.
# Then the regex matches the line end.
Regex_Pattern = r"^\d\w{4}\.$"
~~~

## Character Class

* [Matching Specific Characters](#matching-specific-characters)
* [Excluding Specific Characters](#excluding-specific-characters)
* [Matching Character Ranges](#matching-character-ranges)

### Matching Specific Characters

View on [Hackerrank](https://www.hackerrank.com/challenges/matching-specific-characters)

#### Task

Your test string *S* will have the following requirements:

* *S* must be of length **6**
* First character: **1**, **2** or **3**
* Second character: **1**, **2** or **0**
* Third character: **x**, **s** or **0**
* Fourth character: **3**, **0**, **A** or **a**
* Fifth character: **x**, **s** or **u**
* Sixth character: **.** or **,**


#### Solution

~~~python
# ^ matches the line start.
# Any character from inside the square brackets can be matched with one character from the string.
# [123] can match 1, 2 or 3 in the string.
# Each group of characters inside the square brackets matches with one character in the string,
# There are 6 groups of characters surrounded by square brackets, each group to match one character from the string,
# Thus ensuring the length of the string is 6, since we have the line start and line end at the ends of our pattern.
Regex_Pattern = r'^[123][120][xs0][30Aa][xsu][\.,]$'
~~~

### Excluding Specific Characters

View on [Hackerrank](https://www.hackerrank.com/challenges/excluding-specific-characters)

#### Task

Your test string *S* will have the following requirements:

* *S* must be of length **6**
* First character should not be a digit (**1**, **2**, **3**, **4**, **5**, **6**, **7**, **8**, **9** or **0**).
* Second character should not be a lowercase vowel (**a**, **e**, **i**, **o** or **u**).
* Third character should not be **b**, **c**, **D** or **E**.
* Fourth character should not be a whitespace character (**\r**, **\n**, **\t**, **\f** or the space character).
* Fifth character should not be an uppercase vowel (**A**, **E**, **I**, **O** or **U**).
* Sixth character should not be a **.** or **,** symbol.

#### Solution

~~~python
# ^ matches the line start.
# A caret, ^, inside the square brackets match a character from the string as long as that character is not found in the square bracket from the pattern.
# [^aeiou] will match any character that is not a, e, i, o or u.
# [^\d] will match any non-digit character, like \D.
# Again there are 6 groups of characters surrounded by square brackets,
# Thus ensuring the length of the string is 6, since we have the line start and line end at the ends of our pattern.
Regex_Pattern = r'^[^\d][^aeiou][^bcDF][\S][^AEIOU][^\.\,]$'
~~~

### Matching Character Ranges

View on [Hackerrank](https://www.hackerrank.com/challenges/matching-range-of-characters)

#### Task

* The test string's length is greater than or equal to 5.
* The first character must be a lowercase English letter.
* The second character is a positive digit, cannot be zero.
* The third character must not be a lowercase English letter.
* The fourth character must not be an uppercase English letter.
* The fifth character must be an uppercase English letter.

#### Solution

~~~python
# ^ matches the line start. We need the line start because we're matching starting from the first character of the string.
# [a-z] will match any lowercase English letter from a to z both inclusive. [b-z] and [a-y] would match all lowercase English letters except for a and z respectively.
# [1-9] will match any digit except for zero.
# [^a-z] will match any character that is not a lowercase English letter.
# [^A-Z] will match any character that is not an uppercase English letter.
# [A-Z] will match any character that is an uppercase English letter.
# Note that for this pattern there is no line end, because only the first five characters of the string are relevant, the rest may be anything.
Regex_Pattern = r'^[a-z][1-9][^a-z][^A-Z][A-Z]'
~~~

## Repetitions

## Grouping and Capturing

## Backreferences

## Assertions

## Applications

## Revisions

1 January 2017 - Added [Introduction](#introduction)
22 October 2017 - Added [Character Class](#character-class)
