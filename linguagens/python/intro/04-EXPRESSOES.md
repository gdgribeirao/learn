# Expressões

Agora que já estudamos as variáveis, precisamos entender como utilizá-las em _expressões_. A rigor, uma expressão é:

> uma combinação de valores, variáveis, operadores e ativações de funções ou métodos que são avaliados de acordo com a precedência e associatividade particulares a uma determinada linguagem de programação.

## Avaliando Expressões

Caso seja digitada uma expressão na linha de comando, ela será avaliada linha à linha, seguindo a precedência matemática clássica.

Exemplo:
```Python
>>> 25 + 15
40
>>> 10 * 5 + 10
60
```

No exemplo acima a expressão `10 * 5 + 10` pode ser reescrita com parênteses para mudança da precedência e do valor final:

```Python
>>> 10 * (5 + 10)
150
```

Avaliar uma expressão não é a mesma coisa que imprimir algum valor na tela, isso depende muito do tipo de execução. As maneiras mais comuns para rodar programas Python são:
- A linha de comando (Interpretador Python) - também conhecido como REPL, em que se avalia uma linha por vez, normalmente utilizado para testes rápidos de código.
- Rodar como script, também na linha de comando mas dessa vez o código/arquivo inteiro é executado de uma só vez.



## Precedência de Operadores

Em Python, o parênteses tem sempre a maior precedência, fora ele existe a precedência matemática abaixo:

| Operadores                                   | Significado                                     |
|----------------------------------------------|-------------------------------------------------|
| ( )                                          | Parênteses                                      |
| **                                           | Expoente                                        |
| +x, +x. ~x                                   | Unário mais, unário menos, bitwise não          |
| *, /, //, %                                  | Multiplicação, divisão, divisão inteira, módulo |
| +, -                                         | Adição, Subtração                               |
| <<, >>, &, ^, |                              | Operadores Bitwise                              |
| ==, !=, >, >=, <, <=, is, is not, in, not in | Comparações, identidade, filiação, operadores.  |
| not                                          | NÃO lógico                                      |
| and                                          | E lógico                                        |
| or                                           | OU lógico                                       |


### Regras para expressões

- Operadores com a **mesma precedência** são avaliados da esquerda para a direita. 
- O operador % também é usado para formatação de strings, seguindo a mesma precedência.



## Exemplos de expressões válidas

Abaixo alguns exemplos de expressões válidas em Python:

- Multiplicação:
```python
>>> 25 * 45
1125
>>> 7 * 7
49
```

- Exponenciação:
```python
>>> 25 ** 2
625
>>> 7 ** 5
16807
```

- Divisão exata:
```python
>>> 40 // 45
0
>>> 95 // 30
3
```

- Expressões lógicas:
```python
>>> 55 > 10
True
>>> 20 == 10
False
```

- Expressões de filiação:
```python
>>> 'b' in 'abcd'
True
>>> 'e' in 'abcd'
False
```

- Expressões de assignação:
```python
>>> a = 20
>>> b = 12
>>> c = a + b
>>> c
30
>>> grupo = 'GDG'
>>> grupo + ' ribeirao'
'GDG ribeirao'
```