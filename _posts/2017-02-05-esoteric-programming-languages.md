---
published: true
---
# An Intro to Esoteric Programming Languages

View my presentation slides [here](https://docs.google.com/presentation/d/1eAWIpAgcbfi_n0FTOKv_frM1TaZIkxE8Nv4UETx8B1g/edit?usp=sharing).

## Definition

> An esoteric programming language, or esolang, is a computer programming language designed to experiment with weird ideas, to be hard to program in, or as a joke, rather than for practical use.

Source: <https://esolangs.org/wiki/Esoteric_programming_language>

## Why, though?

I think coders enjoy creating and using esoteric languages because they enjoy one of these aspects:

1. Minimalism, or how can I use as little number of pixels as possible to write a program
2. New concepts
3. Weirdness, like using chicken as the only 'character' of the language
4. Fun, or amusing pastimes when you don't have to code for work

## Several interesting languages

### Brainf*
- Invented in 1993 by Urban Müller
- Information may be hard to find
- Usable characters: > < + - . , [ ]
- Operates on an array of memory cells
- Uses a single pointer

### Prelude/Fugue

![Fugue code sheet music image](https://i.imgsafe.org/7b7a9c23e3.png=400x)

This fugue code is the visual representation of the Prelude language. The intervals between notes as well as the lines represent these characters of Prelude: 

- **#** - Unison
- **^** - ascending second
- **v** - descending second
- **+** - ascending fourth or tritone
- **-** - descending fourth or tritone
- **(** - ascending fifth
- **)** - descending fifth
- **!** - ascending sixth
- **?** - descending sixth

## JSF*

This pseudo-language is especially interesting to me. JSF was developed by Martin Kleppe and restricts a coder to using 6 characters while programming JavaScript:
- **+**
- **!**
- **(**
- **)**
- **[**
- **]**

The fun part is that this code runs in the browser or Node (because they interpret JavaScript), providing a very easy 'workflow' when attempting to code in the language.

#### Coding in JSF

```javascript
// The fun part of JSF in my opinion is creating strings from the allowed characters
// Here are some useful patterns to get used to using:

// False is the base of JSF code:
// It's interesting that using a NOT operator on an array evaluates to false...
![]

// True:
!![]

// The two expressions above are JavaScript types... so now we convert them to strings
![]+[] === 'false';
!![]+[] === 'true';
// Adding an array converts a type into a string of that type? Almost like the toString() method...

// Accessing chars in the previous strings is easy! Just think about accessing indexes in strings...
(![]+[])[+!![]] === 'a'
// Wrapping the first part in parentheses so the interpreter knows what to handle first
// +!![] => adding a '+' before true results in 1

// Getting the string 'hrr21'
(+(+!+[]+[+[]]+[+!+[]]))[(!![]+[])[+[]]+(!![]+[][(![]+[])[+[]]+([![]]+[][[]])[+!+[]+[+[]]]+(![]+[])[!+[]+!+[]]+(!![]+[])[+[]]+(!![]+[])[!+[]+!+[]+!+[]]+(!![]+[])[+!+[]]])[+!+[]+[+[]]]+(+![]+([]+[])[([][(![]+[])[+[]]+([![]]+[][[]])[+!+[]+[+[]]]+(![]+[])[!+[]+!+[]]+(!![]+[])[+[]]+(!![]+[])[!+[]+!+[]+!+[]]+(!![]+[])[+!+[]]]+[])[!+[]+!+[]+!+[]]+(!![]+[][(![]+[])[+[]]+([![]]+[][[]])[+!+[]+[+[]]]+(![]+[])[!+[]+!+[]]+(!![]+[])[+[]]+(!![]+[])[!+[]+!+[]+!+[]]+(!![]+[])[+!+[]]])[+!+[]+[+[]]]+([][[]]+[])[+!+[]]+(![]+[])[!+[]+!+[]+!+[]]+(!![]+[])[+[]]+(!![]+[])[+!+[]]+([][[]]+[])[+[]]+([][(![]+[])[+[]]+([![]]+[][[]])[+!+[]+[+[]]]+(![]+[])[!+[]+!+[]]+(!![]+[])[+[]]+(!![]+[])[!+[]+!+[]+!+[]]+(!![]+[])[+!+[]]]+[])[!+[]+!+[]+!+[]]+(!![]+[])[+[]]+(!![]+[][(![]+[])[+[]]+([![]]+[][[]])[+!+[]+[+[]]]+(![]+[])[!+[]+!+[]]+(!![]+[])[+[]]+(!![]+[])[!+[]+!+[]+!+[]]+(!![]+[])[+!+[]]])[+!+[]+[+[]]]+(!![]+[])[+!+[]]])[+!+[]+[+[]]]+(!![]+[])[+[]]+(!![]+[])[+!+[]]+([![]]+[][[]])[+!+[]+[+[]]]+([][[]]+[])[+!+[]]+(+![]+[![]]+([]+[])[([][(![]+[])[+[]]+([![]]+[][[]])[+!+[]+[+[]]]+(![]+[])[!+[]+!+[]]+(!![]+[])[+[]]+(!![]+[])[!+[]+!+[]+!+[]]+(!![]+[])[+!+[]]]+[])[!+[]+!+[]+!+[]]+(!![]+[][(![]+[])[+[]]+([![]]+[][[]])[+!+[]+[+[]]]+(![]+[])[!+[]+!+[]]+(!![]+[])[+[]]+(!![]+[])[!+[]+!+[]+!+[]]+(!![]+[])[+!+[]]])[+!+[]+[+[]]]+([][[]]+[])[+!+[]]+(![]+[])[!+[]+!+[]+!+[]]+(!![]+[])[+[]]+(!![]+[])[+!+[]]+([][[]]+[])[+[]]+([][(![]+[])[+[]]+([![]]+[][[]])[+!+[]+[+[]]]+(![]+[])[!+[]+!+[]]+(!![]+[])[+[]]+(!![]+[])[!+[]+!+[]+!+[]]+(!![]+[])[+!+[]]]+[])[!+[]+!+[]+!+[]]+(!![]+[])[+[]]+(!![]+[][(![]+[])[+[]]+([![]]+[][[]])[+!+[]+[+[]]]+(![]+[])[!+[]+!+[]]+(!![]+[])[+[]]+(!![]+[])[!+[]+!+[]+!+[]]+(!![]+[])[+!+[]]])[+!+[]+[+[]]]+(!![]+[])[+!+[]]])[!+[]+!+[]+[+[]]]](!+[]+!+[]+[+!+[]])[+!+[]]+(!![]+[])[+!![]]+(!![]+[])[+!![]]+(+!![]+!![])+(+!![]) === 'hrr21';
```

### Takeaway

Although no 'real' programming is done in esoteric programming languages, it's quite fun and a change of pace to experiment with them!
