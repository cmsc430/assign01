# Language: Racket

## When

Racket, which was originally known as PLT Scheme, was first developed
in the mid-1990s by the programming language research group led by
Matthias Felleisen at Rice University.  It was first developed by
Felleisen's graduate students: Matthew Flatt, Robby Findler, Shriram
Krishnamurthi, and Cormac Flannagan.  It is now developed by a large
[team](https://racket-lang.org/team.html) of researchers, volunteers,
and practioners.

## Why

Originally it was developed as a pedagogical programming environment
for teaching introductory university-level programming courses.  It is
still used for this purpose, but has also served as a major research
platform for programming language research and has been used in
several notable industrial projects.  It is unique in its
metaprogramming facilities, making it a plaform suitable for langauge
engineering and prototyping.

## Examples

Here is a simple example of a Racket function that computes the
factorial of a given natural number:

```racket
#lang racket
(define (fact n)
  (cond [(zero? 0) 1]
        [else (* n (fact (sub1 n)))]))
```

One of the unique aspects of Racket is that the programming language
of a module (each file is a module) can itself be programmed and
changed.  Here is a module written in Typed Racket, a statically typed
sister-language of Racket:

```racket
#lang typed/racket
(: fact (-> Natural Natural))
(define (fact n)
  (cond [(zero? 0) 1]
        [else (* n (fact (sub1 n)))]))
```

You can even change the concrete syntax and semantics of a module.
Here is a module written in Racket's Datalog sub-language, a
Prolog-like logic-programming language:

```racket
#lang datalog

ancestor(A, B) :- parent(A, B).
ancestor(A, B) :-
  parent(A, C), ancestor(C, B).
parent(john, douglas).
parent(bob, john).
ancestor(A, B)?
```

## Uses today

Racket is still in use today.  It is used at a number of universities
for teaching.  Hacker News is written in Racket.  Naughty Dog uses
Racket as their in-house scripting language.  There are many others.
