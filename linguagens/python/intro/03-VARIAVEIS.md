# Variáveis

Uma _variável_ é um conceito curioso das linguagens de programação. O que vamos
discutir aqui é válido para toda e qualquer linguagem e adapta-se perfeitamente
ao Python. Obviamente que o Python tem formas específicas de tratar variáveis,
conforme veremos.

Conceitualmente, uma _variável_ é um espaço de armazenamento temporário. Mas, o
que isto quer dizer? De uma forma geral, todo processamento realizado por um
programa precisa armazenar, temporariamente, resultados parciais para que o
processamento seja realizado. Por exemplo, se criarmos um programa que calcula a
quantidade de dias entre a data do seu nascimento e o dia de hoje, será
necessário armazenar a data do seu nascimento, a data de hoje e a quantidade de
dias decorridos em algum lugar. Este _algum lugar_ é uma variável.

## Variáveis têm tipos

Outro conceito comum é o do _tipo_: toda variável é de um tipo. Para entender
este conceito, vamos imaginar que você tenha uma transportadora de carros que
leva carros a uma concessionária de veículos. Imagine que o seu caminhão
carregue todos os _tipos_ de veículos: motos, _scooters_, automóveis,
caminhonetes e caminhões. O _espaço_ onde cabem os veículos são as _variáveis_:
a cada momento há um _valor_ diferente. Porém, no espaço onde cabe uma moto não
cabe uma _scooter_ nem uma caminhonete. Ou seja, o espaço (variável) só permite
armazenar um determinado tipo de veículo (tipo de dado).

Assim, uma variável tem, associada a ela, um tipo muito bem determinado. Por
exemplo:

```python
name = "Asdrúbal Vallermo"
print(name)
```

A variável _name_ é uma _cadeia de caracteres_ cujo valor é *Asdrúval
Vallermo*. Se executarmos este pequeno programa, veremos o valor contido em
_name_ ser colocado na tela do computador.

## Definição de Variáveis

Toda variável, antes de ser utilizada, precisa ser formalmente definida. Este
conceito é igualmente válido para Python. Se você tentar executar a seguinte
instrução:

```python
print(name)
```

Verá algo parecido com o seguinte:

```shell
>>> print(name)
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
NameError: name 'name' is not defined
```

Para fazer uso de uma variável é necessário definí-la. E como se define uma
variável em Python? Já vimos isso! O primeiro exemplo, no qual definimos a
variável _name_ com o valor _"Asdrúval Vallermo"_ é uma definição de
variável. Porém, existem alguns detalhes muito importantes, fruto da forma como
o Python funciona.

### Tipagem Dinâmica

Python é uma linguagem de _tipagem dinâmica_. Isto quer dizer que uma variável
tem o seu tipo determinado no momento em que um valor lhe é atribuído. Veja o
exemplo abaixo:

```python
name = "Asdrúbal Vallermo"
name = 10
name = 123.4
name = [1, 2, 3, 4, 5]
```

Neste exemplo, a variável _name_ assume os tipos _string_, número inteiro,
número de ponto flutuante e lista de números inteiros, respectivamente. A
variável é a mesma. Porém, o conteúdo varia _dinamicamente_ de tipo. Por isso
Python é chamada de _linguagem de tipagem dinâmica_.

> **Nota**
>
> Apesar de ser possível fazer com que uma variável seja reaproveitada com tipos
> diferentes no mesmo escopo, esta é uma péssima ideia. Imagine que em um código
> extenso você resolva reaproveitar o nome da variável para tipos diferentes de
> informação. A manutenção disso será terrível! É uma boa prática ser
> consistente, ou seja, se você definir uma variável como sendo de um tipo,
> procure armazenar dados somente deste tipo na variável. Apesar da linguagem
> permitir usar qualquer tipo diferente sob o mesmo nome no mesmo escopo, esta é
> uma péssima ideia.

### Tipagem Estática

Apesar do nosso foco ser a linguagem Python, é importante discorrer sobre a
tipagem estática. Linguagems como C, C++ e Swift são linguagens de tipagem
estática. O que isso quer dizer? Isto quer dizer que ao definir uma variável
como sendo de um determinado tipo é impossível usar esta variável com tipos
diferentes ser receber algum tipo de reclamação do compilador. Por exemplo, um
pequeno código em _swift_:

```swift

var name = "Asdrúbal Vallermo"
name = 5
```

Este trecho de código sequer compila. A tentativa de atribuir-se 5 à variável
_name_ termina com um belo erro de compilação. Ou seja, você será incapaz de
gerar algo que o computador possa executar. Em _swift_, uma vez definida uma
variável de um determinado tipo, este tipo permanece _estático_ dentro do escopo
de definição da variável.

## Escopo de definição

Já que falamos nisso, é importante definir o que é um _escopo de definição_. O
escopo de definição determina _onde_ uma variável pode ser utilizada. Quando
você define uma variável dentro de um _módulo_, esta variável pode ser
referenciada do ponto onde foi definida adiante. Mas para que sua definição seja
válida, é preciso que a mesma seja _executada_. Por exemplo:

```python
x = 10
if x == 10:
    y = 30
print(y)
```

A variável _y_ foi definida dentro do bloco da instrução _if_, que veremos
adiante. Por enquanto, aceite apenas que a instrução `y = 30` é efetivamente
executada. Assim, _y_ é definida e a função _print_ funciona normalmente,
colocando o valor _30_ na tela. Porém, este código apresentará erro:

```python
x = 40
if x == 10:
    y = 30
print(y)
```

Neste caso o erro ocorre por que _y_ não é definida por que a instrução dentro
do _if_ não é executada.

O importante aqui é entender que _se a definição não for executada pelo
intérprete, a variável não se torna definida_. À partir do momento no qual a
variável é definida dentro de um determinado escopo, ela se torna disponível
dentro deste escopo. O código abaixo também não funciona:

```python

def func():
    y = 40
func()
print(y)
```

Apesar da instrução `y = 40` ser efetivamente executada, ela acontece em _escopo
diferente_ da chamada da função _print_.

> **Nota**
>
> Não se preocupe se a ideia de _escopo_ parece confusa neste momento. Ainda não
> estudamos as funções, as classes e os métodos. É importante, neste momento,
> que você saiba que a definição de uma variável está condicionada ao escopo
> onde ela acontece. Mais adiante, depois que estudarmos outros conceitos da
> linguagem, retornaremos ao conceito de escopo para solidificá-lo.

## Tipos de Dados

Falamos, até aqui, de maneira muito abstrata sobre os tipos de dados. Até aqui
já sabemos que Python é uma linguagem de tipagem dinâmica e já entendemos o que
isto quer dizer. Mas, quais são os tipos de dados suportados pela linguagem?

### Números

Vamos começar pelos números. Python suporta os seguintes tipos numéricos:

* Inteiros
* Booleanos
* Ponto flutuante
* Números complexos

#### Números Inteiros e Booleanos

Python considera os números inteiros e os valores booleanos como tipos numéricos
inteiros. Os números inteiros não tem limite de tamanho, estando limitados ao
tamanho da memória disponível para o intérprete Python. Os números booleanos
suportam apenas dois valores: _True_ ou _False_.

Os números inteiros negativos são representados por [complementos de
dois](https://pt.wikipedia.org/wiki/Complemento_para_dois). A representação
básica dos números, para fins de operações __bitwise__, é binária. Aqui estão
alguns exemplos de literais e seus usos:

```python
3
x = False
a = 45
```

#### Números de ponto flutuante

Python suporta somente números de precisão dupla. Não existem números de
precisão simples. Os projetistas da linguagem acharam por bem manter apenas um
tipo numérico por questões de simplicidade. 

```python
y = 3.14
z = 2.718
```

#### Números complexos

Sim! Python suporta os números complexos! Os números complexos têm dois
componentes e são muito úteis em cálculo vetorial.

```python
cpx = (1+5j)
```

> **Nota**
>
> Apesar de alguns livros-texto utilizarem a letra _i_ para representar a parte
> imaginária de um número complexo, python utiliza a letra _j_. Tentar usar
> outra letra ocasiona em um erro de sintaxe.

< [Estrutura](02-CONSTANTES.md) | [Próximo Tópico: Expressões](04-EXPRESSOES.md) >
