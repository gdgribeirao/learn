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

### elif 

## Estruturas de repetição

### for

### while


