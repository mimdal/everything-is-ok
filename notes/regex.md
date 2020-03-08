Regular Expression
------------------
Some people, when confronted with a problem, think "I know, I'll use regular expressions." Now they have two problems.

```shell 
quantifiers:    
    *   →       0-1-2-...    
    +   →       1-2-3-...   
    ?   →       0-1                 
    {}  →       {2}, {2,}, {2,5} #  exactly 2, 2 or more, 2 up to 5  
   
character class:
    \d    →       any digit
    \w    →       any alphabet or digit
    \s    →       space | tab   |   newline
    .     →       any char, NOT good to use
    
    negative    →       \D, \W, \S
   
escape char = \ before specia chars ^ . [ $ ( ) * | + ? \ 

[] used for or and no need escape char
() ecactly chars inside it. CAPTURING GROUP, to disable ?: in parentheses. 
By placing part of a regular expression inside parentheses, 
you can group that part of the regular expression together. 
This allows you to apply a quantifier to the entire group

greedy and lazy
*   +   {}       : normal behaviour is greedy.
*?  +?  {}?      : to become lazy.

<div>text1</div><div>text2</div> 
<.+>
<.+?>

boundry: 
\b: Between two characters in the string,   
where one is a word character and the other is not a word character!
\B: negative, Damn it! boundry has negative pattern.

back reference:
to repeat a pattern. 
Backreferences match the same text as previously matched by a capturing group
\3

look ahead and behind = lookaround
lookaround actually matches characters, but then gives up the match, 
returning only the result not chars defind in lookaround. 
They do not consume characters in the string. they are called “assertions”.
d(?=r)      :   find d's after  them is r
(?<=r)d     :   find d's before them is r
Has Negative!! 
d(?!r)
(?<!r)d
``` 
    