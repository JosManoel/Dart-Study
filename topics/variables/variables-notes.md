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
* <a href="#boolean">boolean</a>
* <a href="#">list</a>
* <a href="#">sets</a>
* <a href="#">maps</a>
* <a href="#">rune</a>
* <a href="#">symbols</a>


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
***
## 📚 Leitura e links recomendado:
* [📝 Dart - Documentação](https://dart.dev/guides)
* [🎯 Dart Iniciante: Variáveis](https://www.flutterbrasil.com/12-dart-iniciante-variaveis)
* [🎯 Sintaxe Dart: Tipos (não tão) primitivos](https://www.devmedia.com.br/sintaxe-dart-tipos-nao-tao-primitivos/40368)

***
## 🧾Licença:
Este projeto está sob a licença [Apache 2.0](https://github.com/JosManoel/Dart-Study/blob/main/LICENSE).


