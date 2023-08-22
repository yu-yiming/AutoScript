# AutoScript Compiler

**AutoScript** is a general-purpose, high-level scripting language that is statically typed, highly expressive, and can be compiled to **C++** and native binaries, or interpreted on its own custom VM with a bytecode compiler.

This repository contains the source code for the AutoScript compiler, which is mainly written is **C++**. In the following, we will call this compiler `asc` for short.

`asc` is a command-line tool that can be used to compile AutoScript source code to C++ or native binaries. It can also run AutoScript source code directly in the interpreter mode.


## Introduction to AutoScript Language

**AutoScript** features a simple and clean syntax, and is designed to be easy to learn and use. In **AutoSript**, every *name* is an *entity*, which is the smallest semantic unit that is evaluable, despite of its *genre* shown as follows:

- *object*: An object is a collection of *properties*, which are basically data fields.
- *functions*: A function is a sequence of *statements* that can be invoked by providing a list of *arguments*. On invocation, the system will run the statements in the function body, and optionally returns an entity as the result of the function call.
- *types*: A type is an *interface* of entity behaviors, which may or may not contain the memory layout information of the entity.
- *tags*: A tag is a more detailed label of an entity, which explicitly specifies all attributes of the entity, including its type, properties, and memory layouts.

Note that entities are first-class citizens in **AutoScript**, no matter what their genres are. This implies that when we don't really make a distinction among them when we are talking about general concepts, such as:

- *name*: A name is a string of characters that is used to identify an entity. A name that is bound to an entity is also called a *variable*.
- *value*: What an entity evaluates to, the true meaning of the entity.
- *type*: A static label that is determined at compile time, which specifies the behaviors of an entity.
- *tag*: A dynamic label that is determined at runtime, which specifies the attributes of an entity.
- *scope*: The scope of a name is the "place" where the name is defined and affects the visibility of the name. 
- ... and so on.

Thus, there is a unified model for all entities in **AutoScript**, and it's their attributes that make them different from each other.

This is not a specification of the **AutoScript** language, so I will not go into details about the syntax and semantics of the language. Snippets of code will be used, though, to illustrate the features of the language when necessary. If you are interested in the details, you can go to another folder `Specification`.

### Everything Is Entity

In **AutoScript**, everything is an entity, which means objects, functions and types share the same grammar for definition.
