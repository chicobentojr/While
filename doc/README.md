Enquanto.g4
# [Enquanto](Enquanto.g4.html)

## Rules

1. programa
2. seqComando
3. comando
4. expressao
5. bool
6. INT
7. ID
8. Texto
9. Espaco

-
### programa [Top](Enquanto.g4.html "Go to top")

#### Text notation:

programa : seqComando ;

#### Visual notation:
![](images/programa.png)

-
### seqComando [Top](Enquanto.g4.html "Go to top")

#### Text notation:

seqComando : comando (';' comando)\* ;

#### Visual notation:
![](images/seqComando.png)

-
### comando [Top](Enquanto.g4.html "Go to top")

#### Text notation:

comando : ID ':=' expressao # atribuicao | 'skip' # skip | 'se' bool 'entao' comando 'senao' comando # se | 'enquanto' bool 'faca' comando # enquanto | 'exiba' Texto # exiba | 'escreva' expressao # escreva | '{' seqComando '}' # bloco ;

#### Visual notation:
![](images/comando.png)

-
### expressao [Top](Enquanto.g4.html "Go to top")

#### Text notation:

expressao : INT # inteiro | 'leia' # leia | ID # id | expressao '\*' expressao # opBin | expressao '+' expressao # opBin | expressao '-' expressao # opBin | '(' expressao ')' # expPar ;

#### Visual notation:
![](images/expressao.png)

-
### bool [Top](Enquanto.g4.html "Go to top")

#### Text notation:

bool : ('verdadeiro'|'falso') # booleano | expressao '=' expressao # opRel | expressao ' expressao # opRel | 'nao' bool # naoLogico | bool 'e' bool # eLogico | '(' bool ')' # boolPar ;

#### Visual notation:
![](images/bool.png)

-
### INT [Top](Enquanto.g4.html "Go to top")

#### Text notation:

INT : ('0'..'9')+ ;

#### Visual notation:
![](images/INT.png)

-
### ID [Top](Enquanto.g4.html "Go to top")

#### Text notation:

ID : ('a'..'z')+ ;

#### Visual notation:
![](images/ID.png)

-
### Texto [Top](Enquanto.g4.html "Go to top")

#### Text notation:

Texto : '"' .\*? '"' ;

#### Visual notation:
![](images/Texto.png)

-
### Espaco [Top](Enquanto.g4.html "Go to top")

#### Text notation:

Espaco : [ \t\n\r] -> Skip ;

#### Visual notation:
![](images/Espaco.png)

Generated by: [ANTLR 4 IDE](https://github.com/jknack/antlr4ide). Copyright (c) 2013 [Edgar Espina](https://twitter.com/edgarespina)