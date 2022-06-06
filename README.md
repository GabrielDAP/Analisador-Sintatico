# AnalisadorSintatico

Analisador Sintático criado pelos alunos Daniel Marques, Diego Albuquerque, Gabriel Carlos, Pedro Guimarães e.....,  baseado em exemplos vistos em sala de aula e pesquisado pelos membros integrantes do grupo.

Exemplo de um pequeno compilador feito em Java para analisar expressões aritméticas.
Feito de forma manual para apresentar os conceitos de autômatos e parsers visto na disciplina de Compiladores

## Analisador Léxico

Tokens Reconhecidos:
Identificadores := LETRA (LETRA | DIGITO)*
Numeros := DIGITO+ (. DIGITO*)?
Operadores := > | < | = | ! | + | - | * | /

## Analisador Sintático
Dada a gramática

G = (Vn, Vt, P, S)

Vn = E, T, OP

Vt = id, num, + , - , * , /

P = dado pelas regras abaixo

		1. E ->   E OP T | T
		2. T ->  id | num
		3. OP ->  + | - | * | /

*precisamos reescrever a regra 1, transformando-a nas seguintes regras*

	1a.  E  ->  T E'
	1b.  E' -> OP T E' | &
	2.   T  -> id | num
	3.   OP -> + | - | * | /
	
Tranformamos a gramática em LL(1).