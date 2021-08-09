# Dart: Estruturas de repetições <a href = "https://dart.dev/"><img src="https://raw.githubusercontent.com/JosManoel/Dart-Study/main/images/icons/dart.png" width = "24"></img></a>

As estruturas de repetições são pequenos artifícios presentes na grande maioria das linguagens de programação. Elas permitem que certos trechos de código possam ser repetidos por uma quantidade de vezes predefinida ou até que uma condição seja obedecida, sem a necessidade de duplicar o código.

# For - Laços de repetições predefinidas
O **for** permite que um bloco de código seja executado por um número definido de vezes. Sua estrutura possui uma variável de incremento ou decremento obrigatória, que funciona como um contador para as repetições. O laço de repetição **for** é bastante útil quando já se sabe o número de vezes em que o código será executado.

> As variáveis criadas dentro de um loop for no dart não são acessíveis por outra parte do código fora do loop.

### For - estrutura

| Variável de incremento|Sentença de repetição | Tipo de interação|
|-|-|-|
|Esta é a variável que vai contar as repetições | Esta sentença retorna um valor booleano que, quando verdadeiro, finaliza o laço de repetição | Indica se a interação será de incremento ou decremento|

```
for (int count = 1 ; count <= 4 ; count++){
    print("Goku SSJ" + count.toString());
}
```
No exemplo acima, a variável de incremento **count** é iniciada com o valor 1 e será incrementada ( **count++** ) até que seja maior ou igual a 4 ( **count <= 4** ), quando o laço de repetição será finalizado, exibindo as transformações SSJ do Goku do 1 ao 4.

## For ..in - Laços interáveis

O Laço **For ..in** é geralmente utilizado para criar um loop em iteráveis, como o list e o set, e possui um retorno vazio. O **for ..in** é uma forma contraída do laço for e é bastante útil em situações em que é necessário apenas percorrer alguma List. 

### Exemplo de utilização do laço for ..in
```
var lista_de_animes = ["Yu Yu Hakusho", "Cowboy Bebop", "Trigun", "One Piece", "Dragon Ball"];

for (String anime in lista_de_animes) {print(anime);}

```

## ForEach() -  manipulação de listas

Assim como no **for ..in**, o **forEach()** é capaz de realizar percorrer cada elemento de uma lista e executar um determinado trecho de código, seja ele uma operação matemática ou apenas um print. No entanto, o **forEach()** não retorna nenhum elemento, da mesma forma que o for ..in. Caso esta função seja necessária, é recomendado o o uso do **map()**.

> O forEach é recomendado quando é necessário apenas a execução de um procedimento específico, sem a necessidade de retornar um conjunto de dados.

### Exemplo de utilização do laço forEach()

```
var lista_de_animes = ["Yu Yu Hakusho", "Cowboy Bebop", "Trigun", "One Piece", "Dragon Ball"];

lista_de_animes.forEach((anime) => print(anime));

```
***

# map() - manipulação de listas

O **map()** funciona de uma maneira semelhante ao **forEach()**, realizando interações em listas. No entando este método é capaz de retornar um grupo de elementos criados a partir de funções definidas no map.

> CUIDADO: O método mensionado é o **map()**, que é diferente do **Map()** ( Com o 'M' maiúsculo ). O **map()** é um método que realiza interações. Já o **Map()** é um construtor, sendo uma das formas de se declarar uma variável do tipo Map.

O **map()** pode ser utilizado em situações que é necessário armazenar o retorno do método, para que seja acessado e utilizado posteriormente.

### Exemplo de utilização do map()

* Utilizando o map() apenas para percorrer e imprimir valores:

```
var lista_de_animes = ["Yu Yu Hakusho", "Cowboy Bebop", "Trigun", "One Piece", "Dragon Ball"];

lista_de_animes.map((anime) => print(anime)).toList();

```

* Utilizando o map() para criar uma nova lista a partir de uma já existente:

```
var lista_1 = [2,4,6,8];
print("Lista 1");
lista_1.forEach((num_1) => print(num_1));

// Criando nova lista a partir da lista 1
var lista_2 = lista_1.map((num) => num*2).toList();
print("Lista 2");
lista_2.forEach((num_2) => print (num_2));


/*

Saída:

Lista 1
2
4
6
8
Lista 2
4
8
12
16

*/
```
***
# While - Interações não predefinidas

O **While** é uma estrutura de repetição que permite que o código seja executado até uma condição se torne **false**, semelhante ao operador **if**, com a diferença que o bloco será executado **enquanto** a condição for verdadeira. 

Deste modo, é comum encontrar na estrutura do while uma variável que é incrementada ao final de um ciclo.

### Exemplo de utilização do while

```
var count = 1;

while (count <= 4){
    print("Goku SSJ" + count.toString());

    count++;
}
```

> O while é indicado para situações onde não existe um número exato de interações predefinidas, porém, já se possui uma ideia de qual seria a gama de casos atendidos.
***
## 📚 Leitura e links recomendado:
* [📝 Dart - Documentação](https://dart.dev/guides)
* [🎯 Introdução à programação com Dart](https://dev.to/madebyluque/introducao-a-programacao-com-dart-aji)
* [🎯 Introdução ao Dart](https://www.paulocagol.dev.br/2021/04/00004-introducao-linguagem-dart/#8-estrutura-de-repeti%C3%A7%C3%A3o-)
* [🎯 Estruturas condicionais e de repetição no Dart](https://www.treinaweb.com.br/blog/estruturas-condicionais-e-de-repeticao-no-dart)
* [🎯 toString method](https://api.flutter.dev/flutter/dart-core/num/toString.html)
* [🎯 Dart (DartLang) Introduction: for and for-in loops](https://medium.com/run-dart/dart-dartlang-introduction-for-and-for-in-loops-ff2bf5aeab5d)
* [🎯 Estruturas condicionais e de repetição no Dart](https://www.treinaweb.com.br/blog/estruturas-condicionais-e-de-repeticao-no-dart)
* [🎯 Iterating asynchronous operations in dart(using forEach and for..in loop)](https://dev.to/uchennaemeruche/iterating-asynchronous-operations-in-dart-using-foreach-and-for-in-loop-1n4f)
* [🎯 Aprendendo a utilizar forEach( ) ou map( ) para a manipulação de listas no Dart.](https://medium.com/@arthurgiani/aprendendo-a-utilizar-foreach-ou-map-para-a-manipula%C3%A7%C3%A3o-de-listas-no-dart-230e0dc1a53d)
* [🎯 Diferença entre while e for](https://pt.stackoverflow.com/questions/61491/diferen%C3%A7a-entre-while-e-for)
* [🎯 Quando utilizar os métodos “map()” ou “toList()”?](https://pt.stackoverflow.com/questions/403324/quando-utilizar-os-m%c3%a9todos-map-ou-tolist)
* [🎯 Você sabe utilizar um mapa? {Dart}](https://www.linkedin.com/pulse/voc%C3%AA-sabe-utilizar-um-mapa-dart-fellipe-malta/?originalSubdomain=pt)
* [🎯 Video: Realizando Repetições (Loops)](https://www.youtube.com/watch?v=PAv1k0z4wrI&list=PLR5GUTqrcwXhVV-jNR38vfAZabkmGGKfO&index=8)
***
## 🧾Licença:
Este projeto está sob a licença [Apache 2.0](https://api.flutter.dev/flutter/dart-core/num/toString.html).
