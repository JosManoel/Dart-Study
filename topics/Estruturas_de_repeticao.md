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

O Laço **For ..in** geralmente é utilizado para criar um loop em interáveis, como o list e o set, e possui um retorno vazio. O **for ..in** é uma forma contraída do laço for e é bastante útil em situações em que é necessário apenas percorrer alguma List. 


### Exemplo de utilização do laço for ..in
```
var lista_de_animes = ["Yu Yu Hakusho", "Cowboy Bebop", "Trigun", "One Piece", "Dragon Ball"];

for (String anime in lista_de_animes) {print(anime);}

```
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
* [🎯 Video: Realizando Repetições (Loops)](https://www.youtube.com/watch?v=PAv1k0z4wrI&list=PLR5GUTqrcwXhVV-jNR38vfAZabkmGGKfO&index=8)
***
## 🧾Licença:
Este projeto está sob a licença [Apache 2.0](https://api.flutter.dev/flutter/dart-core/num/toString.html).
