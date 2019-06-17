# Cpp-Lisp-Interpreter
# A Lisp interpreter implemented with C++



## Architecture
* Tokenizer
* Text Parser
* BuiltIn
* Environment
* AST
* Macro Compiler
* Evaluator

![image](https://github.com/WOWSCpp/Cpp-Lisp-Interpreter/blob/v1.01/imgs/Arch.png)


Compile: in /src path, then use this command:

g++ main.cpp astnode.cpp builtin.cpp environment.cpp evaluator.cpp utils.cpp -I ../include -o main

