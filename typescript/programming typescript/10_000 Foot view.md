# The Compiler

programs are files that contain a bunch of text written by you, the programmer. 

That text is parsed by a special program called a compiler, which transforms it into an __abstract syntax tree__ (AST), a data structure that ignores things like whitespace, comments, and where you stand on the tabs versus spaces debate. 

The compiler then converts that AST to a lower-level representation called bytecode.

You can feed that bytecode into another program called a runtime to evaluate it and get a result.

Once again, the steps are:
1. Program is parsed into an AST.
2. AST is compiled to bytecode.
3. Bytecode is evaluated by the runtime.

Where TypeScript is special is that instead of compiling straight to bytecode, Type‐Script compiles to… JavaScript code! You then run that JavaScript code like you normally would—in your browser, or with `NodeJS`.


# JavaScript Engines
**JavaScript compilers and runtimes** are typically combined into a single program called an **engine**.

As a programmer, this engine is what you normally interact with.

Examples include:
- **`V8`** — powers Node.js, Chrome, and Opera
- **`SpiderMonkey`** — used by Firefox
- **`JavaScriptCore` (`JSCore`)** — used by Safari
- **`Chakra`** — used by Edge

This architecture is what gives JavaScript the appearance of being an **interpreted language**, even though modern engines perform sophisticated compilation behind the scenes.


# Typechecker
A special program that verifies that your code is `typesafe`.
![[Pasted image 20260127115118.png]]
Steps 1–3 are done by TSC, and steps 4–6 are done by the JavaScript runtime that lives in your browser, `NodeJS`, or whatever JavaScript engine you’re using.

## Type system
A set of rules that a typechecker uses to assign types to your
program.

There are generally two kinds of type systems: type systems in which you have to tell the compiler what type everything is with explicit syntax, and type systems that infer the types of things for you automatically.

TypeScript is inspired by both kinds of type systems: you can explicitly annotate your types, or you can let TypeScript infer most of them for you.

To explicitly signal to TypeScript what your types are, use annotations. Annotations take the form `value: type`
```ts
let a: number = 1                 // a is a number
let b: string = 'hello'           // b is a string
let c: boolean[] = [true, false]  // c is an array of booleans
```

And if you want TypeScript to infer your types for you:
```ts
let a = 1               // a is a number
let b = 'hello'         // b is a string
let c = [true, false]   // c is an array of booleans
```

> In general, it is good style to let TypeScript infer as many types as it can for you, keeping explicitly typed code to a minimum.


Comparing JavaScript’s and TypeScript’s type systems:

| **Type system feature**            | **JavaScript**      | **TypeScript**           |
| ---------------------------------- | ------------------- | ------------------------ |
| How are types bound?               | Dynamically         | Statically               |
| Are types automatically converted? | Yes                 | No (mostly)              |
| When are types checked?            | At runtime          | At compile time          |
| When are errors surfaced?          | At runtime (mostly) | At compile time (mostly) |


Let’s walk through the specific example of how JavaScript evaluates `3 + [1]`:
1. JavaScript notices that `3` is a number and `[1]` is an array.
2. Because we’re using `+`, it assumes we want to concatenate the two.
3. It implicitly converts `3` to a string, yielding `"3"`.
4. It implicitly converts `[1]` to a string, yielding `"1"`.
5. It concatenates the results, yielding `"31"`.
When you run that same Java‐ Script code through TSC, you’ll get an error:

