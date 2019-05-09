# Expressões

Agora que já estudamos as variáveis, precisamos entender como utilizá-las em
_expressões_. A rigor, uma expressão é:

> uma combinação de valores, variáveis, operadores e ativações de funções ou
> métodos que são avaliados de acordo com a precedência e associatividade
> particulares a uma determinada linguagem de programação.

## Operadores e Operandos

Antes de seguirmos adiante, é importante que façamos uma pequena parada no mundo
dos operadores e operandos. Afinal, as expressões são combinações destes
elementos, não limitando-se a eles conforme já vimos.

O _operador_ realiza uma operação. Parece óbvio. Mas não tão assim. As operações
podem ser bem complicadas, principalmente em linguagens que permitem a
sobrecarga de operadores, como C++. Já voltamos nisso.

O _operando_ são os elementos necessários para que a operação seja executada com
sucesso. A grande maioria dos operadores das linguagens de programação são
operadores _binários_, ou seja, necessitam de dois operandos. Aqui estão alguns
exemplos:

```python
10 + 25
3 - 4
5 / 2
4 * 34
42 ** 2
```

No exemplo podemos notar que os números e os operadores. Esta é a forma mais
simples de expressão, ou seja, operadores e seus respectivos operandos.

Os símbolos que definem os operadores são determinados pela _gramática_ da
linguagem de programação. Assim, cada linguagem tem seu próprio conjunto de
símbolos que definem as operações. Normalmente os projetistas das linguagens de
programação tentam manter o senso comum: + é soma, - é subtração. No entanto, é
sempre uma boa ideia ler a documentação da linguagem para saber se isto é
realmente uma verdade. Por exemplo, o operador _+_ é usado como concatenação de
strings em diversas linguagens, algo que é bem diferente de uma _soma_.

A tabela abaixo demonstra os operadores definidos pela gramática da linguagem Python:

| Operador | Significado |
|---|---|
|+ | Soma. Pode ser usado para concatenar strings. |
|- | Subtração. |
|* | Multiplicação |    
|** | Exponenciação |   
|/ | Divisão |
|// | Divisão exata ou inteira (arredonda para baixo) |
|% | Módulo (resto da divisão) |
|@ | Multiplicação de matrizes |
|<< | Giro de bits à esquerda |   
|>> | Giro de bits à direita |
|& | E bit a bit (bitwise) |
|\| | OU bit a bit (bitwise) |
|^ | XOR bit a bit (bitwise) |
|~ | NÃO bit a bit (bitwise) |
|< | Menor |
|> | Maior |    
|<= | Menor ou igual |
|>= | Maior ou igual |
|== | Igual |
|!= | Diferente |
|in | Pertence (usado para verificar se um item pertence à uma coleção) |
|or | OU booleano |
|and | E booleano |
|not | NÂO booleano |
|if else | Expressão condicional |
|lambda | Expressão anônima |

### Conversões Aritméticas



## Avaliando Expressões

Caso seja digitada uma expressão na linha de comando, ela será avaliada linha a
linha, seguindo a precedência matemática clássica.

Exemplo:

```Python

>>> 25 + 15

40

>>> 10 * 5 + 10

60
```

No exemplo acima a expressão `10 * 5 + 10` pode ser reescrita com parênteses
para mudança da precedência e do valor final:

```Python

>>> 10 * (5 + 10)

150
```

Avaliar uma expressão não é a mesma coisa que imprimir algum valor na tela, isso
depende muito do tipo de execução. As maneiras mais comuns para rodar programas
Python são:

- A linha de comando (Interpretador Python) - também conhecido como
  [REPL](https://en.wikipedia.org/wiki/Read%E2%80%93eval%E2%80%93print_loop), em
  que se avalia uma linha por vez, normalmente utilizado para testes rápidos de
  código.

- Rodar como script, também na linha de comando mas dessa vez o código/arquivo
  inteiro é executado de uma só vez.

## Precedência de Operadores

A _precedência_ determina a ordem na qual uma expressão será
avaliada. Normalmente as linguagens de programação tentam seguir as regras
estabelecidas pela matemática. No entanto, as expressões nas linguagens de
programação podem envolver tipos diferentes, o que faz com que as expressões
sejam bem diferentes se comparadas às da matemática. Portanto, cada linguagem
determina sua própria ordem de precedência.

A _ordem de precedência_ determina qual operação será realizada primeiro em uma
expressão. Os operadores em Python seguem a seguinte ordem de precedência:

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

- Operadores com a **mesma precedência** são avaliados da esquerda para a
  direita.

- O operador % também é usado para formatação de strings, seguindo a mesma
  precedência.

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

< [Variáveis](03-VARIAVEIS.md) | [Próximo Tópico: Estruturas de Controle](05-CONTROLE.md) >
