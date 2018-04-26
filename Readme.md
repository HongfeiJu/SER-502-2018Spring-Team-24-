# SER502-Spring2018-Team<24>

**Members**

Hongfei Ju

Ruihao Zhou

Zachary Wang

**Development Plan**

Lexical Analysis: Hongfei Ju, Ruihao Zhou

Parser & Intermediate Code Generator: Hongfei Ju

Interpreter: Zachary Wang


## System Requirement

**Platform**

    Windows(Java runtime environment 1.8.0)
    MacOS(Java runtime environment 1.8.0)


## Install Directions

Compiler: download executable file "Compiler.jar" from [here](https://github.com/HongfeiJu/SER502-Spring2018-Team-24/tree/master/bin).

Interpreter: download java class "Interpreter" from [here](https://github.com/HongfeiJu/SER502-Spring2018-Team-24/tree/master/src/runtime).



## Build and Run Directions


For the compiler, run the following command in Command Prompt, :

`java -jar Compiler.jar filename.L0`

For the interpreter, please see the following instruction. The following example takes Mac as the development environment.

Step 1:
On terminal.app, go to Interpreter.java directory, and run the following command to compile Interpreter.java.

    javac Interpreter.java

Step 2:
Run the following command to run the interpreter and test Sample1_IC.txt. If the txt file is in the same directory, just add the file name to the command line.

    java Interpreter Sample1_IC.txt

If the txt file is not in the same directory, we need to add the complete path

    java Interpreter /Users/david/Desktop/SER502/sample1_IC.txt


## YouTube Video Link

The presentation video about this project is [here](https://www.youtube.com/watch?v=vZbybIA0izA).

## Language Name

**L0** will be our language name.
Zero is the first natural number, we see L0 as a good start of our learning in compiling techniques.

## Language design

Primitive Type: 

This programming language includes two primitive types: boolean values and int numeric value. 

Operation:

For boolean type data, the corresponding operators include “equal”, “larger than”, “no less than”, “less than”, no larger than”, “not equal”. For int numeric type data, the corresponding operators include “plus”, “minus”, “multiply”, “divide”.

Statements: 

assignment to associate a value with a variable, if-then-else statement to make decisions, and while statement for iterative execution.



## Grammar Rule

```
program  :  statement_list ;
statement_list  :  statement  statement_list  |  statement  ;
statement  :  declaration  |  assignment  |  if_statement  |  while_statement  |  print  ;
declaration  :  'var'  ID  ';'  ;
assignment  :  ID  ':='  low_expression ';'  ;
if_statement  :  'if'  '(' boolean_expression  ')'  'correct'  '{'  statement_list  '}'  |  'if'  '('  boolean_expression  ')'  'correct'  '{'  statement_list  '}'  'wrong'  '{'  statement_list  '}'  ;
while_statement  :  'while'  '('  boolean_expression  ')'  '{'  statement_list  '}'  ;
print  :  'print'  low_expression  ;
boolean_expression  :  low_expression  '=='  low_expression  |  low_expression  '>'  low_expression  |  low_expression  '>='   low_expression  |  low_expression '<' low_expression  |  low_expression  '<='  low_expression  |  low_expression  '!='  low_expression  |  boolean_val  ;
boolean_val  :  'true'  |  'false'  ;
low_expression  :  high_expression  '+'  low_expression  |  high_expression  '-'  low_expression  |  high_expression  ;
high_expression  :  item  '*'  high_expression  |  item  '/'  high_expression  |  item  ;
item  :  '(' expr ')' | ID | NUMBER  ;
ID  :  [a-z|A-Z]+  ;
NUMBER  :  [0-9]+  ;
WS :  [ \t\r\n]+ -> skip ;
```

## Design Details
* Paradigm of the Language
	
		imperative paradigm
	

* Parsing Process(Technique)

   ![Parsing Process](https://github.com/HongfeiJu/SER502-Spring2018-Team-24/blob/master/doc/Parsing%20process.png)
		


* Example Program in High Level Language

     For more example, please see [here](https://github.com/HongfeiJu/SER502-Spring2018-Team-24/tree/master/data)
	
     Example: counting the sum of all the numbers between 0 and 10 using our language L0.

```
var sum;
sum:=0;
var count;
count:=0;
while(count<=10){
sum:=sum+count;
count:=count+1;
}
print sum;
```
 
### Extra Credit ###
1. We implemented `print` statment in our language to output the variable or value. So you can:

```
var a;
a:=1;
print a;
```
	
the output will be 

	
```
1
```


