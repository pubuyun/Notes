---
title: Definitions
slug: definitions
cover: ""
categories:
  - Computer Science
tags:
  - G1
halo:
  site: https://www.pu6uyun.net
  name: 4cc9a709-e6fb-4950-8fb4-39d90665bf16
  publish: true
---
## Datatype
### Constant
**constant** is a **named piece of memory** where the value cannot be changed while a **program runs**
### Variable
**a named storage unit** with a value that **can be modified** throughout the **program's execution**

## Control Structures

### Sequence
The statements are executed one by one in the order they are written.
### Selection
Selection is **the process of making a decision**. The result of the decision decides which path the program executes.
### Iteration
Iteration is the process of repeating a set of instructions until a specific condition is met.
Including:
- Count-controlled loops
- Precondition loops
- Postcondition loops


### Sequence

- Question: What does the term "sequence" mean in programming, and why is it important for structuring code?

- Answer: Sequence in programming means the order in which instructions are executed. In a sequence, each step is executed one after the other, in the same order they appear. It's important because it ensures that the program performs tasks in the correct order, which is essential for achieving the desired result.

### Iteration

- Question: How would you define iteration in the context of programming?

- Answer: Iteration refers to the repetition of a set of instructions a specific number of times or until a condition is met. In CIE IGCSE, this is typically done using loops like FOR, WHILE, or REPEAT-UNTIL. It is useful for tasks that need to be repeated, such as counting or processing items in a list.

### Selection

- Question: What does "selection" refer to in programming, and how does it affect program flow?

- Answer: Selection is a decision-making process in programming, where the program chooses which path to take based on conditions. This is done using IF, ELSE, and CASE statements. It allows the program to perform different actions depending on certain conditions, affecting the overall flow of the program.

### Subroutine

- Question: What is a subroutine, and how does it differ from the main program?

- Answer: A subroutine is a set of instructions designed to perform a specific task, which can be called from the main program whenever needed. It helps break down a complex program into smaller, manageable parts. The main difference is that a subroutine is a small, reusable section of code, while the main program includes all the instructions, including calls to subroutines.

### Library Routine

- Question: What is a library routine, and how does it differ from a custom-built subroutine?

- Answer: A library routine is a pre-written, tested piece of code that is part of a standard library and can be used in programs without modification. Unlike custom-built subroutines, which are written specifically for a program, library routines are general-purpose and shared across many programs, saving time and effort in coding.

### Variable Scope

- Question: How would you explain the concept of variable scope to someone new to programming?

- Answer: Variable scope refers to the part of the program where a variable can be accessed or modified. In CIE IGCSE, scope is usually described as either local (accessible only within a specific subroutine or block of code) or global (accessible from anywhere in the program). Understanding scope is important to avoid errors and conflicts when using variables.
## Subroutines
*definition*: a sequence of instructions that perform a specific task or set of tasks
```
FUNCTION <name> ([<identifier>:<datatype>]) RETURNS <datatype>
	<codes>
    RETURN <data>
ENDFUNCTION

PROCEDURE <name> ([<identifier>:<datatype>])
    <codes>
ENDPROCEDURE
```