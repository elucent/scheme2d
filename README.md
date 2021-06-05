# Introducing ***Scheme 2-D***

Are you ever bored by other Lisp dialects? Do s-expressions feel flat and lifeless to you? Have you ever been worried you're not getting your money's worth out of the space bar on your keyboard?

Have we got the perfect programming language for you!

In ordinary Scheme, you'd write parenthesized lists of terms, which is _so_ last decade! 🤮
```scheme
(define (factorial x)       ; yuck!
    (if (= x 0) 1               ; gross!
        (* x (factorial (- x 1))))) ; homoiconic???
```

With ***Scheme 2-D***, you can take your Scheme programs to the next level, with the power of the *second dimension*! 😎

```scheme     
        ^   ^           
<define f   i>          beautiful!
        a   f               so aesthetic!
        c                       look at those angles!
        t  <= x 0>              
        o                        
        r   1       
        i       ^
        a  <* x f>
        l   v   a
                c
        x       t
        v       o
                r
                i
                a
                l

               <- x 1>
                v
```

Gain full control over your syntax tree, and release your full 10xer potential by ~~buying~~ downloading ***Scheme 2-D*** for ~~just $19.95 + S&H~~ free today!

## Installation

Scheme 2-D is based on [Chez Scheme](https://cisco.github.io/ChezScheme/). To install Scheme 2-D, first install Chez Scheme, then clone this GitHub repository. 

The `scheme2d` script at the top level of this project contains the entire compiler, with no local dependencies. So, as long as you have the Chez Scheme `scheme-script` utility present in your `/bin`, you may freely move `scheme2d` to any other directory.

## How To Use

```
scheme2d <filename>
```
Simply run `scheme2d` on the Scheme 2-D source file you wish to run, and it will interpret it.

## How It Works

Scheme 2-D is an alternative two-dimensional syntax for Chez Scheme. Horizontal parentheses have been replaced with angle brackets (`<` and `>`), and vertical "parentheses" have been introduced with the tokens `^` and `v`.

Top-level expressions are parsed horizontally, but must start at column 0: 

```scheme
12   <--- an integer constant
"hello"   <--- a string constant
'apple   <--- a quoted symbol
<+ 1 2 3>   <--- adding 1, 2, and 3 (equivalent to (+ 1 2 3))

    <* 2 2>   <--- ignored, since it doesn't start at column 0!
```

Lists within horizontal lists must be written vertically! A vertical list can be started at any position within a horizontal list, by placing a "top parenthese" (caret, `^`) at that column on the line above. The list extends down from there until it reaches a "bottom parenthese" (lowercase V, `v`): 

```scheme
     ^
<+ 1 + 4>   <--- equivalent to (+ 1 (+ 2 3) 4)

     2

     3
     v
```

Lists within vertical lists need to be written horizontally again, started by a left angle bracket (`<`) immediately to the left of a position in a vertical list:

```scheme
     ^
<+ 1 +>   <--- equivalent to (+ 1 (+ 2 (+ 3 (+ 4 5))))
     
     2   
         ^
    <+ 3 +>
         
         4

         5
         v
```

Whitespace acts as a separator in all lists, but is ignored beyond that - so adding extra spaces to organize terms is totally okay! 

As a consequence of this syntax, all text outside of bracketed lists is ignored, and can be used for comments.

## FAQ

### *Why would you write this?*

I drank like four cups of coffee at 11:53 p.m.

### *Why would I write anything using this?*

If the infomercial pitch didn't already sell you on it, I doubt anything else will.

### *I wrote some obviously wrong code and didn't get an error. Isn't that a problem?*

Unlike other stickler compilers, the Scheme 2-D compiler forgoes annoying things like "syntax errors", "formal grammars", and "having a real lexer or parser". This just means it does its best to make your code work! Don't worry about it, and keep that development velocity high!

### *I'm having an issue with strings/characters/literally-any-symbol-with-angle-brackets?*

These aren't covered by the warranty.

### *I'm sold! This is clearly the future of programming. How do I contribute?*

If you have any interest in helping to improve the compiler and have way too much free time, we do accept pull requests! We also accept new examples!

### *How do I support continued development of Scheme 2-D?*

Please follow me on [Twitter](https://twitter.com/elucentdev) and give this project lots of GitHub Stars to provide me with moral support.