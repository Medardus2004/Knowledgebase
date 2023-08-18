# Web Exploits
We want to leak the encryption method somehow, so we open **BurpSuite** to monitor the requests made to the site.



# Binary Exploits

Introduction: https://guyinatuxedo.github.io/


### What is Binary?

A binary is compiled code. When a programmer writes code in a language like C, the C code isn't what gets actually ran. It is compiled into a binary and the binary is run. Binary exploitation is the process of actually exploiting a binary, but what does that mean?

In a lot of code, you will find bugs. Think of a bug as a mistake in code that will allow for unintended functionality. As an attacker we can leverage this bug to attack the binary, and actually force it to do what we want by getting code execution. That means we actually have the binary execute code that we say, and can essentially hack the code.

### Assembly

Memory is allocated to the heap always when **malloc** , **calloc** , **static** or **global** are called.

registers are small storages in the processor.

there are 6 general purpose registers: **eax, ebx, ecx, edx, ebi, edi**

There are 3 special reserved registers: **rbp, rsp, rip**

The stack is a data structure comprised of elements that are added and removed with push and pop

esp: top element of the stack
ebp: bottom element of the stack

There are two syntaxes assembly is normally written in; AT&T and Intel

We have tools such as Ghidra that will take compiled assembly code and give us a view of what it thinks the C code that the code was compiled from looks like.

In x64 there is the rax, eax, ax, and al register. The rax register points to the full 8. The eax register is just the lower four bytes of the rax register. The ax register is the last 2 bytes of the rax register. Lastly the al register is the last byte of the rax register.

#### Übersicht der Comands

https://www.utd.hs-rm.de/infobuch2/buch_webseite/kap03/assemblerbefehle.pdf

### Useful tools
#### ghidra 
Gidra will take compiled assembly code and give us a view of what it thinks the C code that the code was compiled from looks like.

#### objdumb
To view disassembly machine code into assembly code, you can use something like objdump

&>     objdump -D hello_world -M intel | less

#### gdb
gdb is a debugger (specifically the gnu debugger). Gef is an a gdb wrapper, designed to give us some extended features

$> gdb ./hello-owrld 
- 'next' - which will take you through one line of code, but will step over function calls such as puts.
- 'step' - which will take you through one line of code, but will step into function calls
- 'stepi' - whch will take you through one instruction at a time, stepping into function calls


For Example, if we can see that the register esp holds the value 0xffffd0d0, which is a pointer. Let's see what it points to:

gef➤  x/a 0xffffd0d0

0xffffd0d0:	0x80484b0

gef➤  x/10c 0x80484b0

0x80484b0:	0x68	0x65	0x6c	0x6c	0x6f	0x20	0x77	0x6f

0x80484b8:	0x72	0x6c

gef➤  x/s 0x80484b0

0x80484b0:	"hello world!"

let's view the contents of all of the registers:

gef➤  info registers

Now let's view the stack frame:

gef➤  info frame

Now let's view the disassembly for the main function:

gef➤  disass main

Let's say we wanted to change the contents of what will be printed. Importantly, in many programs your ability to do this is dependent on the size of the string you are trying to replace. If you overwrite it with something that is too large, you run the risk of overwriting other memory and breaking the program. There are plenty of workarounds but this is rarely applicable from a bin-ex perspective.


gef➤  set {char [12]} 0x080484b0 = "hello venus"

gef➤  x/s 0x080484b0

0x80484b0:	"hello venus"

gef➤  nexti

Now let's say we wanted to change the value stored at the memory address 0x08048451 to 0xfacade:

gef➤  x/g 0x08048451

0x8048451 <__libc_csu_init+33>:	0xff08838d

gef➤  set *0x08048451 = 0xfacade

gef➤  x/g 0x08048451

0x8048451 <__libc_csu_init+33>:	0xfacade

Let's say we wanted to jump directly to an instruction like 0x08048451, and skip all instructions in between:


gef➤  j *0x08048451

Continuing at 0x0x08048451.

hello venus

#### pwntools intro

Pwntools is a python ctf library designed for rapid exploit development. It essentially help us write exploits quickly, and has a lot of useful functionality behind it.

$> python3

>> from pwn import *

>> target = remote("github.com", 9000)

>> target = process("./challenge")

>> gdb.attach(target)   //Attaches the gdb debugger

http://docs.pwntools.com/en/stable/
