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

![Architecture](https://github.com/WOWSCpp/Cpp-Lisp-Interpreter/blob/v1.01/imgs/Arch.png)


## Features
|  true | * | == | >   | or    | list      | rm_head     | cons   | foldl |
|:-----:|:-:|----|-----|-------|-----------|-------------|--------|-------|
| false | / | <= | def | if    | push_back | rm_tail     | max    | map   |
| +     | % | >= | set | while | head      | nth_element | min    |       |
| -     | ! | <  | and | func  | tail      | size        | filter |       |

## Sample of Abstract Syntax Tree
#### Fibonacci sequence recuesive version
```Lisp
(function fib (n) 
  (if 
    (< n 2) 
    n 
    (+ 
      (fib (- n 1)) 
      (fib (- n 2))
    )
  )
)
```

![Sample of Abstract Syntax Tree](https://github.com/WOWSCpp/Cpp-Lisp-Interpreter/blob/v1.01/imgs/recur.png)


## Sample Results

#### Fibonacci sequence iterative version
```Lisp
(def a (list 0 1 1))
(function fib(n) 
  (while 
    (< (size a) n)  
      (push_back a  
      (+
        (nth_element(- (size a) 1) a)
        (nth_element(- (size a) 2) a)
      )
    )
  )
)
```
![result of iterative fibonacci sequence](https://github.com/WOWSCpp/Cpp-Lisp-Interpreter/blob/v1.01/imgs/fib_res.png)


####  Function and Higher Order Function
Example of the filter function.

```Lisp
(def a (list 1 2 3 4))
(function even (x)
  (if
    (== (% x 2) 0)
    true
    false
   )
)
(filter even a)
```
![result of filter](https://github.com/WOWSCpp/Cpp-Lisp-Interpreter/blob/v1.01/imgs/filter_res.png)

Example of foldl function.

```Lisp
(def a (list 1 2 3 4))
(function sum(x y) (+ x y))
(foldl sum 10 a)
```
![result of filter](https://github.com/WOWSCpp/Cpp-Lisp-Interpreter/blob/v1.01/imgs/fold_res.png)

You can also implement your own logic for map, foldl and filter function.

####  Function Overloading

Example of sum function overloading.

```Lisp
(function add (a b) (+ a b))
(function add (a b c) (+ a b c))
```
![result of filter](https://github.com/WOWSCpp/Cpp-Lisp-Interpreter/blob/v1.01/imgs/over_res.png)


## Compilation: 
* For linux, first cd in /src, then use this command:
  g++ main.cpp astnode.cpp builtin.cpp environment.cpp evaluator.cpp utils.cpp -I ../include -o main
 
* For windows, you can simply add the files into your project and then compile & run your project.
