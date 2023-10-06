<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
**Table of Contents**  *generated with [DocToc](https://github.com/thlorenz/doctoc)*

- [How To Survive Your Project's First 100,000 Lines](#how-to-survive-your-projects-first-100000-lines)
  - [If you think you're using enough assertions, you're wrong](#if-you-think-youre-using-enough-assertions-youre-wrong)
  - [Lean on the type system](#lean-on-the-type-system)
  - [A better way to comment](#a-better-way-to-comment)
  - [Avoid nondeterminism](#avoid-nondeterminism)
  - [...except you can't really avoid nondeterminism, so how do we solve it?](#except-you-cant-really-avoid-nondeterminism-so-how-do-we-solve-it)
  - [Stay on top of your testing](#stay-on-top-of-your-testing)
    - [Prefer end-to-end tests](#prefer-end-to-end-tests)
    - [Know when to add a test](#know-when-to-add-a-test)
  - [Prioritize development velocity](#prioritize-development-velocity)
  - [Bonus: Sanity Checking](#bonus-sanity-checking)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

# How To Survive Your Project's First 100,000 Lines

Font: <https://verdagon.dev/blog/first-100k-lines>

## If you think you're using enough assertions, you're wrong

Rule of thumb: Every time you think something is true about your data, and it's not ensured by the type system, **add an assertion that checks it**.

Don't just occasionally use them, drench your code in them. When your code so much as sneezes, they should shake off like sand after the beach. This is the way.

## Lean on the type system

When you find yourself accidentally passing an ID string argument into a first name string parameter, it's a hint that you shouldn't be passing around strings, and perhaps you should wrap them in different kinds of structs. This is sometimes called the New Type pattern.

## A better way to comment

...

However, comments can become out-of-date, and you might not be lucky enough to stumble across the right comment before you embark on a refactoring adventure.

For this reason, we also scatter clues around, like the below.

## Avoid nondeterminism

Have you ever had a bug that you could only reproduce one out of every ten tries? What an adventure!

And then there's the bugs that you might only reproduce every hundredth try. A harrowing endeavor. You try and you try, and eventually give up and close the bug report as "Cannot Reproduce".

If non-determinism creeps into your program, you'll be testing your application, find a bug, and then never be able to reproduce it. Avoid it when you can!

## ...except you can't really avoid nondeterminism, so how do we solve it?

???

## Stay on top of your testing

### Prefer end-to-end tests

### Know when to add a test

## Prioritize development velocity

- Use a language with good compile speeds.
- Use a memory-safe language
- Prioritize looser coupling. Find a way to harness object-oriented benefits:
  - Dependency injection (the pattern, not the kind of framework)
  - Encapsulation
  - Polymorphism
- Use a flexible language

## Bonus: Sanity Checking

After you add your normal assertions, also consider periodically calling a sanityCheck function
