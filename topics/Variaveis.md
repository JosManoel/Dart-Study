<img src="https://i.imgur.com/gsrNCJY.png"> 

<p>

**Autor:**
  <a href="https://github.com/JosManoel">Manoel Freitas</a>
</p>


Uma variável é, basicamente, um espaço alocado na memória do computador para armazenar um determinado dado. De certo modo, as variáveis possuem um ciclo de vida dentro do programa, por isso, deve-se tomar cuidado ao utiliza-las, de modo a evitar problemas de declaração ou de overflow. Por ser uma linguagem tipada, as variáveis declaradas em Dart precisam ter o seu tipo informado. No entanto, não é necessário definir o valor da variável quando ela é declarada.


***
<h2>🧮 Sumário</h2>

* <a href="#numbers">Numbers</a>
* <a href="#strings">Strings</a>
* <a href="#runes">Runes</a>
* <a href="#boolean">Boolean</a>
* <a href="#list">List</a>
* <a href="#maps">Maps</a>
* <a href="#sets">Sets</a>
* <a href="#var">Var</a>
* <a href="#dynamic">Dynamic</a>
* <a href="#leitura_e_link">📚 Leitura e links recomendado</a>
* <a href="#licenca">🧾Licença</a>

***

<h2 id="numbers">Numbers</h2>

No Dart temos 3 tipos de variáveis para armazenar valores numéricos, sendo elas int, double e num. O **int**, assim como em outras linguagens, é utilizado para armazenar apenas valores inteiros, tanto os números negativos quanto os positivos. No **double** temos uma pequena semelhança com o tipo **float**, utilizado em outras linguagens. Com o double é possível armazenar números fracionários, comumente chamados de números de ponto flutuante. Já o **num** é um tipo que engloba tanto o int como o double. Deste modo, **uma variável num pode ser tanto int como double**.

<h3 align="center">Declarando variáveis do tipo number</h3>

~~~dart
void main(){
  // Numeros inteiros
  int result = 42;

  // Numeros decimais
  double radio = 98.9;

  // Numeros inteiros OU decimais
  num numero = 1.23;
  num codigo = 123; 
}
~~~

<p align="center">
    <a href="https://dartpad.dev/?id=b3479d6283212aed857c7a38720148eb">
        <img src="https://i.imgur.com/VN7D0R0.png" height="24">
    </a>
</p>

<h2 id="strings">Strings</h2>

As strings, assim como na maioria das linguagens de programação atuais, são responsáveis por armazenar um ou mais caracteres, representada com aspas duplas ou simples. Existem várias maneiras de se trabalhar com strings, seja concatenando ou alterando o valor inicial. Estas e outras funcionalidades serão abordadas posteriormente em ou tópico específico.

<h3 align="center">Declarando Strings</h3>

~~~dart
void main(){
  // Declarando strings com aspas duplas
  String anime1 = " Yu Yu Hakusho";

  //Declarando strings com aspas simples
  String anime2 = 'Ranma 1/2';
}
~~~

<p align="center">
    <a href="https://dartpad.dev/?id=1e5d233625587b9b48caff3b2ca516a0">
        <img src="https://i.imgur.com/mxmUWy2.png" height="24">
    </a>
</p>


> Perceba que na variável anime2, apesar de conter números, eles são tratados com uma string e não como um int. Isso acontece porque estão dentro das aspas.


<h2 id="runes">Runes</h2>

As runas são uma categoria de string com uma importante funcionalidade acrescentada: **Emojis**. Assim como as strings comuns, as runas são uma sequência de caracteres  Unicode, no entanto, diferentemente da string, as runas permitem exibir o código, formando caracteres especiais como símbolos e emojis.

<h3 align="center">Declarando runas</h3>

~~~dart

 void main(){
  Runes computador = Runes("\u1F4BB");

  // para imprimir uma rune é necessário utilizar o "fromCharCodes"
  print(String.fromCharCodes(computador));
  //Resultado: 💻
 }
~~~

<p align="center">
    <a href="https://dartpad.dev/?id=f54369ab70eb32d9f07e6a724df46e8f">
        <img src="https://i.imgur.com/HtYsJfc.png" height="24">
    </a>
</p>

> Esta função pode gerar alguns erros no DartPad.

<h2 id="boolean">Boolean</h2>

Os valores booleanos são declarados utilizando o tipo bool, tendo dois valores possíveis:

* **true** (verdadeiro)
* **false** (falso)

<h3 align="center">Declarando valores booleanos</h3>

~~~dart
void main(){
  // Declarando variaveis booleanas
  bool sol = true;
  bool chuva  = false;
}
~~~

<p align="center">
    <a href="https://dartpad.dev/?id=82fba89944ed62104cc31c0b1331ad2c">
        <img src="https://i.imgur.com/ivTb18f.png" height="24">
    </a>
</p>

O Dart dispõe de uma série de operadores para serem utilizados para comparar valores booleanos.

|Operador | Descrição                                                        |
|---------|------------------------------------------------------------------|
|  ==     | Igual.                                                           |
|  !=     | Diferente.                                                       |
|  >      | Maior.                                                           |
|  >=     | Maior ou igual.                                                  |
|  <      | Menor.                                                           |
|  <=     | Menor ou igual.                                                  |
|  &&     | Operador lógico AND.                                             |
|  \|\|   | Operador lógico OR.                                              |
|  is     | Verifica se o item é do mesmo tipo de outro.                     |
|  !is    | Verifica se o tipo do item é diferente do tipo de outra variável.|

> Estes operadores serão abordados mais profundamente nos tópicos de condicionais.

<h2 id="list"> List</h2>

A list, que recebe o nome de **array** em outras linguagens, é um conjunto de valores ordenados e que possuem um índice. O índice corresponde a uma posição na fila de itens, começando do item 0.

<h3 align="center">Funcionamento do índice</h3>

|Item  |Yu Yu Hakusho|Cowboy Bebop|Trigun|One Piece|Dragon Ball|
|------|-------------|------------|------|---------|-----------|
|Índice|     0       |     1      |  2   |    3    |     4     |


<h3 align="center">Declarando uma variável do tipo List</h3>

~~~dart

void main(){
  // Criando uma List
  var lista_de_animes = ["Yu Yu Hakusho", "Cowboy Bebop", "Trigun", "One Piece", "Dragon Ball"];

  // Imprimindo uma list
  print(lista_de_animes);
  // Saída: Yu Yu Hakusho, Cowboy Bebop, Trigun, One Piece, Dragon Ball.

  // Acessando um item especcifico da list
  // print(list[index]);
  print(lista_de_animes[3]);
  // O resultado é: One Piece.
}
~~~

<p align="center">
    <a href="https://dartpad.dev/?id=040d52ecb2bcaab193e63e6a2adc04a6">
        <img src="https://i.imgur.com/sl9DCgQ.png" height="24">
    </a>
</p>

> Observe que para retornar os valores nós utilizamos a função print. Esta e outra funções serão mencionadas posteriormente num tópico saída de dados. 

> Outro ponto importante é que utilizamos o tipo de variável **var**, este tipo é como um "coringa" dentro do dart e será documentado mais a frente.

Para verificar a quantidade de itens contidos em uma lista, que seria o seu tamanho, utilizamos o length, que retorna a quantidades de itens.


<h3 align="center">Verificando o tamanho de uma List</h3>

~~~dart

void main(){
  // Criando uma List
  var lista_de_animes = ["Yu Yu Hakusho", "Cowboy Bebop", "Trigun", "One Piece", "Dragon Ball"];

    // Verificando a quantidade de itens
    print(lista_de_animes.length);
 }
~~~

<p align="center">
    <a href="https://dartpad.dev/?id=e91073cc0a8dcc2058d8145070ce3a37">
        <img src="https://i.imgur.com/VmVWIG0.png" height="24">
    </a>
</p>


<h3 align="center">Adicionando novos valores a List</h3>

~~~dart

void main(){
  // Criando uma List
  var lista_de_animes = ["Yu Yu Hakusho", "Cowboy Bebop", "Trigun", "One Piece", "Dragon Ball"];

    lista_de_animes.add("Ranma 1/2");
    lista_de_animes.add("Urusei Yatsura");
}
~~~

<p align="center">
    <a href="https://dartpad.dev/?id=673ac183842a92161ed75a534de1c40f">
        <img src="https://i.imgur.com/GesQcXY.png" height="24">
    </a>
</p>


<h2 id="maps"> Maps</h2>

Os maps são os equivalentes aos dicionários utilizados em outras linguagens. Através dos maps é possível criar uma list com um pequeno upgrade: as Keys. As keys fazem parte de um par de chave-valor utilizados nos maps. Um bom exemplo prático disso é o próprio dicionário, onde temos uma **palavra** (key - chave) e o seu **significado** (value - valor).

Exemplo:

| Key    | Value             |
|--------|-------------------|
| Game   | Zelda: BOTW       |
| Cantor | Tatsuro Yamashita |
| Rapper | Froid             |
| Carro  | Fusca             |


<h3 align="center">Criando maps</h3>

~~~dart

void main(){
  // A estrutura de um map segue a seguinte maneira:
  // "key" : "value" => {"chave":"valor"}

  // Criando um map
  var mapa = {
      "Game"   : "Zelda: BOTW",
      "Cantor" : "Tatsuro Yamashita",
      "Rapper" : "Froid",
      "Carro"  : "Fusca",
  };

  // Imprimindo um valor especifico a partir da chave:
  print(mapa["Rapper"]);
  // O Resultado é Froid
}
~~~

<p align="center">
    <a href="https://dartpad.dev/?id=9e4de218a134f5e4278b42c27aa13141">
        <img src="https://i.imgur.com/3weq4Ee.png" height="24">
    </a>
</p>


> Os maps possuem várias outras formas de serem utilizados. Para se aprofundar, entre em algum dos links da leitura recomendada. 

<h2 id="sets"> Sets</h2>

Os sets em dart são conjuntos não ordenados de itens exclusivos, semelhantes aos conjuntos matemáticos, onde a ordem e elementos duplicados não possuem relevância. Para utilizar um conjunto, deve-se especificar o seu tipo antes das chaves, caso contrário, será reconhecido como um map comum.

<h3 align="center">Criando sets</h3>

~~~dart

void main(){
  // Declarando um conjunto Set
  Set deck_kaiba = <String>{"Dragão Branco", "Dragão Branco", "Dragão Branco", "pote da ganancia", "polimerização"};

  print(deck_kaiba);
  // Saida: Dragão Branco, pote da ganancia, polimerização;
}
~~~

<p align="center">
    <a href="https://dartpad.dev/?id=a89946ac88229ec126ab071d430b35a0">
        <img src="https://i.imgur.com/ALhNYZX.png" height="24">
    </a>
</p>

> Veja que por mais que exista **3** dragãos brancos, apenas **1** será retornado, já que elementos duplicados não são considerados.


<h2 id="var"> Var</h2>

Dentro do Dart nós temos alguns coringas como o tipo **var**. O var é uma categoria de variável capaz de inferir qual o tipo correto para a variável. Deste modo, se um número for declarado como var, automaticamente ele será um int, caso seja um número inteiro, ou um double, caso seja um número decimal. Uma vez declarado, o tipo da variável não pode ser alterado. 

<h3 align="center">Declarando variáveis do tipo var</h3>

~~~dart
void main(){
  // Declarando uma variavel var
  var numero = 1;
  
  print(numero);
  // Resultado: 1
}
~~~

<p align="center">
    <a href="https://dartpad.dev/?id=ba137f18a67ad4dfb77f240066723897">
        <img src="https://i.imgur.com/MajvzXs.png" height="24">
    </a>
</p>


> Atenção: Ao utilizar o var, o dart utiliza um pouco mais de processamento para descobrir o tipo adequado de variável. Atente-se ao uso excessivo deste método para evitar processamento desnecessário.


<h2 id="dynamic"> Dynamic</h2>

Outro grande coringa presente no Dart é o tipo dynamic. Além de assumir qualquer valor quando declarada, através da inferência como acontece com o tipo **var**, ele também pode ser alterado para qualquer outro tipo.

<h3 align="center">Declarando variáveis do tipo dynamic</h3>

~~~dart

void main(){
  // Declarando uma variavel dynamic
  dynamic numero = 1;

  // Utilizando o tipo dynamic, e possivel alterar o o tipo da variavel sem retornar nenhum erro.

  numero = "Yu-Gi-Oh";
}
~~~

<p align="center">
    <a href="https://dartpad.dev/?id=035717d766baee715cfc549f4cd1d7f1">
        <img src="https://i.imgur.com/EPnyFeP.png" height="24">
    </a>
</p>

***

<h2 id="leitura_e_link">📚 Leitura e links recomendado</h2>

* [📝 Dart - Documentação](https://dart.dev/guides)
* [🎯 Dart Iniciante: Variáveis](https://www.flutterbrasil.com/12-dart-iniciante-variaveis)
* [🎯 Dart Intermediário: Maps e List](https://www.flutterbrasil.com/23-dart-intermediario-maps-e-list)
* [🎯 Sintaxe Dart: Tipos (não tão) primitivos](https://www.devmedia.com.br/sintaxe-dart-tipos-nao-tao-primitivos/40368)
* [🎯 Introdução à programação com Dart](https://dev.to/madebyluque/introducao-a-programacao-com-dart-aji)
* [🎯 Video: Declarando e Modificando Variáveis](https://www.youtube.com/watch?v=wMS3DO0jL0I&list=PLR5GUTqrcwXhVV-jNR38vfAZabkmGGKfO&index=2)

***

<h2 id="licenca">🧾Licença</h2>

Este projeto está sob a licença [Apache 2.0](https://github.com/JosManoel/Dart-Study/blob/main/LICENSE).


