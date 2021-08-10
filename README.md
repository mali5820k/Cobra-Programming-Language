# King Cobra
### Project Goals/Focus:
  - A programming language inspired from Python's simplicity and C/C++'s speed.
  - The language itself is going to be compiler-based with focus on portability via a VM (low-level Virtual Machine). The focus of this project is to implement KC entirely with the help of "Crafting Interpreters" by Robert (Bob) Nystrom, and then to implement modern features to make KC a language that I would use. If time becomes scarce, then I'll simply leave the project as a learning experience. Please check out the P.S. section for more details on licensing and potential future plans.

Again, this is an ongoing project that is based off of interest in compiled languages.
The book I am actively reading to accomplish this project is "Crafting Interpreters" by Bob Nystrom which he has made publicly available at: https://craftinginterpreters.com/
For those who think I'm mistaken about the language being compiled when I'm reading a book about making an interpreter, there is a bit of a knowledge trip you have to undergo:
- All interpreted languages compile instructions down to machine code for execution.
- Compiled languages simply have divided the interpreter into two distinct "programs": the compiler and the interpreter. The compiler optimizes and converts the source code into a medium that is either machine-code or an intermediate representation like byte-code, and the interpreter can take on two forms, one where it is ommitted, and another where it is a separate program for executing the compiled byte-code; There are languages, such as C/C++, that compile to machine code for direct execution on machine hardware without an interpreter, and other languages like Java where the JVM is essentially a really complex interpreter.
- Interpreted languages like Python combine the compiler and interpreter into a "Interpreter" where the code is executed as it's read and converted. The reason this is different from Java's implementation of JVM is because Python doesn't store the current compiled instruction for later use, it simply compiles the instruction again, where-as JVM receives the compiled byte-code that doesn't need to be re-compiled when it is being executed by the interpreter (JVM), therefore it retains a speed advantage over Python.
- This implementation is a mix of the compiler and interpreter together as one complete "interpreter". I have yet to test the execution speed for this interpreter implementation, but I will be creating a separate compiler for this language so that a byte-code file can be generated for faster execution, just like how Java, C#, and other IR compiling languages function.
- So why not make a compiler and interpreter separately from the get go? I want to match the functionality of languages like Java where you can have a live interpreter session to run code, so I would've needed to include an interpreter anyways regardless of the approach.
- Lastly, I have no performance metrics of the interpreter as of writing this. It could be just as fast as the JVM, slower, or even faster (best case). If it matches the speed of the JVM, then I've effectively acheived one of the many goals of the language implementation.

## Important Notes for compiling and running the interpreter

### For Windows 10 users:
- If you want to skip the manual build process, you can grab a pre-built executable from the [releases](https://github.com/mali5820k/KC-Programming-Language/releases) page. Keep in mind that this may not be the most current version.
- To run the interpreter, you need to first install GCC for Windows 10 and if you don't want to use the build program executable, acquire Make for Windows as well.
- If you don't want to use Make or the program executable, you can run the python build script in powershell, cmd, or a terminal window of your choice to produce the Interpreter_Program.exe program. Run the terminal of your choice as an administrator. 
- Finally, you can type away in the program once you have launched it.

### For Mac OS users:
- I haven't tested anything with Macs as I don't own one. I do know that Macs have Clang pre-installed and it's closest in terms of functionality to Linux as it's Unix-based, so you might be able to run the included make file after some tweaks or the python compile file and have the program compile to an executable binary.
- I still recommend Mac users try to acquire GCC in some way as Clang has resulted in strange issues from build to build that weren't present in GCC.

### For Linux users:
- Since this project is natively coded on Linux, you can simply run the make file for GCC. 
- The python build script will also work as long as you have python 3 installed or run the included executable (if there is one included at the time).
- Once the program binary is compiled, you simply need to run the file in a terminal with
  ```./Interpreter_Program```

## P.S.
Keep in mind that I'm only one person and although Nystrom's book is guiding me through this project, functionality that I want to add is going to take time; so bugs are to be expected and with time, the language will diverge and become more of its own thing-if you will-than the Lox programming language implementation described in "Crafting Interpreters" by Bob Nystrom.

Also, a syntax and feature guide will be posted here as well as the releases page with a downloadable PDF later. I have several more features to include before that will be relevant. 

A possible question you may ask is "Why not just fork Nystrom's repository and work from there?" Simply, I want to experience the entire process that he outlines in his book to understand the material to the best of my ability. Furthermore, he is hosting other files and directories in his repository that aren't covered under his MIT license, so I deliberatly created a fresh repository to house the MIT licensed code while giving credit to him in the license file and in this long ReadMe. Another reason for not forking his repository is that I simply wouldn't have known where to start, as I'm learning how a programming language is created from scratch from his book. For those interested, here is his [repository](https://github.com/munificent/craftinginterpreters).

Lastly, it is unclear to me as to how to use the MIT license in terms of the copyright of code. To be safe, I have included the original copyright notice of Bob Nystrom (written as Robert Nystrom in his original license file on his repository) from his MIT license for MIT licensed code, in my MIT license file as well. This should suffice for any modifications or additions that I have made and to ensure all legal bases are covered for the MIT licensed code.

Thank you for checking out my repo!
