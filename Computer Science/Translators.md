### What is a translator?
- A translator is a program that **translates** program **source code** into **machine code** so that it can executed directly by a processor
- **Low-level languages** such as **assembly code** are translated using an **assembler**
- **High-level languages** such as **Python** are translated using a **compiler** or **interpreter**

### What is a compiler?
- A compiler translates high-level languages into machine code **all in one go**
- Compilers are generally used when **a program is finished** and has been checked for syntax errors
- Compiled code can be **distributed (creates an executable)** and run **without the need for translation software**
- If compiled code contains any errors, after fixing, it **will need re-compiling**

| **Advantages**                        | **Disadvantages**                                |
| ------------------------------------- | ------------------------------------------------ |
| Speed of execution                    | Can be memory intensive                          |
| Optimises the code                    | Difficult to debug                               |
| Original source code will not be seen | Changes mean it must be recompiled               |
|                                       | It is designed solely for one specific processor |

### What is an interpreter?
- An interpreter translates high-level languages into machine code **one line at a time**
- Each line is executed after translation and if **any errors are found**, the **process stops**
- Interpreters are generally used when a program **is being written** in the development stage
- Interpreted code is more **difficult to distribute** as **translation software is needed for it to run**

| **Advantages**                                              | **Disadvantages**                                     |
| ----------------------------------------------------------- | ----------------------------------------------------- |
| Stops when it finds a specific **syntax error** in the code | Slower execution                                      |
| Easier to debug                                             | Every time the program is run it has to be translated |
| Require less RAM to process the code                        | Executed as is, no optimisation                       |
