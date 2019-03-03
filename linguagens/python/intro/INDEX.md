# Introdução à Programação em Python

Python é uma linguagem criada por Guido van Rossum em 1991. O principal foco da linguagem é a legibilidade, legibilidade esta conseguida com o uso de espaços em branco significativos. É uma linguagem interpretada, o que significa dizer que é necessária a presença de um _intérprete_ para que programas escritos nesta linguagem possam executar em um computador. Com o fim de sintetizar as características da linguagem, aqui está uma lista bem resumida delas:

- imperativa: Python é imperativa, ou seja, o programador determina não só as instruções que precisam ser executadas mas, também, a ordem na qual devem ser executadas;
- tipagem dinâmica: os tipos de dados são verificados durante a execução do programa e não durante a compilação; Isto permite uma série de construções que são bem difíceis de criar em linguagens de tipagem estática como a linguagem C;
- multi-paradigma, pois você pode escrever código procedural, orientado ao objeto ou funcional;
- interpretada, pois é preciso um software especista chamado _intérprete_ que cuida da verificação sintática do código, conversão em _byte code_ e, por fim, da execução do mesmo. 

Uma das características do Python é justamente um código com alto grau de legibilidade. Além disso, o código tende a ficar mais compacto. Veremos estas características ao longo do texto.

## Antes de Começar

Este material foi escrito tendo em mente a leitura sequencial. Tentar pular um capítulo não é uma boa ideia, pois alguns conceitos são necessários e são tratados no decorrer do texto. Tenha paciência!

O texto foi criado com o intuito de ensinar dois tópicos na realidade: como programar e a linguagem Python. Programar é algo independente da linguagem de programação e os conceitos aplicam-se a virtualmente toda linguagem de programação já inventada. Escrever código em Python exige o conhecimento da sintaxe e da semântica da linguagem, especificamente. 

> **Dica**
>
> Saber uma linguagem de programação não faz ninguém programador. Existe muito mais a aprender do que somente a linguagem. Sempre que possível este material adicionará links úteis para outros textos e livros valiosos para que você possa aprofundar seus conhecimentos em desenvolvimento de software. 

## Aquecimento

Antes de continuar, é preciso instalar algum software no seu computador para que você possa não só criar programas, mas tambémn executá-los e depurá-los. Alguns softwares são apenas recomendações, mas outros são obrigatórios.

### Editor de textos

Você precisará de um bom editor de textos. Existem diversos no mercado, mas alguns têm ganhado destaque nos últimos anos. Todos são gratuitos.

- [Atom](https://atom.io/)
- [VSCode](https://code.visualstudio.com/)
- [Notepad++](https://notepad-plus-plus.org/)
- [Crimson Editor](http://www.crimsoneditor.com/)
- [Vim](https://www.vim.org/)
- [Emacs](https://www.gnu.org/software/emacs/)

Se você já usa algum editor de textos e já está habituado com ele, continue usando-o. É preciso que ele permita editar código em texto plano, de preferência codificado em UTF-8.

> **Dica**
>
> Não importa qual editor de textos você decida usar para editar seus programas. Procure um com o qual você se sinta à vontade e domine-o. Leia a documentação, aprenda a customizá-lo. No futuro, isto fará diferença na sua produtividade enquanto programador.

### Intérprete Python

O intérprete Python é essencial. Sem ele não há como executar nenhum programa escrito em Python. A melhor fonte de downloads do intérprete é [o site da Python Foundation](https://www.python.org/downloads/). Sugere-se o uso da versão 3.7 ou superior pelo suporte a UTF-8. Hoje em dia tornou-se impraticável escrever código em multibyte ou ASCII dada a necessidade de internacionalização.

Se você tem dificuldades em entender inglês, aqui estão alguns links com downloads sugeridos do intérprete Python:

- [Windows 32 bits](https://www.python.org/ftp/python/3.7.2/python-3.7.2.exe)
- [Windows 64 bits](https://www.python.org/ftp/python/3.7.2/python-3.7.2-amd64.exe)
- [macOS](https://www.python.org/ftp/python/3.7.2/python-3.7.2-macosx10.9.pkg)

Se você utiliza alguma distribuição linux, procure na documentação como realizar o download e instalação através do seu gerenciador de pacotes. Porém, se você for um _hardcore linuxer_, você pode [baixar os fontes](https://www.python.org/ftp/python/3.7.2/Python-3.7.2.tgz), compilar e instalar no braço. A forma mais simples ainda continua sendo instalar pelo seu gerenciador de pacotes favorito.

Quem usa macOS também tem a opção de usar o [Homebrew](https://brew.sh/index_pt-br) para instalar o intérprete.

> **Dica**
>
> Gaste o tempo que achar necessário lendo a documentação de como instalar o intérprete no seu ambiente. Isto é muito valioso para o correto _setup_ do seu ambiente. 

Para saber se o intérprete foi corretamente instalado, abra um _prompt de comando_ e execute a seguinte linha:

```shell
python --version
```

Você deverá ver algo parecido com o texto abaixo. O conteúdo deve variar dependendo da sua plataforma. 

```shell
Python 3.7.2
```

Se você leu a informação de versão do Python, maravilha! Estamos prontos para começar!

> **Dica**
>
> Não importa qual shell você utiliza. Se você gosta do Powershell, do Bourne Again Shell (bash), Korn Shell, C Shell, Bourne Shell, não importa. Domine-o. Todo shell oferece a possibilidade de automação do ambiente que é algo extremamente útil no dia-a-dia do programador. 

< [Voltar](/learn/linguagens/INDEX.html) | [Próximo Tópico: Estrutura da Linguagem](01-ESTRUTURA.md) >
