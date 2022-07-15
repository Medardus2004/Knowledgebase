#Binary Exploits

Introduction: https://guyinatuxedo.github.io/


###What is Binary?

A binary is compiled code. When a programmer writes code in a language like C, the C code isn't what gets actually ran. It is compiled into a binary and the binary is run. Binary exploitation is the process of actually exploiting a binary, but what does that mean?

In a lot of code, you will find bugs. Think of a bug as a mistake in code that will allow for unintended functionality. As an attacker we can leverage this bug to attack the binary, and actually force it to do what we want by getting code execution. That means we actually have the binary execute code that we say, and can essentially hack the code.

###Assembly

Memory is allocated to the heap always when **malloc** , **calloc** , **static** or **global** are called.

registers are small storages in the processor.

there are 6 general purpose registers: **eax, ebx, ecx, edx, ebi, edi**

There are 3 special reserved registers: **ebp, esp, eip**

The stack is a data structure comprised of elements that are added and removed with push and pop

esp: top element of the stack
ebp: bottom element of the stack

There are two syntaxes assembly is normally written in; AT&T and Intel
