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
    they provided the basis for a man named Stephen Kleen, for which his contributions to regex are immortalized with the Kleene star operator, to come by in 1956 and use their neural models and described them using algebra notation that he described as 'Regular Expressions'. 
        
    -Implementation-

        In 1968 a man named Ken Thompson, a mathematician and Unix pioneer, took the idea of regular expressions and implemented them into a basic text editor called 'ed'. He aimed to allow the user to do 
    advanced pattern matching in text files, which eventually saw ed evolving to have the functionality to search based on regular expressions and thus regexes entered the computing world. It continued to evolve and become more complex. 
        
    -Evolution-

        In 1986 a man by the name of Henry Spencer, who later wrote an implementation for Tcl called Advanced Regular Expressions, created a regex library that was the bases for the programming language 
    Perl.  in 1997 Philip Hazel developed Perl Compatible Regular Expressions(PCRE). Which brings us to today where we see regexes supported in text processing programs, programming languages, advanced text editors as well as other programs. Regex is a standard part of the library for many programming languages, like Java and Python, and is built into the syntax of others, like Perl and ECMAScript. In the 2010's several companies began to offer hardware implementations of PCRE compatible regex engines that are faster compared to CPU implementations. 

        
## Using_Regex

        To begin to understand how to use regex we must first recognize that everything is a character and we are making strings to match specific sequences of characters. Most patterns use ASCII but unicode 
    characters can also be used to match international text. However there are some metaCharacters used in regular expressions that can be used to match multiple character types, such as the \d which can be used to match and digit, alternatively a \D will match any non-digit. One thing to note is that with all the metaCharacters a lower case letter indicates that it will include all of a given type, while a capital character will exclude all characters of the given type. The operator \ is used to denote some of these metaCharacters, here is a quick list of characters that use the \ notation. 

    \d is used to match one digit from 0-9
    \D is used to match one non-digit character\
    \w is used to match one word character (ASCII letter, digit or underscore)
    \W is used to match one non-word character
    \s is used to match one white-space character
    \S is used to match one non-white space character
 
        Now looking at metaCharacters \w and \W. These metaCharacters are used to denote whitespace which include the space ( ), the tab (\t), the new line (\n) and the 
    return (\r).

        Next we'll introduce the dot "." which is a wildcard character and will match any single character. Also note that to search for the dot you must the \. escape to search for a single ".". Now if we 
    want to find specific strings we use the [] symbols and anything we put in there will be used to determine our matches. So if we have a look at this list of words and want to only match the first two words we would take the [] and put in the words containing the letters we want to find. for example [fr]un will iterate through the list and first look for an f or r (so it will focus the words fun, run, ran and fan) then it will check the following characters to match the rest of the string, which in this case are fun and run. Keep in mind that the search for characters is case sensitive.

```md
    fun
    run
    pun
    sun
    ran
    fan
    pan
```


        There are many ways to write regular expressions to accomplish the same goal. Let's look the character ^, this is used to indicate that the following characters will be used as what NOT to look for
    in expression. For example, using the same list, if we were to create the expression [^ps]un, the regex will iterate through the list and look for the first character that ISN"T a p or an s (in this case fun, run, ran and fan) then take the results and look for words that have un as following characters. So our regex will again return the words fun and run. 

        Next we'll look at the "-" character. This character is used within the [] to denote a range. As an example for this we'll look at the following list.  If we wanted to return the names in this list 
    (as they are proper nouns and thus capitalized) we could write the expression [A-Z], or alternatively [^a-z], this would create an inclusive list of characters that range from A all the way to Z. So our expression will look at this list and find the first time a letter appears that is a capitol letter, so our regex would return Ana, Bob and Jim and would exclude ball and cube as they do not contain a qualifying letter.
```md
    Ana
    Bob
    ball
    cube
    Jim
```
        Now lets move onto Quantifier. A quantifier is used in conjunction with a basic expression to find the pattern a determined amount of times. Here is a list of quantifiers

    +       Used to find one more (also called the Kleene Plus)
    {2}     Used to find exactly 2 times (this can be any number(X) and will attempt to find the pattern (X) amount of times)
    {2,5}   Used to find between 2 and five times (this can be any two numbers(X)(Y) and will attempt to find the patter, between (X) and (Y) times)
    {3,}    Used to find 3 or more times (this can be any number(X) and will attempt to find the pattern (X) or more times)
    *       Used to find zero or more times (also called the Kleene Star)
    ?       Used to find one or none times

        We can use these quantifiers to further help refine our searches. Lets look at the following list. We want to find the words that contain two "l"s. So we would write the expression l{2}. This will 
    look through the list first and return all words with one l, then with the quantifier attached it will look for that pattern the amount of time defined following our initial query, in this example the {2} is used to search for the l 2 times, so it returns (ba)ll, (ma)ll, (ca)ll, (ce)ll and ll(ama). Note the letters in the () will not be returned
```m
    ball
    mall
    call
    bail
    sail
    llama
    cell
```
        Let's look at Kleene characters (+,*) and see how we could use those to query the list. If we wanted to exclude cell and llama from the list we would use the Kleene characters to further refine our 
    expression. Given the expression a+l+ we see that it searches the list for at one a which returns all words except cell, then it searches the list for at least one iteration of an l following an "a" which will then return (b)all, (m)all and (c)all. Now about the * character, if we used the expression a*+[e-i]+l{2} this would return all words on the list except cell. First the expression would search for all the words that have 0 or more a's (which is all the words) and then search for the words that have an e through i (e,f,g,h,i) at least one time, narrowing this list down to bail, sail and cell. Then lastly it will search the words that have 2 "l"s in a row, so our list is then further refined to return {c}ell.

        The last quantifier we are gonna look at is the "?". This is used to denote and optional character. Returning to our previous list if we wrote the expression a?l{2} we would get (b)all, (m)all, (c)
    all ll(ama) and (ce)ll. Note that if you wanted to search for a single "?" you would have to type it out as "\?" to have it be matched as a character and not be used as a metaCharacter.

        Now let's say we only wanted to return the ball, mall and call and not get the llama using the l{2} expression. To achieve that we can use the ^ and $ metaCharacters. While the ^ is used to denote 
    NOT while inside [] putting at the beginning of the expression means that it will search for the patter at the beginning of the words, alternatively using the $ at the end of the expression means we look at the end of the word to see if the pattern appears there. 

        Onto our next topic let's talk about capture groups. A capture group allows us to extract layers of information by nesting groups. For example, given the following list. If we wanted to capture just 
    the day but also have another expression to capture the entire date we would use a nested capture group. (\w+ (\w+ \d+.)). Looking at this expression we can see that the first part is capturing any word then the space, that will be our first capture group, then we have a second expression nested inside the first one that will take everything from the first group and add to it. So the nested expression is taking the first word and also checking for another word followed by a space and one or more digits and the '.' will take the suffix to the number.

```m
    Monday Jan 1st
    Thursday Aug 9th
    Wednesday Sep 17th

```
        Now our last topic will be the '|' metaCharacter. This character is a logical or operator, it allows us to define a regex with multiple parameters and have it return either/or of the defined 
    parameters. So lets look at an example. Given the previous list if we wanted to find all days that were either Monday or Wednesday we would be able to do this with the '|' metaCharacter. Our Expression for this one is pretty simple, we make two capture groups and put the '|' between them (Monday)|(Wednesday) this will check the list and look for either the Monday or Wednesday words and return them.   

        Hopefully with this new found knowledge you are able to put together more complex regular expression as you can see once broken down into their parts they are simpler to understand. There are many 
    more ways to write regular expression with many more metaCharacters to help filter. I have provided a link to a website I found that has very in depth explanations of all things regex. Thank you for checking out my tutorial and I hope you are no longer intimidated by the perceived complexity of regular expressions




## Link
This is a link to my github page
(https://github.com/Jgarnaat/regex-express)

here is a helpful website filled will all things RegEx
https://www.rexegg.com/


