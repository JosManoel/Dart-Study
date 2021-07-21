# Dart: Declarando variáveis <a href = "https://dart.dev/"><img src="https://raw.githubusercontent.com/JosManoel/Dart-Study/main/images/icons/dart.png" width = "24"></img></a>


Uma variável é, basicamente, um espaço alocado na memória do computador para armazenar um determinado dado. De certo modo, as variáveis possuem um ciclo de vida dentro do programa, por isso, deve-se tomar cuidado ao utiliza-las, de modo a evitar problemas de declaração ou de overflow. Por ser uma linguagem tipada, as variáveis declaradas em Dart precisam ter o seu tipo informado. No entanto, não é necessário definir o valor da variável quando ela é declarada.

```
// Declarando uma variavel
int numero;

numero = 1;
```


No Dart, temos os seguintes tipos de variáveis suportados:

* <a href="#numbers">numbers</a>
* <a href="#strings">strings</a>
* <a href="#runes">runes</a>
* <a href="#boolean">boolean</a>
* <a href="#list">list</a>
* <a href="#maps">maps</a>
* <a href="#sets">sets</a>
* <a href="#var">var</a>
* <a href="#dynamic">dynamic</a>


<h1 id="numbers"> Numbers</h1>

No Dart temos 3 tipos de variáveis para armazenar valores numéricos, sendo elas int, double e num. O **int**, assim como em outras linguagens, é utilizado para armazenar apenas valores inteiros, tanto os números negativos quanto os positivos. No **double** temos uma pequena semelhança com o tipo **float**, utilizado em outras linguagens. Com o double é possível armazenar números fracionários, comumente chamados de números de ponto flutuante. Já o **num** é um tipo que engloba tanto o int como o double. Deste modo, **uma variável num pode ser tanto int como double**.

```
// Numeros inteiros
int result = 42;

// Numeros decimais
double radio = 98.9;

// Numeros inteiros OU decimais
num numero = 1.23;
num codigo = 123; 
```


<h1 id="strings"> Strings</h1>

As strings, assim como na maioria das linguagens de programação atuais, são responsáveis por armazenar um ou mais caracteres, sendo representada com aspas duplas ou simples. Existem várias maneiras de se trabalhar com strings, seja concatenando ou alterando o valor inicial. Estas e outras funcionalidades serão abordadas posteriormente em ou tópico específico.

```
// Declarando strings com aspas duplas
String anime1 = " Yu Yu Hakusho";

//Declarando strings com aspas simples
String anime2 = 'Ranma 1/2';

```

> Perceba que na variável anime2, apesar de conter números, eles são tratados com uma string e não como um int. Isso acontece porque estão dentro das aspas.


<h1 id="runes"> Runes</h1>

As runas são uma categoria de string com uma importante funcionalidade acrescentada: **Emojis**. Assim como as strings comuns, as runas são uma sequência de caracteres  Unicode, no entanto, diferentemente da string, as runas permitem exibir o código, formando caracteres especiais como símbolos e emojis.

### Criando runas:

```
Runes computador = Runes("\u1F4BB");

// para imprimir uma rune é necessário utilizar o "fromCharCodes"
print(String.fromCharCodes(computador));
//Resultado: 💻
```


<h1 id="boolean"> Boolean</h1>

Os valores booleanos são declarados utilizando o tipo bool, tendo dois valores possíveis:

* **true** (verdadeiro)
* **false** (falso)

```
// Declarando variaveis booleanas
bool sol = true;
bool chuva  = false;
```

O Dart dispõe de uma serie de operadores para serem utilizados para comparar valores booleanos.

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

<h1 id="list"> List</h1>

A list, que recebe o nome de **array** em outras linguagens, é um conjunto de valores ordenados e que possuem um índice. O índice corresponde a uma posição na fila de itens, começando do item 0.

### Exemplo de como funciona o índice:

|Item  |Yu Yu Hakusho|Cowboy Bebop|Trigun|One Piece|Dragon Ball|
|------|-------------|------------|------|---------|-----------|
|Índice|     0       |     1      |  2   |    3    |     4     |

### Declarando uma list em Dart:

```
// Criando uma List
var lista_de_animes = ["Yu Yu Hakusho", "Cowboy Bebop", "Trigun", "One Piece", "Dragon Ball"];

// Imprimindo uma list
print(lista_de_animes);
// Saída: Yu Yu Hakusho, Cowboy Bebop, Trigun, One Piece, Dragon Ball.

// Acessando um item especcifico da list
// print(list[index]);
print(lista_de_animes[3]);
// O resultado é: One Piece.
```
> Observe que para retorna os valores nós utilizamos a função print. Esta e outra funções serão mencionadas posteriormente num tópico saída de dados. 

> Outro ponto importante é que utilizamos o tipo de variável **var**, este tipo é como um "coringa" dentro do dart e será documentado mais a frente.

Para verificar a quantidade de itens contidos em uma lista, que seria o seu tamanho, utilizamos o length, que retorna a quantidades de itens.

```
// Verificando a quantidade de itens
print(lista_de_animes.length);
```
### Adicionando valores na lista:

```
lista_de_animes.add("Ranma 1/2");
lista_de_animes.add("Urusei Yatsura");

```

<h1 id="maps"> Maps</h1>

Os maps são os equivalentes aos dicionários utilizados em outras linguagens. Através dos maps é possível criar uma list com um pequeno upgrade: as Keys. As keys fazem parte de um par de chave-valor utilizados nos maps. Um bom exemplo prático disso é o próprio dicionário, onde temos uma **palavra** (key - chave) e o seu **significado** (value - valor).

Exemplo:

| Key    | Value             |
|--------|-------------------|
| Game   | Zelda: BOTW       |
| Cantor | Tatsuro Yamashita |
| Rapper | Froid             |
| Carro  | Fusca             |

### Criando maps:

```
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

```

> Os maps possuem várias outras formas de serem utilizados. Para se aprofundar, entre em algum dos links da leitura recomendada. 

<h1 id="sets"> Sets</h1>

Os sets em dart são conjuntos não ordenados de itens exclusivos, semelhantes aos conjuntos matemáticos, onde a ordem e elementos duplicados não possuem relevância. Para utilizar um conjunto, deve-se especificar o seu tipo antes das chaves, caso contrário, será reconhecido como um map comum.

### Criando sets:

```
// Declarando um conjunto Set
Set deck_kaiba = <String>{"Dragão Branco", "Dragão Branco", "Dragão Branco", "pote da ganancia", "polimerização"};
```

> Veja que por mais que exista **3** dragãos brancos, apenas **1** será retornado, já que elementos duplicados não são considerados.


```
Set deck_kaiba = <String>{"Dragão Branco", "Dragão Branco", "Dragão Branco", "pote da ganancia", "polimerização"};

print(deck_kaiba);
// Saida: Dragão Branco, pote da ganancia, polimerização;
```


<h1 id="var"> Var</h1>

Dentro do Dart nós temos alguns coringas como o tipo **var**. O var é uma categoria de variável capaz de inferir qual o tipo correto para a variável. Deste modo, se um número for declarado como var, automaticamente ele será um int, caso seja um número inteiro, ou um double, caso seja um número decimal. Uma vez declarado, o tipo da variável não pode ser alterado. 

```
// Declarando uma variavel var
var numero = 1;
print(numero);
// Resultado: 1

/*
A seguinte expressao nao e valida, ja que uma vez atribuida como numerica nao e possivel alterar o valor para uma string
*/

numero = "Yu-Gi-Oh"
```

> Atenção, ao utilizar o var, o dart utiliza um pouco mais de processamento para descobrir o tipo adequado de variável. Atente-se ao uso excessivo ou desnecessário deste método para evitar processamento desnecessário.


<h1 id="dynamic"> Dynamic</h1>

Outro grande coringa presente no Dart é o tipo dynamic. Além de assumir qualquer valor quando declarada, atraves da inferencia como acontece com o tipo **var**, ele tambem pode ser alterado para qualquer outro tipo.

```
// Declarando uma variavel dynamic
dynamic numero = 1;

/*
Utilizando o tipo dynamic, e possivel alterar o o tipo da variavel sem retornar nenhum erro.
*/

numero = "Yu-Gi-Oh"
```

***
## 📚 Leitura e links recomendado:
* [📝 Dart - Documentação](https://dart.dev/guides)
* [🎯 Dart Iniciante: Variáveis](https://www.flutterbrasil.com/12-dart-iniciante-variaveis)
* [🎯 Dart Intermediário: Maps e List](https://www.flutterbrasil.com/23-dart-intermediario-maps-e-list)
* [🎯 Sintaxe Dart: Tipos (não tão) primitivos](https://www.devmedia.com.br/sintaxe-dart-tipos-nao-tao-primitivos/40368)
* [🎯 Introdução à programação com Dart](https://dev.to/madebyluque/introducao-a-programacao-com-dart-aji)
* [🎯 Video: Declarando e Modificando Variáveis](https://www.youtube.com/watch?v=wMS3DO0jL0I&list=PLR5GUTqrcwXhVV-jNR38vfAZabkmGGKfO&index=2)

***
## 🧾Licença:
Este projeto está sob a licença [Apache 2.0](https://github.com/JosManoel/Dart-Study/blob/main/LICENSE).


