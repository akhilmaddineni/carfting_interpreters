# Crafting Interpreters by Robert Nystrom

# Notes 

## 2. Map of territory 

Scanning - Takes in linear stream of characters and chunks then together into a series of words, In programming languages these are called tokens. 

Parsing - This is where our syntax gets a grammar. It takes the flat sequence of tokens and buils a tree structure that mirrors the nested nature of the grammar. 

Static Analysis - First bit of analysis that most languages do is called binding or resolution. For each identifier , we find out where that name is defined and wire them together. This is where scope comes into play. 

We need to store all this analysis somewhere , there are few places that we can store this . 
- Often it gets stored right back as attributes on the syntax tree itself. 
- We may store data in a lookup stable off to the side. They keys to this table are identifiers - names of vars and declarations . 
- Transform the tree into a entirely new data structure that more directly expresses the semantics of the code. Thats explained below. 

Intermediate representations - This lets you support multiple source languages and target platforms with less effort . Write one front end and each for each source language that produces the IR and then one backend for each target architecture. 

Optimization - Once we understand what the user program means , we are free to swap it out with a different program that has the same semantics but implements them more efficiently . 

Example of this is constant folding , if some expression always evaluates to the exact same value we can do the evaluation at compile time and replace the code for the expression with its result. 

Code generation - generating primite assembly like instructions a cpu runs

Virtual machine - If compiler produces byte code , work isnt done as there is no chip that runs the byte code, its our job to translate. This can be thought of as an intermediate representation. or we can write a virtual machine, a program that emulates hypothetical chip supporting your virtual architecture at run time. 

Run time - If we have compiled it to machine code , we directly tell os to 
