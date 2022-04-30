<img src="https://i.imgur.com/FrYitaj.png"> 

<p>

**Autor:**
  <a href="https://github.com/JosManoel">Manoel Freitas</a>
</p>

Durante o desenvolvimento de aplicações, comumente nos encontramos necessitando de novas funcionalidades que não foram definidas originalmente na linguagem utilizada. Seja para lidar com dados de diferentes formas ou para realizar cálculos complexos, por mais que uma linguagem possua diversos recursos, ela não conseguirá suprir todas as necessidades nativamente. Por isso, para otimizar a criação de aplicações, recorremos a complementos pré-fabricados, denominados **bibliotecas**.

***
<h2 id="sumario">🧮 Sumário</h2>
 
  * <a href="#O_que_e_uma_biblioteca">O que é uma biblioteca ?</a>
  * <a href="#Utilizando_bibliotecas_no_Dart">Utilizando bibliotecas no Dart</a>
    * <a href="#Importando_uma_biblioteca">Importando uma biblioteca</a>
    * <a href="#Importação seletiva">Importação seletiva da biblioteca</a>
    * <a href="#Nomeando_bibliotecas">Nomeando bibliotecas com library prefix</a>
  * <a href="#Bibliotecas_dart">Principais bibliotecas internas do Dart</a>
  * <a href="#leitura_e_link">📚 Leitura e links recomendado</a>
  * <a href="#licenca">🧾Licença</a>

***

<h2 id="O_que_e_uma_biblioteca">O que é uma biblioteca ?</h2>


As bibliotecas, em resumo são apanhados de funções destinadas a uma aplicação específica, contando com rotinas e instruções criadas para agilizar o desenvolvimento, como a biblioteca **math()**, que traz novas funções matemáticas, como o cálculo de raiz quadrada.

A principal vantagem em sua utilização está na possibilidade de utilizar uma programação modular, através das funções pré-definidas, reduzindo os possíveis erros de sintaxe e o retrabalho de definir todas as funções necessárias, além de facilitar a atualização de diversas funcionalidades.


<p align="right">
    <a href="#sumario">
        <img src="https://raw.githubusercontent.com/JosManoel/Dart-Study/main/images/icons/voltar_ao_topo.png" height="32">
    </a>
</p>

***

<h2 id="Utilizando_bibliotecas_no_Dart">Utilizando bibliotecas no Dart</h2>

A utilização de uma biblioteca no Dart é bastante semelhante à utilização em outras linguagens, como o C ou Java, em que é necessário importá-las para a sua aplicação antes de utilizá-las. No Dart, esta função pode ser executada de diversas formas, importando uma biblioteca por inteiro, apenas a parte desejada ou excluindo itens desnecessários.

Para importar uma biblioteca, o ecossistema Dart, que inclui o Flutter, utiliza pequenos arquivos responsáveis por agrupar conjuntos de funções que constituem as bibliotecas, denominados packages. De maneira direta, um package, ou pacote, no Dart pode ser tratado como um diretório responsável por armazenar as funções e ferramentas de uma biblioteca, constituído por, no mínimo, um arquivo _**pubspec.yaml**_ que atribui alguns de seus metadados, como o nome, a versão e a descrição da ferramenta. Um bom exemplo de sua utilização está no desenvolvimento com Flutter, onde o _**pubspec.yaml**_ é responsável por delimitar informações importantes a respeito do app, como a versão do sdk e o nome do app. 

Um package possui outras inúmeras funções importantes, como o gerenciamento de pacotes criados pela comunidade  e a utilização de dependências, mas para este tópico, iremos nos restringir apenas ao seu uso para importação de bibliotecas. Caso queira aprofundar seu conhecimento a respeito do [packages](https://dart.dev/guides/packages) e do [pubspec](https://dart.dev/tools/pub/pubspec), visite sua documentação.

<h2 id="Importando_uma_biblioteca">Importando uma biblioteca</h2>

Para utilizar alguma função de uma determinada biblioteca, primeiro devemos importá-la para o nosso projeto. A importação acontece de maneira bastante simples, seguindo esta sintaxe:

~~~dart
import 'dart:library';
~~~

No entanto, esta sintaxe não serve para bibliotecas de um package diferente do **package dart**, sendo necessário utilizar um método um pouco diferente:

~~~dart
import 'package:URI';
~~~

> O URI, traduzido como "Identificador Uniforme de Recursos", é funciona como um "link" que aponta para um recurso, seja ele um arquivo de texto ou uma imagem. No nosso caso, o URI é o diretório da biblioteca.

Como exemplo de implementação, utilizaremos a biblioteca **math()**, que é bastante utilizada para funções matemáticas, para gerar números aleatórios que representam o índice de um card da lista.


<h3 align="center">Utilização de bibliotecas em Dart</h3>

~~~dart
//Importando a biblioteca math
import 'dart:math';

void main() {
  var yugiStarterDeck = [
    "Dragon Zombie", 
    "Dark Magician", 
    "Summoned Skull",
    "Mystical Elf",
    "Celtic Guardian",
    "Dark Hole",
    "Trap Hole",
    "Monster Reborn",
    "Waboku",
    "Yami",
    "Feral Imp"
  ];
  
  //Printando cards do deck
  print("Mão inicial");
  print("card 1: " + yugiStarterDeck[Random().nextInt(10)]);
  print("card 2: " + yugiStarterDeck[Random().nextInt(10)]);
  print("card 3: " + yugiStarterDeck[Random().nextInt(10)]);
  print("card 4: " + yugiStarterDeck[Random().nextInt(10)]);
  print("card 5: " + yugiStarterDeck[Random().nextInt(10)]);

}
~~~

<p align="center">
    <a href="https://dartpad.dev/?id=5ecb54426ebfe479016228702452b0a7">
        <img src="https://i.imgur.com/AlXZxsv.png" height="24">
    </a>
</p>

> Tente clicar no botão "Run" várias vezes para observar os cards mudando. Esta é uma das funções da biblioteca **math()**, que será abordada posteriormente.

<p align="right">
    <a href="#sumario">
        <img src="https://raw.githubusercontent.com/JosManoel/Dart-Study/main/images/icons/voltar_ao_topo.png" height="32">
    </a>
</p>

<h2 id="Importação seletiva">Importação seletiva da biblioteca</h2>

Apesar de já está funcional, perceba que no código anterior a biblioteca **math** inteira foi importada, incluindo todas as suas constantes, classes e funções. Essa abordagem pode trazer alguns problemas de nomeação caso esteja utilizando mais uma biblioteca, já que bibliotecas diferentes podem ter funções diferentes com o mesmo nome, causando conflitos nas chamadas.

Para solucionar este caso, o Dart possui alguns recursos, como a importação seletiva da biblioteca, que funciona utilizando dois métodos: o **show** e o **hide**.

Com o método **show** é possível importar apenas a função desejada de uma função, eliminando todas as outras. Sua sintaxe é bem simples e segue o seguinte exemplo:

~~~dart
import 'dart:library' show function;
import 'package:URI' show function;
~~~

Já o método **hide** é utilizado para excluir uma função da importação. Pode ser bastante útil quando temos apenas uma função conflitante entre duas bibliotecas importadas. Sua sintaxe é semelhante ao método anterior:

~~~dart
import 'dart:library' hide function;
import 'package:URI' hide function;
~~~

<h3 align="center">Bibliotecas - importação seletiva</h3>

~~~dart
//Importando apenas o Random da biblioteca math
import 'dart:math' show Random;

void main() {
  var yugiStarterDeck = [
    "Dragon Zombie", 
    "Dark Magician", 
    "Summoned Skull",
    "Mystical Elf",
    "Celtic Guardian",
    "Dark Hole",
    "Trap Hole",
    "Monster Reborn",
    "Waboku",
    "Yami",
    "Feral Imp"
  ];
  
  //Printando cards do deck
  print("Mão inicial");
  print("card 1: " + yugiStarterDeck[Random().nextInt(10)]);
  print("card 2: " + yugiStarterDeck[Random().nextInt(10)]);
  print("card 3: " + yugiStarterDeck[Random().nextInt(10)]);
  print("card 4: " + yugiStarterDeck[Random().nextInt(10)]);
  print("card 5: " + yugiStarterDeck[Random().nextInt(10)]);

}
~~~

<p align="center">
    <a href="https://dartpad.dev/?id=22d0c6dea728ed187d53ac9894450ee9">
        <img src="https://i.imgur.com/NsCFvBX.png" height="24">
    </a>
</p>

> Experimente trocar o "show" pelo "hide" e observe a saída do console.

<p align="right">
    <a href="#sumario">
        <img src="https://raw.githubusercontent.com/JosManoel/Dart-Study/main/images/icons/voltar_ao_topo.png" height="32">
    </a>
</p>

<h2 id="Nomeando_bibliotecas">Nomeando bibliotecas com library prefix</h2>

O Dart também dispoêm de outro método para realizar a diferenciação entre as funções de bibliotecas chamado _**"library prefix"**_. Este método funciona como um apelido para a biblioteca e é indicado para situações onde é necessário manter funções com o mesmo nome, mas com funcionalidades diferentes. Sua sintaxe segue o exemplo dos métodos anteriores, sendo da seguinte forma:

~~~dart
import 'dart:library' as prefix;
import 'package:URI' as prefix;
~~~

A utilização das funções de uma biblioteca nomeada com o library prefix também sofre algumas mudanças, sendo necessário informar o nome da biblioteca antes de utilizar a função desejada, seguindo o exemplo:

~~~dart
prefix.Function();
~~~

<h3 align="center">Utilizando o método library prefix</h3>

~~~dart
//Nomeando a biblioteca math como "card"
import 'dart:math' as card;

void main() {
  var yugiStarterDeck = [
    "Dragon Zombie", 
    "Dark Magician", 
    "Summoned Skull",
    "Mystical Elf",
    "Celtic Guardian",
    "Dark Hole",
    "Trap Hole",
    "Monster Reborn",
    "Waboku",
    "Yami",
    "Feral Imp"
  ];
  
  //Printando cards do deck
  print("Mão inicial");
  print("card 1: " + yugiStarterDeck[card.Random().nextInt(10)]);
  print("card 2: " + yugiStarterDeck[card.Random().nextInt(10)]);
  print("card 3: " + yugiStarterDeck[card.Random().nextInt(10)]);
  print("card 4: " + yugiStarterDeck[card.Random().nextInt(10)]);
  print("card 5: " + yugiStarterDeck[card.Random().nextInt(10)]);

}
~~~

<p align="center">
    <a href="https://dartpad.dev/?id=f444a66320ad83307e3f1e55d60c0fbb">
        <img src="https://i.imgur.com/pf885CG.png" height="24">
    </a>
</p>

> Este método também pode ser bastante útil para manter seu código legível e coeso.

<p align="right">
    <a href="#sumario">
        <img src="https://raw.githubusercontent.com/JosManoel/Dart-Study/main/images/icons/voltar_ao_topo.png" height="32">
    </a>
</p>


***

<h2 id="Bibliotecas_dart">Principais bibliotecas internas do Dart</h2>

O Dart, por padrão, disponibiliza um conjunto de bibliotecas que auxiliam no desenvolvimento de diversas aplicações, indo de funções matemáticas a manipulação de gráficos vetoriais (.svg) e elementos de I/O. Boa parte dessas bibliotecas são utilizadas com maior frequência no desenvolvimento com o framework Flutter, mas algumas delas são bastante importantes para aplicações em Dart e a leitura de suas documentações é recomendada.

|Biblioteca      | Descrição                                         | Documentação|
|----------------|---------------------------------------------------|-------------|
| dart:math      | Biblioteca para utilização de funções matemáticas complexas. | [math library](https://api.dart.dev/stable/2.16.2/dart-math/dart-math-library.html)|
| dart:io        | Tratamento de arquivos, entradas HTTP e suporte a outros elementos de I/O. | [io library](https://api.dart.dev/stable/2.16.2/dart-io/dart-io-library.html)|
| dart:core      | Um conjunto complexo de tipos, coleções, funções e outras funcionalidades para o desenvolvimento em Dart. | [core library](https://api.dart.dev/stable/2.16.2/dart-core/dart-core-library.html)|
| dart:convert   | Ferramentas de codificação e descodificação para a conversão de diferentes formatos de dados, incluindo o JSON.| [convert library](https://api.dart.dev/stable/2.16.2/dart-convert/dart-convert-library.html)|
| dart:type_data | Biblioteca com métodos definidos para o trabalho com dados de tamanho fixo e outros tipos numéricos. | [typed_data library](https://api.dart.dev/stable/2.16.2/dart-typed_data/dart-typed_data-library.html)|

> Outras bibliotecas e packages podem ser encontrados no repositório oficial do Dart [pub.dev](https://pub.dev/).

<p align="right">
    <a href="#sumario">
        <img src="https://raw.githubusercontent.com/JosManoel/Dart-Study/main/images/icons/voltar_ao_topo.png" height="32">
    </a>
</p>


***

<h2 id="leitura_e_link">📚 Leitura e links recomendado</h2>


* [🎯 DART - BIBLIOTECAS](https://acervolima.com/dart-bibliotecas/)
* [🎯 Dart Programming - Libraries](https://www.tutorialspoint.com/dart_programming/dart_programming_libraries.htm#:~:text=A%20library%20in%20a%20programming,typedefs%2C%20properties%2C%20and%20exceptions.)
* [🎯 The pubspec file](https://dart.dev/tools/pub/pubspec)
* [🎯 How to use packages](https://dart.dev/guides/packages)
* [🎯 Creating packages](https://dart.dev/guides/libraries/create-library-packages)
* [🎯 A tour of the Dart language - Libraries and visibility](https://dart.dev/guides/language/language-tour#libraries-and-visibility)
* [🎯 Video: Bibliotecas em Dart- Curso de Gratuito de DART](https://www.youtube.com/watch?v=PcAIFJxiimo)

<p align="right">
    <a href="#sumario">
        <img src="https://raw.githubusercontent.com/JosManoel/Dart-Study/main/images/icons/voltar_ao_topo.png" height="32">
    </a>
</p>

***

<h2 id="licenca">🧾Licença</h2>

Este projeto está sob a licença [Apache 2.0](https://github.com/JosManoel/Dart-Study/blob/main/LICENSE).

<p align="right">
    <a href="#sumario">
        <img src="https://raw.githubusercontent.com/JosManoel/Dart-Study/main/images/icons/voltar_ao_topo.png" height="32">
    </a>
</p>
