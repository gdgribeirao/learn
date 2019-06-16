# Estruturas de Controle de Fluxo

As _estruturas de controle de fluxo_ são usadas para permitir que o programa
tome decisões ou repita operações. Estas estruturas desviam o fluxo normal de
execução do programa, seguindo determinada lógica imposta pelo programador.

Assim, quando um programa precisa avaliar alguma situação para tomar uma
decisão, isto é feito através das estruturas explicadas neste capítulo.


## Estrutura condicional

A estrutura condicional avalia uma expressão verificando se o resultado é
verdadeiro ou falso. A expressão usada por uma estrutura condicional é comumente
chamada de _condição_.

Em Python, verdadeiro é `True` e falso é `False`. Porém, Python também considera
como _verdadeiro_ todos os números diferentes de zero e _falso_, o número zero
em si. Além disso, Python também considera verdadeiro valores diferentes de
`None` e falso quando o valor é igual a `None`.

Apesar de parecer um pouco confuso a princípio, esta característica da linguagem
tem consequências interessantes que simplificam, sobremaneira, a forma de
escrever o código conforme veremos a seguir.

### if

A estrutra _if_ permite que um programa analise o resultado de uma expressão
lógica e tome uma decisão com relação a este resultado. Assim é possível fazer
com que um programa decida de realiza determinada operação ou não com base no
resultado de uma expressão lógica.

> **Lembrete**
>
> A expressão lógica, ou booleana, tem como resultado sempre um valor lógico, ou
> seja, `True` ou `False`.

Vamos observar como isto funciona avaliando um pequeno trecho de código.

```python
from datetime import datetime

now = datetime.now()
if now.hour >= 18:
    print("Boa noite")
```

Este programa obtém a data e hora atuais e avalia se a hora passou de 18 para
lhe dar boa noite. Não é um programa completo, mas é o suficiente para
entendermos o funcionamento da estrutura _if_.

A primeira linha do programa é usada para trazer ao espaço de nomes do programa
módulos e rotinas de um pacote. Os detalhes desta operação não são de interesse
agora. Depois, o programa obtém a data e hora atuais. Por fim, a hora é
avaliada.

Observe a expressão `now.hour >= 18`. Esta expressão pode ter apenas dois
resultados possíveis: `True` ou `False`. Se o resultado da expressão for `True`,
o programa lhe dará boa noite. E aqui está uma consideração importante sobre o
_if_: o bloco de código imediatamente abaixo dele será executado se, e somente
se, o resultado da expressão avaliada for `True`. Se o resultado for `False`,
este bloco de código será ignorado e não será executado.

> **Nota**
>
> A expressão lógica avaliada pela estrutura _if_ é comumente denominada
> _condição_.

### else

Até aqui aprendemos como tomar decisões simples quando uma expressão lógica é
verdadeira. Mas, e quando a expressão é falsa? A instrução `else` é usada
exatamente para que um bloco de código seja executado quando uma expressão é
falsa.

Em termos de sintaxe, a estrutura condicional completa é assim descrita:

```python

if condição:
    # Instruções que são executadas quando a condição é verdadeira
else:
    # Instruções que são executadas quando a condição é falsa
```

> **Nota:**
>
> Sem o `else`, as instruções que são escritas após o `if` são executadas
> independentemente da condição ser verdadeira ou falsa. Para que um conjunto de
> instruções seja executado quando a condição é falsa, necessariamente este
> conjunto precisa ser escrito dentro do bloco `else`.

A instrução `else` é opcional, ou seja, o `if` não precisa ser escrito com
ela. Porém, se você quer que algo seja necessariamente executado quando a
condição é falsa, é imprescindível escrevê-la no seu código.

Vamos entender melhor isto olhando um exemplo:

```python
x = int(raw_input("Favor digitar um inteiro: "))
if x < 0:
    print("Número negativo")
else:
    print("Número positivo ou igual a zero")
```

Este pequeno exemplo solicita ao usuário um número inteiro e avalia-o para saber
se é um número negativo ou não. A mensagem `Número positivo ou igual a zero` só
é apresentada se o número armazenado em `x` for maior ou igual a zero, ou seja,
a expressão `x < 0` é falsa.

### elif

Python permite uma construção conveniente que simplifica o "encadeamento de
ifs". Normalmente, algumas linguagens permitem o uso da instrução `switch` ou
uma instrução parecida, cujo objetivo é avaliar um valor dentro de uma faixa de
valores conhecida - veremos um exemplo comparativo para entender o que isto quer
dizer.

Os projetistas do Python acharam, por bem, simplificar a linguagem, mantendo
somente a instrução `if` com a conveniência da instrução `elif`. Mas, chega de
mistério. Vamos entender o que é o `elif`.

Vamos voltar ao exemplo anterior, adicionando algumas condições extras:

```python
x = int(raw_input("Favor digitar um inteiro: "))
if x < 0:
    print("Número negativo")
else:
    if x > 0:
        print("Número positivo")
    else:
        if x > 10:
            print ("Número maior que 10")
        else:
            if x > 5:
                print ("Número maior que 5")
            else:
                print("Zero")
```

Este é um exemplo ruim, na verdade. O encadeamento de ifs, como o do exemplo,
normalmente denota uma falha de lógica que pode ser resolvida com expressões
lógicas melhores. Como isto não é um concurso de código bonito e como queremos
aprender Python, o exemplo nos permitirá demonstrar para que serve o tal `elif`.

Veja que o código parece uma escada. Quanto mais condições acrescentarmos para
avaliar os valores possíveis de `x`, mais estranho fica o código, até chegar a
um ponto que a leitura ficará impossível dado o excesso de encadeamento. É para
isso que serve o `elif`. Vamos reescrever o código usando o `elif` para entender
como isso é usado:

```python
x = int(raw_input("Favor digitar um inteiro: "))
if x < 0:
    print("Número negativo")
elif x > 0:
    print("Número positivo")
elif x > 10:
    print ("Número maior que 10")
elif x > 5:
    print ("Número maior que 5")
else:
    print("Zero")
```

O `elif` é equivalente a `else if`. Para ser mais compacto, preferiu-se escrever
`elif`. Com este uso, a estrutura `if` fica mais compacta, de leitura mais
simples e evita-se, com isto, aquela escadinha horrorosa do exemplo anterior.

Esta construção é particularmente útil quando avaliando-se valores discretos
dentro de uma faixa possível de valores. É uma prática comum, em programação,
codificar valores com significados específicos, normalmente usados para algum
tipo de controle de estado. 

Por exemplo, poderíamos criar um menu de opções baseado em uma lista de valores:

```
print("Menu\n1 - Cadastro\n2 - Pesquisa\n3 - Relatórios")
opcao = int(raw_input("Digite a opção desejada: "))
if opcao == 1:
    print("Você solicitou o Cadastro")
elif opcao == 2:
    print("Você solicitou a Pesquisa")
elif opcao == 3:
    print("Você solicitou os Relatórios")
else:
    print("Opção inválida. Tente novamente")
```

Este programa avalia o que o usuário informou em `opcao` para realizar alguma
coisa. Se o usuário digitar um valor que não é esperado, fora da faixa de
avaliação, o programa emite uma mensagem indicando que o usuário se enganou.

Observe que os valores são avaliados um a um. Se fosse um programa complexo, com
diversos itens de menu, a ausência do `elif` tornaria o programa bem difícil de
ler.

## Estruturas de repetição

### for

### while


