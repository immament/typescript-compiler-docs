typescript-compiler-docs
========================

A work in progress documentation of how the TypeScript compiler works 

# Useful PRs with Insight
## Missing try block with a catch / finally 
https://github.com/Microsoft/TypeScript/pull/262/files
**Parser** : Gives information about the `isStatement` function. If that function returns then `parseStatement` will get called which must return *some* type of `Statement`. In this case we are going to return a `TryStatement` from a utility `parseCatchOrFinallyBlocksMissingTryStatement` function. These utility (`parse-`) functions apparently prepare the AST for the emitter by creating (`createNode` function) and finishing Nodes (`finishNode` function).

## Parsing logic for Object Literals 
https://github.com/Microsoft/TypeScript/pull/273/files
**Parser** : `parseObjectLiteral` is used to parse object literals. `parseDelimitedList` is used to parse the properties of object literals.

## Fast compilation on watch
https://github.com/Microsoft/TypeScript/pull/324
Basically create a copy of the `program` and update it based on changes. Mostly inside `tc.ts` the `recompile` function.

## Initial port of the language service: 
https://github.com/Microsoft/TypeScript/pull/303

# Tutorials 
**hacking it to add a documentation emitter** http://www.codeproject.com/Articles/635280/TypeScript-Compiler-Documentation-Output 
