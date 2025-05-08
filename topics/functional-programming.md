# What is functional programming?

It's difficult to define functional programming in a way that satisfies everyone, because not everyone always agrees on what it is exactly.

With my own words, I'd say it's a programming paradigm that make use of only two elements: functions and values. Each function is pure, which means that, given an input X, it'll always return the output Y. Each value is immutable, which means that everytime a value is passed to a (pure) function, it won't be modified by the function. It also means that, if you want to add 1 to every element of an array, a brand new array will be returned and the array provided as input won't be modified. Why all of that? Well, there are several benefits :

- Predictability: if the business-critic part of the program is split in many pure functions and that every value living in the memory is immutable, the behavior of that code should be completely predictable, therefore less buggy and, when something wrong happens, easier to debug (because we can reproduce exactly what happened)

- Reusability: a function can be reused anywhere it's needed (therefore no need for `utils.py|js|cpp|whatever` file), and even combined with other functions to create a new one that combines the features of both, this is composability. In a way, we can see functions as values as well.

## Resources

- An introduction to functional programming, by the creator of [fp-ts](https://github.com/gcanti/fp-ts) (in Italian, but there's an English version): <https://github.com/gcanti/functional-programming>

## Write functional code

### Specific languages

There are several languages specialized in that matter, such as <https://elixir-lang.org/> or <https://www.haskell.org/>.

### Specific libraries

| Language   | Name        | Repository                                 |
| ---------- | ----------- | ------------------------------------------ |
| TypeScript | fp-ts       | <https://github.com/gcanti/fp-ts>          |
| TypeScript | effect      | <https://github.com/Effect-TS/effect>      |
| TypeScript | neverthrow  | <https://github.com/supermacro/neverthrow> |
| Python     | returns     | <https://github.com/dry-python/returns>    |

Note that neverthrow is specialized in error handling and success/failure modeling, whereas the others are broader and cover more uses cases, including error handling as well.

## Railway oriented programming

I'll define a "program's operation" as a sequence of instructions in a program that can succeed or fail. In functional programming, this is typically a pure-function call.

Railway oriented programming is a functional programming offering a way of handling program's operations that can succeed or fail and is based on the image of a railway track that can divide in two directions to describe the program's sequence. Each operation potentially\* lead to two possible paths:

\*potentially: a program's operation doesn't need to have an error path, for example a function that takes a number and multiply it by 3.14, well it just does the multiplication and that's it

- one for successful outcomes
- one for errors

The programmer is therefore forced to handly the error cases, or must explicitely allow the error to crash the program. This approch is also very graat for type-safety because all the possible errors are part of the type system. Anyways it looks interesting, so here are some resources to start with.

### Resources

| Type     | Title                                                                                                                 | Author/Channel                                                 |
| -------- | --------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------- |
| Video    | [Railway oriented programming: Error handling in functional languages by Scott Wlaschin](https://vimeo.com/113707214) | [NDC Conferences](https://vimeo.com/ndcconferences)            |
| Playlist | [Railway-Oriented Programming](https://www.youtube.com/playlist?list=PLYpjLpq5ZDGs4XtFbelLZl-bwPyNyjJSI)              | [Milan Jovanović](https://www.youtube.com/@MilanJovanovicTech) |
