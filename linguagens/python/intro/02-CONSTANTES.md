# Constantes e Literais

Para iniciar nossos estudos em Python é preciso que falemos inicialmente de valores _literais_ e das _constantes_. É importante ter em mente que estes conceitos são cabíveis a qualquer linguagem de programação. 

Por definição, uma _constante_ representa um valor de um determinado tipo, não podendo ter sua representação alterada depois de criada. Isto quer dizer que se você define uma constante como contendo o valor 5, o valor desta constante será 5 não importa o que você faça. 

Também por definição, um _literal_ é uma representação de um valor de um determinado tipo. A diferença do literal com relação à constante é que a constante é uma característica intrínseca da linguagem de programação, enquanto a constante é criada pelo programador. Vamos aos exemplos!

```python
PI = 3.14
```

Neste exemplo criamos uma constante chamada PI que representa o valor _literal_ 3, 14. Entendeu a diferença entre constante e literal? O literal é determinado pela linguagem de programação. Assim, o número 3.14 é um literal e PI é uma constante, visto que a constante foi criada pelo programador.

> **Nota**

> Não existem constantes em Python. 😱

Mas... Hein? Como assim?

Python é uma linguagem cujo _design_ objetivou a simplicidade. Assim sendo, os projetistas da linguagem acharam por bem não diferenciar variáveis de constantes pela dor-de-cabeça que é tentar manter as constantes imutáveis depois de definidas. Assim, sintaticamente não existem constantes em Python. O que isto quer dizer?

Isto quer dizer que a linguagem não permite construções explícitas para determinação de constantes. Trocando em miúdos, o último exemplo é, na verdade, a definição de uma variável. Não se preocupe se você ainda não sabe o que é uma variável. Veremos as variáveis com detalhes adiante. Por hora, preocupe-se em saber que uma variável pode ter seu valor interno alterado. 

## Convenção

Apesar de Python não suportar constantes sintaticamente, convencionou-se que variávies cujos nomes estão em maiúsculas, com partes separadas pelo caractere sublinhado e definidas no nível do módulo (veja [PEP 8](https://www.python.org/dev/peps/pep-0008/) para mais detalhes). Assim, são exemplos de constantes:

```python

PI = 3.14
MAX_CONCURRENT_PROCESSES = 1032
```

Vale dizer, antes de continuar, que as convenções do Python são documentadas como PEPs, do inglês _Python Enhancement Proposal_, ou proposta de melhoramento do python em tradução livre. São textos técnicos mantidos pela Python Foundation que descrevem boa práticas e características técnicas da linguagem. Você pode ler estes [textos aqui](https://www.python.org/dev/peps/).

A convenção não é uma obrigação. Se assim o fosse, chamaria-se regra. A convenção é uma sugestão de adoção que visa estabelecer um linguajar único para que todos possam comunicar-se adequadamente. Apesar de não ser obrigatória, deixar de seguir uma convenção é uma péssima ideia pois pode trazer efeitos indesejáveis principalmente se você estiver escrevendo código com uma equipe de desenvolvimento.

Assim, se você for definir uma constante no seu programa, lembre-se de seguir a PEP 8: declare-a a nível de módulo e com letras maiúsculas, separando as partes por sublinhados. E, o mais importante, uma vez definida não atribua nada à ela. Como Python não define constantes sintaticamente, é importante que você não saia redefinindo o valor de uma constante pois isto pode criar uma infinidade de dores-de-cabeça. 

## Literais

A diferença entre uma constante e um literal é simples: você não pode atribuir nada a um literal. A constante você atribui seu valor inicial e este valor permanece assim durante toda a execução do seu programa. Veja os exemplos:

```python
"Asdrúbal Vallermo"
123
123.4
[1, 2, 3, 4]
(4, 5, 6)
```

Todos são exemplos de literais, respectivamente: string, número inteiro, número de ponto flutuante, lista de inteiros e uma tupla. Estas representações não inventei da minha mente doentia. São representações criadas pelo projetista da linguagem. Por enquanto não se preocupe com o significado de listas e tuplas. Veremos cada um destes itens com profundidade mais adiante.

Como dito, se você tentar atribuir algo a um literal, ganhará um belo erro:

```shell
>>> 123 = "roberto"
  File "<stdin>", line 1
SyntaxError: can't assign to literal
```

< [Estrutura](01-ESTRUTURA.md) | [Próximo Tópico: Variáveis](03-VARIAVEIS.md) >


