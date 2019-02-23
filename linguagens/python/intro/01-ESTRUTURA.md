# Estrutura da Linguagem

Antes de metermos realmente a mão na massa é preciso compreender como as coisas são organizadas para que o seu programa possa ser executado de forma adequada. Toda linguagem tem alguma forma de organização. No geral, os arquivos do seu programa serão organizados de acordo com a vontade do programador. Se o programador é organizado, maravilha. Se não é, bem...

A linguagem Python convenciona algumas regras importantes que você precisa saber na largada. Estes conceitos são um pouco artificiais, porém simples de entender. Aqui vamos mesclar um pouco de conceitos gerais juntamente com os conceitos da linguagem. Indicaremos quando o conceito for geral, ou seja, aplicável a qualquer linguagem de programação, e quando for um conceito específico do Python.

## Conceitos Iniciais

### Código-fonte

*Conceito Geral*

O _código-fonte_, do inglês _source code_, é o código que você, programador, escreveu. O código-fonte é escrito em alguma linguagem de programação. Não importa qual seja, o nome é código-fonte para todas. Como estamos tratando de Python, especificamente, é o código que você escrever. 

O código-fonte é escrito em uma linguagem de programação que é inteligível pelo ser humano. Na verdade, o seu computador só entende código binário. É muito mais legível você ler algo que faz sentido do que um amontoado de zeros e uns, que precisam de algum tipo de tradução para fazer sentido. No nosso caso especial, o código-fonte é escrito em texto puro usando a linguagem Python.

### Compilador

*Conceito Geral*

O _compilador_ é, de um ponto-de-vista simplista, o responsável por traduzir o código-fonte em linguagem de máquina. Obviamente que um compilador faz muito mais do que só o trabalho de tradução: ele verifica se o que você escreveu está de acordo com as regras de sintaxe, tenta buscar todos os arquivos que fazem parte do seu programa, avalia alguma expansão de texto que seja necessária e por aí vai. Como não é intenção criar um compilador, mas entender que há um para Python, é interessante entender, pelo menos o conceito.

*Conceito Específico*

Por ser uma linguagem interpretada, não á um compilador no sentido lato da palavra para Python. Na verdade, as funções do compilador são acumuladas pelo intérprete. O intérprete realiza a compilação para um formato intermediário, chamado de _byte code_ que é o formato compreendido pelo intérprete. Este formato é independente de plataforma e pode ser fornecido diretamente ao intérprete. 

Normalmente, basta fornecer o seu código-fonte ao intérprete. Isto basta.

### Intérprete

*Conceito Geral*

O _intérprete_ é um software especialista que interpreta e executa as instruções de uma determinada linguagem de programação. No caso do Python, o intérprete é responsável por avaliar o seu código quanto às regras de sintaxe e executá-lo efetivamente, criando o seu programa. A principal vantagem da linguagem interpretada, como o Python, é a possibilidade de executar seu código em diversas plataformas sem a necessidade de reescrevê-lo. Basta portar o intérprete para outra plataforma que o seu programa estará disponível naquela plataforma também.

### Espaço Significativo

*Conceito Específico*

Python é uma linguagem que usa o conceito de _espaço significativo_. Isto quer dizer que todo espaço _antes_ de uma instrução é importante e tem um significado. O espaço determina o agrupamento de código, o que chamamos de blocos de código. Estes agrupamentos determinam o escopo das instruções e isto é muito importante. 

> **Nota**
> 
> Esta é uma meia-verdade. Muitas vezes uma plataforma tem características tão únicas que mesmo havendo o intérprete disponível nela é necessário escrever código específico para ela. Porém, de forma geral, o conceito é verdadeiro.

## Python (finalmente)

Depois de todo este blábláblá, finalmente vamos falar de Python. Aqui já sabemos que Python é uma linguagem interpretada e que o código-fonte é fornecido diretamente ao intérprete para que seja executado. Mas é preciso salvar o seu código-fonte em algum lugar. O arquivo no qual o seu código-fonte é salvo é chamado de _módulo_.

O módulo é um arquivo texto comum cuja extensão é `.py`.  Imagine que você criou um programa de envio de emails e salvou o seu código no arquivo `mail.py`. Pela convenção da linguagem, `mail` é o nome do módulo. Você coloca em um módulo uma miscelânea de declarações e definições. E isto é o seu programa.

Ao contrário de outras linguagens de programação, Python não exige que você crie um ponto de entrada para o seu programa. Por exemplo, a linguagem C exige que o ponto de entrada do programa seja uma função chamada `main`. Java exige que você crie um método estático chamado `main` que tem uma assinatura específica. Python não exige nada disso. O ponto de entrada do seu programa é problema seu, não da linguagem.

Seu programa começa em um módulo. Qualquer um. Você é quem decide qual será o módulo que será o ponto de entrada do seu programa. O que estiver dentro do módulo é o que será executado pelo intérprete. 

Aqui está um programa que foi salvo no módulo _fib.py_: 

```python
# Exemplo de programa escrito em Python
# Crédito: Python Tutorial
# https://docs.python.org/3/tutorial/modules.html

import sys

def fib(n):    
    a, b = 0, 1
    while a < n:
        print(a, end=' ')
        a, b = b, a+b
    print()

if __name__ == "__main__":
    if len(sys.argv) == 1:
        print("Uso: fib <número inteiro positivo>")
    else: 
        n = int(sys.argv[1])
        if n < 0:
            n *= -1
        fib(n)
```

Este programa calcula uma [série de Fibonacci](https://pt.wikipedia.org/wiki/Sequ%C3%AAncia_de_Fibonacci). Os detalhes da implementação não são importantes agora. O importante é ter em mente que isto é um programa Python que foi salvo dentro do módulo `fib.py`. Mas, como faço para executar este programa? Para fazer isto, você precisa dizer ao intérprete Python como achar seu módulo. Na linha de comando do seu computador, execute o programa:

```shell
python fib.py
```

A resposta será `Uso: fib <número inteiro positivo>`. Para ver uma série de verdade, experimente o seguinte:

```shell
python fib.py 10
```

Você deverá obter como resposta algo assim: `0 1 1 2 3 5 8`.

### A Linha de Comando

Para executar um módulo como um programa, a sintaxe da linha de comando é basicamente esta:

```shell
python módulo.py arg1 arg2 arg3
```

- `python` é o interpretador Python
- `módulo.py` é o nome do arquivo no qual você salvou seu programa. A rigor, é o nome do _módulo_.
- `arg1 arg2 arg3` são os argumentos de linha de comando do seu programa. No nosso caso, usamos apenas um único argumento.

Observe que o código de exemplo não tem nenhuma função _main_ ou qualquer outro ponto de entrada definido. Há uma definição de função (instrução _def_) e uma estrutura _if_ seca no meio do código. Não se preocupe ainda comos detalhes deste código.

> **Dica**
>
> Tente digitar e executar este programa. Não deixamos o programa disponível para download por que é preciso sentir a dificuldade imposta pela indentação. Se você não tomar cuidado, seu programa não vai fazer o que você espera por que você não adicionou os espaços corretamente ao início das linhas.
