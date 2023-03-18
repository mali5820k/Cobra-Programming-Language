# King Cobra (Byte-code Interpreted language)
### Current Status of the Project:
  - I am ending development on this project and will be leaving it as a learning experience, until I see myself coming back to do more work on this interpreter. Moving forward, I will be making a new programming language without using source code from "Crafting Interpreters" by Robert (Bob) Nystrom, his repository, or even this repository. The reason being the new language will be fundamentally a typed-language with my own opinions and design choices, which will require a major rewrite of the existing (this) code-base anyways. Creating the new language from scratch would allow me to better apply what I have learned thus far and not tie me down to source code that was intended for a different type of programming language. This decision makes more sense when you look at the new language's repo where I explain what I am using to build the compiler for it. **CORRECTION from the future: The new programming language's implementation will be a compiled one. The goal is AOT compiled, but JIT compiled may also be chosen depending on practicality.** Both the new and current projects will continue to be open source but the repository for the new project will be separate. The link to the new project can be found [here](https://github.com/mali5820k/Cobralyth).
  
  - I also want to mention that the name of this language was chosen for the sake of naming the language, and thus this language and project are not associated with any trademarked entity nor is it meant to be associated with any trademarked entity. Therefore, this project is solely a learning experience.

  - Once again, thank you so much for checking out my programming language. I owe it to Robert (Bob) Nystrom's ["Crafting Interpreters"](https://craftinginterpreters.com/) book for getting me this far. In the future, when I know enough about the use of open-source licensing with regards to forking, language names, linking with various runtimes, and etc so that I am no longer oblivious to intricate legal details with regards to licensing, then I may revisit this project for the sake of refining it. And who knows, this language could be ported over to run on different interpreters, some with JIT, or directly compiled to another language target like C, C++, WebAssembly, and more. If I have to be honest, I feel as though this language is more Lox than King Cobra, since the foundation is the Lox language implementation which I built off of to make King Cobra. That's also the reason why I want to move on from this project and make another language that I can fully call my own without the "imposter" syndrome feeling found with getting something done the first time around and feeling as if you only managed this because someone else was there to help you, in this case Robert (Bob) Nystrom's book. In other words, I want to prove to myself that I am now capable of taking what I've learned and making something that I can call my own.
  - For those interested in Robert (Bob) Nystrom's source code repository, [here you go](https://github.com/munificent/craftinginterpreters). I explained in the P.S. Section of this readme as to why I didn't simply fork Robert (Bob) Nystrom's repository and work from there. TLDR: I was new and wanted to go through each phase by reading from the book and working towards the end goal, as well as avoiding licensing issues with other files that he hosted in his repo that weren't covered under the MIT license file from his repo. His copyright is still included in this repo's license (FYI), as well as mine from the changes/additions/amends that I've made.

### Current State of the Source Code (Non-Release) (10/16/2021)
The last features that I haven't compeletely implemented yet were arrays, include statements, and further built-in functions, however, I would like to move on from this project and believe that any more work here would simply take way from the vision I have of my new project. If you're interested to implement this feature and any others, feel free to do so. The language already is object oriented and the foundation for adding new features is already in place.

### Project Goals/Focus:
  - A programming language inspired from Python's simplicity and C/C++'s speed.
  - The language itself is going to be compiler-based with focus on portability via a VM (low-level Virtual Machine). The focus of this project is to implement KC entirely with the help of "Crafting Interpreters" by Robert (Bob) Nystrom, and then to implement modern features to make KC a language that I would use. ***If time becomes scarce or my motivation to work on this language changes, then I'll simply leave the project as a learning experience.*** Please check out the P.S. section for more details on licensing and potential future plans.

Again, this is an ongoing project that is based off of interest in compiled languages.
The book I am actively reading to accomplish this project is "Crafting Interpreters" by Bob Nystrom which he has made publicly available at: https://craftinginterpreters.com/
For those who think I'm mistaken about the language being compiled when I'm reading a book about making an interpreter, there is a bit of a knowledge trip you have to undergo:
- Most interpreted languages compile source-code instructions down to byte-code representation for interpreting in a virtual machine (VM) for execution.
- Compiled languages simply have divided the interpreter into two distinct "units" and optimized each for their own purposes: the compiler and the interpreter. The compiler optimizes and converts the source code into a medium that is either machine-code, an intermediate representation like byte-code, or something else that can be  evaluated, and the interpreter can take on two forms, one where it is the machine hardware itself (fastest), and another where it is a separate program that is often referred to as a virtual machine (think Java JVM or C#'s CLR and CPython's Interpreter) for executing the compiled byte-code or source code; There are languages, such as C/C++, that compile to machine code for direct execution on machine hardware where the hardware serves the purpose of the interpreter, and other languages like Java where the JVM is essentially a really complex software-interpreter which compiles the most used instructions into machine code that's most optimized for the machine that's running it, also referred to as Just-In-Time (JIT) compilation. As always, hardware interpretation is faster than software interpretation.
- Interpreted languages like Python stage the interpreter into two stages, the compiler and virtual-machine, where the byte-code that's compiled from the source code is executed as it's read and converted. The reason this is different from Java's implementation of JVM is because Python has to decipher the variable or datastructure type before executing every compiled byte-code instruction, it simply takes longer to execute instructions due to the lack of type information, where-as JVM receives the compiled byte-code with the variable and datastructure types, that simply needs to be interpreted and executed by the interpreter (JVM) and no additional overhead is required for identifying types at runtime since Java is a strongly-typed langauge. Therefore, with the use of the JVM's JIT compiler, Java retains a speed advantage over Python.
- This implementation is most relatable to that of CPython, a mix of the byte-code compiler and byte-code interpreter together as one complete "interpreter program". I have yet to test the execution speed for this interpreter implementation, but if I am able to, I will be modifying the compiler for this language so that a byte-code file can be generated for portability, and then utilizing a JIT API/tool/resource such as LLVM or something else for faster execution, just like how Java, C#, and other IR compiling languages function.
- So why not make a compiler and interpreter separately from the get go? I want to match the functionality of languages like Java where you can have a live interpreter session to run code, so I would've needed to include an interpreter anyways regardless of the approach.
- Lastly, I have no performance metrics of the interpreter as of writing this. It could be just as fast as the JVM, slower, or even faster (best case). If it matches the speed of the JVM, then I've effectively acheived one of the many goals of the language implementation.

## Important Notes for compiling and running the interpreter

### For Windows 10 users:
- If you want to skip the manual build process, you can grab a pre-built executable from the [releases](https://github.com/mali5820k/KC-Programming-Language/releases) page. Keep in mind that this may not be the most current version.
- To run the interpreter, you need to first install GCC for Windows 10 and if you don't want to use the build program executable, acquire Make for Windows as well.
- If you don't want to use Make or the program executable, you can run the python build script in powershell, cmd, or a terminal window of your choice to produce the Interpreter_Program.exe program. Run the terminal of your choice as an administrator. 
- Finally, you can type away in the program once you have launched it.

### For Mac OS users:
- I haven't tested anything with Macs as I don't own one. I do know that Macs have Clang pre-installed and it's closest in terms of functionality to Linux as it's Unix-based, so you might be able to run the included make file after some tweaks or can edit the python compile file, to add mac compilation support, and have the program compile to an executable binary.
- I still recommend Mac users try to acquire GCC in some way as Clang has resulted in strange issues from build to build that weren't present in GCC.

### For Linux users:
- Since this project is natively coded on Linux, you can simply run the make file for GCC. 
- The python build script will also work as long as you have python 3 installed or run the included executable (if there is one included at the time).
- Once the program binary is compiled, you simply need to run the file in a terminal with
  ```./Interpreter_Program```

## P.S.
Keep in mind that I'm only one person and although Nystrom's book is guiding me through this project, functionality that I want to add is going to take time; so bugs are to be expected and with time, the language will diverge and become more of its own thing-if you will-than the Lox programming language implementation described in "Crafting Interpreters" by Bob Nystrom.

**UPDATE:** I have changed my mind to not include a feature guide, instead, please see the test#.kc file variants included in the release for Windows 10 Final Version as I'm stopping work on this project for my new project (as stated at the top of the Readme). Those test files encompass the various features that the language supports with comments. If viewing those files in VSCode, change the language highlight mode to Go, for Notepad++ change the language highlight mode to Javascript.

A possible question you may ask is "Why not just fork Nystrom's repository and work from there?" Simply, I want to experience the entire process that he outlines in his book to understand the material to the best of my ability. Furthermore, he is hosting other files and directories in his repository that aren't covered under his MIT license, so I deliberatly created a fresh repository to house the MIT licensed code while including his original copyright notice in the license file in this repo and mentioning him in this README. Another reason for not forking his repository is that I simply wouldn't have known where to start, as I'm learning how a programming language is created from scratch from his book. For those interested, here is his [repository](https://github.com/munificent/craftinginterpreters).

Lastly, it is unclear to me as to how to use the MIT license in terms of the copyright of code regarding new addtions to MIT licensed code. To be safe, I have included the original copyright notice of Bob Nystrom (written as Robert Nystrom in his original license file in his repository) from his MIT license that covers all MIT licensed code from him in my MIT license file, as well as my copyright statement for any new modifications/amends/ and expanding existing code. This should suffice for any modifications or additions that I have made and to ensure all legal bases are covered for the MIT licensed code.

Thank you for checking out my repo!
