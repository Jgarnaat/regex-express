# <Regex_Express>

## Description

Welcome to my tutorial on how to use Regex. In this tutorial we are gonna look at what regex is, where it came from and how to use it.
The tutorial has been broken down into three parts. First we will look at what a regex is and a basic overview of its functionality and how to use it.
Second we'll take a quick dive into the history of Regex, I feel like it's important to understand where it came from to get an idea as to what exactly it 
was created for. Last we'll delve into basic use cases for implementing the regex into our code. Note that while regex syntax varies slightly between programming languages we'll be focusing on Javascript for our regex tutorial.



## Table of Contents (Optional)

- [What is Regex?](#what_is_regex?)
- [History of Regex](#history_of_regex)
- [Using regex](#using_regex)
- [About the author](#About_the_author)
- [link](#link)

## What_is_Regex?

    Regex (or Regular Expression) is a text string we use to describe patterns we can use for four main tasks. first it can be used to find text within a larger body of text,
  second we can use the string to validate that a given string conforms to the desired format, third we can use regex to find and replace text or insert text into a matched 
  position withing a field, and last we can use regex to split strings.

    The process of handling the regex functionality is handled by a regex engine, most text editors have a regex engine as well as most programming languages.  
  Before we dive into regex it's important to understand some basics about regex. I have compiled a short list as a cheat sheet to reference some of the syntax used in our regular expressions.
  These might be unfamiliar at first but we'll break these down later so their use becomes apparent.


    abc…	    Letters
    123…	    Digits
    \d	        Any Digit
    \D	        Any Non-digit character
    .	        Any Character
    \.	        Period
    [abc]	    Only a, b, or c
    [^abc]	    Not a, b, nor c
    [a-z]	    Characters a to z
    [0-9]	    Numbers 0 to 9
    \w	        Any Alphanumeric character
    \W	        Any Non-alphanumeric character
    {m}	        m Repetitions
    {m,n}	    m to n Repetitions
    *	        Zero or more repetitions
    +	        One or more repetitions
    ?	        Optional character
    \s	        Any Whitespace
    \S	        Any Non-whitespace character
    ^…$	        Starts and ends
    (…)	        Capture Group
    (a(bc))	    Capture Sub-group
    (.*)	    Capture all
    (abc|def)	Matches abc or def


## History_of_regex

    -Inception-

        In 1943 two scientist, a neuroscientist by the name of Warren S. McCulloch and a Logician named Walter Pitts, began developing models describing how the human nervous system works. Their research was 
    primarily focused on understanding the brain and how it could produce complex patterns using simple cells that are bound together. While these two individuals were not directly responsible for regex 
    they provided the basis for a man named Stephen Kleen, for which his contributions to regex are immortalized with the kleene star operator, to come by in 1956 and use their neural models and described them using algebra notation that he described as 'Regular Expressions'. 
        
    -Implementation-

        In 1968 a man named Ken Thompson, a mathematician and Unix pioneer, took the idea of regular expressions and implemented them into a basic text editor called 'ed'. He aimed to allow the user to do 
    advanced pattern matching in text files, which eventually saw ed evolving to have the functionality to search based on regular expressions and thus regexes entered the computing world. It continued to evolve and become more complex. 
        
    -Evolution-

        In 1986 a man by the name of Henry Spencer, who later wrote an implementation for Tcl called Advanced Regular Expressions, created a regex library that was the bases for the programming language 
    Perl.  in 1997 Philip Hazel developed Perl Compatible Regular Expressions(PCRE). Which brings us to today where we see regexes supported in text processing programs, programming languages, advanced text editors as well as other programs. Regex is a standard part of the library for many programming languages, like Java and Python, and is built into the syntax of others, like Perl and ECMAScript. In the 2010's several companies began to offer hardware implementations of PCRE compatible regex engines that are faster compared to CPU implementations. 

        
## Using_Regex

        To begin to understand how to use regex we must first recognize that everything is a character and we are making strings to match specific sequences of characters. Most patterns use ASCII but unicode 
    characters can also be used to match international text. However there are some metacharacters used in regular expressions that can be used to match multiple character types, such as the \d which can be used to match and digit, alternatively a \D will match any non-digit. One thing to note is that with all the metacharacters a lower case letter indicates that it will include all of a given type, while a capital character will exclude all characters of the given type. The operator \ is used to denote some of these metacharacters, here is a quick list of characters that use the \ notation.

    \d is used to match one digit from 0-9
    \D is used to match one non-digit character\
    \w is used to match one word character (ASCII letter, digit or underscore)
    \W is used to match one non-word character
    \s is used to match one white-space character
    \S is used to match one non-white space character

        Next we'll introduce the dot "." which is a wildcard character and will match any single character. Also note that to search for the dot you must the \. escape to search for a single ".". Now if we 
    want to find specific strings we use the [] symbols and anything we put in there will be used to determine our matches. So if we have a look at this list of words and want to only match the first two words we would take the [] and put in the words containing the letters we want to find. ex. < mark> [fr]un </mark> will iterate through the list and first look for an f or r (so it will focus the words fun, run, ran and fan) then it will check the following characters to match the rest of the string, which in this case are fun and run.

    fun
    run
    pun
    sun
    ran
    fan

        There are many ways to write regular expressions to accomplish the same goal. For example, using the same list, if we were 

## Link

![badmath](https://img.shields.io/github/languages/top/lernantino/badmath)

Badges aren't necessary, per se, but they demonstrate street cred. Badges let other developers know that you know what you're doing. Check out the badges hosted by [shields.io](https://shields.io/). You may not understand what they all represent now, but you will in time.
