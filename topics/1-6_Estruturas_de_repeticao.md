<img src="https://i.imgur.com/lkf06jo.png"> 

<p>

**Autor:**
  <a href="https://github.com/JosManoel">Manoel Freitas</a>
</p>

As estruturas de repetições são pequenos artifícios presentes na grande maioria das linguagens de programação. Elas permitem que certos trechos de código possam ser repetidos por uma quantidade de vezes predefinida ou até que uma condição seja obedecida, sem a necessidade de duplicar o código.

***
<h2 id="sumario">🧮 Sumário</h2>
 
 * <a href="#for_lacoes_de_rep">For - Laços de repetições predefinidas</a>
 * <a href="#for_in_interavel">For ..in - Laços interáveis</a>
 * <a href="#foreach">ForEach() - manipulação de listas</a>
 * <a href="#map">map() - manipulação de listas</a>
 * <a href="#while">While - Interações não predefinidas</a>
 * <a href="#do_while">Do/While - Uma segunda forma de utilizar o While</a>
 * <a href="#controle">Declarações de controle</a>
    * <a href="#break">Break</a>
    * <a href="#continue">Continue</a>
 * <a href="#leitura_e_link">📚 Leitura e links recomendado</a>
 * <a href="#licenca">🧾Licença</a>

***

<h2 id="for_lacoes_de_rep">For - Laços de repetições predefinidas</h2>

O **for** permite que um bloco de código seja executado por um número definido de vezes. Sua estrutura possui uma variável de incremento ou decremento obrigatória, que funciona como um contador para as repetições. O laço de repetição **for** é bastante útil quando já se sabe o número de vezes em que o código será executado.

> As variáveis criadas dentro de um loop for no dart não são acessíveis por outra parte do código fora do loop.

<h3 align="center">For - estrutura</h3>

| Variável de incremento|Sentença de repetição | Tipo de interação|
|-|-|-|
|Esta é a variável que vai contar as repetições | Esta sentença retorna um valor booleano que, quando verdadeiro, finaliza o laço de repetição | Indica se a interação será de incremento ou decremento|

<h3 align="center">For - sintaxe</h3>

~~~dart
void main(){
    for (int count = 1 ; count <= 4 ; count++){
        print("Goku SSJ" + count.toString());
    }
}    
~~~

<p align="center">
    <a href="https://dartpad.dev/?id=60b036305ffc1eb98804fdec315bb493">
        <img src="https://i.imgur.com/DR0yBTg.png" height="24">
    </a>
</p>
 
No exemplo acima, a variável de incremento **count** é iniciada com o valor 1 e será incrementada ( **count++** ) até que seja maior ou igual a 4 ( **count <= 4** ), quando o laço de repetição será finalizado, exibindo as transformações SSJ do Goku do 1 ao 4.

<h2 id="for_in_interavel">For ..in - Laços interáveis</h2>

O Laço **For ..in** é geralmente utilizado para criar um loop em iteráveis, como o list e o set, e possui um retorno vazio. O **for ..in** é uma forma contraída do laço for e é bastante útil em situações em que é necessário apenas percorrer alguma List. 

<h3 align="center">Exemplo de utilização do laço for ..in</h3>

~~~dart
void main(){
    var lista_de_animes = ["Yu Yu Hakusho", "Cowboy Bebop", "Trigun", "One Piece", "Dragon Ball"];

    for (String anime in lista_de_animes) {print(anime);}
}    
~~~

<p align="center">
    <a href="https://dartpad.dev/?id=ba7e1200d0f7f7611d6761b7f793ce8c">
        <img src="https://i.imgur.com/J5gcUGo.png" height="24">
    </a>
</p>
 
<h2 id="foreach">ForEach() - manipulação de listas</h2>

Assim como no **for ..in**, o **forEach()** é capaz de realizar percorrer cada elemento de uma lista e executar um determinado trecho de código, seja ele uma operação matemática ou apenas um print. No entanto, o **forEach()** não retorna nenhum elemento, da mesma forma que o for ..in. Caso esta função seja necessária, é recomendado o o uso do **map()**.

> O forEach é recomendado quando é necessário apenas a execução de um procedimento específico, sem a necessidade de retornar um conjunto de dados.

<h3 align="center">Utilização do laço forEach()</h3>

~~~dart
void main(){
    var lista_de_animes = ["Yu Yu Hakusho", "Cowboy Bebop", "Trigun", "One Piece", "Dragon Ball"];

    lista_de_animes.forEach((anime) => print(anime));
}    
~~~

<p align="center">
    <a href="https://dartpad.dev/?id=9acb6ec5c4b717d2a64267552738d85c">
        <img src="https://i.imgur.com/vilTqY6.png" height="24">
    </a>
</p>
 
<p align="right">
    <a href="#sumario" style="font-size:1rem;font-weight: bold;">
        <img src="https://raw.githubusercontent.com/JosManoel/Dart-Study/main/images/icons/voltar_ao_topo.png" height="32">
    </a>
</p>

***

<h2 id="map">map() - manipulação de listas</h2>

O **map()** funciona de uma maneira semelhante ao **forEach()**, realizando interações em listas. No entando este método é capaz de retornar um grupo de elementos criados a partir de funções definidas no map.

> CUIDADO: O método mensionado é o **map()**, que é diferente do **Map()** ( Com o 'M' maiúsculo ). O **map()** é um método que realiza interações. Já o **Map()** é um construtor, sendo uma das formas de se declarar uma variável do tipo Map.

O **map()** pode ser utilizado em situações que é necessário armazenar o retorno do método, para que seja acessado e utilizado posteriormente.

<h3 align="center">Utilização do map()</h3>


~~~dart
void main(){
    var lista_de_animes = ["Yu Yu Hakusho", "Cowboy Bebop", "Trigun", "One Piece", "Dragon Ball"];

    lista_de_animes.map((anime) => print(anime)).toList();
}    
~~~

<p align="center">
    <a href="https://dartpad.dev/?id=63a9f1b35697cd2eb892da1c95ad6e3d">
        <img src="https://i.imgur.com/vilTqY6.png" height="24">
    </a>
</p>
 

<h3 align="center">map() - Criando uma lista a partir de outra</h3>

~~~dart
void main(){
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
}
~~~

<p align="center">
    <a href="https://dartpad.dev/?id=a395bca09a10d2a535bd3d805e1fe86d">
        <img src="https://i.imgur.com/Nee2NfQ.png" height="24">
    </a>
</p>
 
<p align="right">
    <a href="#sumario" style="font-size:1rem;font-weight: bold;">
        <img src="https://raw.githubusercontent.com/JosManoel/Dart-Study/main/images/icons/voltar_ao_topo.png" height="32">
    </a>
</p>

***

<h2 id="while">While - Interações não predefinidas</h2>

O **While** é uma estrutura de repetição que permite que o código seja executado até uma condição se torne **false**, semelhante ao operador **if**, com a diferença que o bloco será executado **enquanto** a condição for verdadeira. 

Deste modo, é comum encontrar na estrutura do while uma variável que é incrementada ao final de um ciclo.

<h3 align="center">Utilização do while</h3>


~~~dart
void main(){
    var count = 1;

    while (count <= 4){
        print("Goku SSJ" + count.toString());

        count++;
    }
}
~~~


<p align="center">
    <a href="https://dartpad.dev/?id=ee9f53861156a2838a0e4f12ae4297f6">
        <img src="https://i.imgur.com/N2nwlmk.png" height="24">
    </a>
</p>
 
> O while é indicado para situações onde não existe um número exato de interações predefinidas, porém, já se possui uma ideia de qual seria a gama de casos atendidos.

<h2 id="do_while">Do/While - Uma segunda forma de utilizar o While</h2>

O **Do/While** funciona exatamente da mesma forma que o **While** comum, porém possui uma pequena mudança em sua estrutura, apresentando o operador de verificação no final. Essa configuração permite que o laço sempre seja executado pelo menos uma vez no código, mesmo que a condição de retorno não seja atendida.

<h3 align="center">Utilização do Do/While</h3>

Utilização do Do/While

~~~dart
void main() {
  var ki = 1;

  print("Golpe especial");
  print("Ki disponível: " + ki.toString());
  
  do {
      print("Carregando Ki: " + ki.toString());
      ki++;
  } while (ki <= 10);
  
  print("Golpe especial!");
}


/*
Saída:

Golpe especial
Ki disponível: 1
Carregando Ki: 1
Carregando Ki: 2
Carregando Ki: 3
Carregando Ki: 4
Carregando Ki: 5
Carregando Ki: 6
Carregando Ki: 7
Carregando Ki: 8
Carregando Ki: 9
Carregando Ki: 10
Golpe especial!
*/
~~~

<p align="center">
    <a href="https://dartpad.dev/?id=ee7abad7fe81ad5b297c4daeeff72776">
        <img src="https://i.imgur.com/7bTsRSk.png" height="24">
    </a>
</p>
 
> No exemplo anterior o Ki será carregado apenas se o valor inicial for menor que 10. Caso a variável seja iniciada com o valor 10, não será necessário carregar o Ki.

<p align="right">
    <a href="#sumario" style="font-size:1rem;font-weight: bold;">
        <img src="https://raw.githubusercontent.com/JosManoel/Dart-Study/main/images/icons/voltar_ao_topo.png" height="32">
    </a>
</p>

***

<h2 id="controle">Declarações de controle</h2>

Durante a utilização dos laços mencionados acima é comum que seja necessário implementar outras formas de controle do fluxo, além das que já estão implantadas na estrutura do loop. Para sanar esta necessidade, o dart possui compatibilidade com duas categorias de instruções de controle de fluxo, sendo elas o **break** e o **continue**.

<h2 id="break">Break</h2>

O comando **break** possui a função de interromper o fluxo do loop de maneira imediata, retornando o fluxo de controle para fora do laço mesmo que a condição de parada ainda não tenha sido atingida. Através dele é possível encerrar a execução do loop sempre que necessário.

<h3 align="center">Utilização do break </h3>


~~~dart
void main(){
    var count = 1;

    while (count <= 4){
        print("Canon: Goku SSJ" + count.toString());

        if( count == 3){
            break; 
        }

        count++;
    }
}
~~~

<p align="center">
    <a href="https://dartpad.dev/?id=5eb89916bb9d17ff3b80996099e4d7b8">
        <img src="https://i.imgur.com/5DhwIT0.png" height="24">
    </a>
</p>

> Perceba que o loop é encerrado antes da sua condição de parada original, que seria quando a variável "count" atingisse o valor 4.


<h2 id="continue">Continue</h2>

O continue possui uma função semelhante ao **break**, porém ao invés de interromper o laço inteiro ela interrompe apenas uma execução, pulando para a próxima iteração.

<h3 align="center">Utilização do continue</h3>


~~~dart
void main(){
    var count = 0;

    while (count < 4){
      count++;

      if(count == 2){
        print("pulou");
        continue;
      }

      print("Goku SSJ" + count.toString());
    }
}
~~~

<p align="center">
    <a href="https://dartpad.dev/?id=e11ff244a38ed322906ab2d30d0f3e91">
        <img src="https://i.imgur.com/fUEltlF.png" height="24">
    </a>
</p>

> Observe que o texto "Goku SSJ2" não é mostrado, já que seu ciclo é encerrado antes desta ação ocorrer.

<p align="right">
    <a href="#sumario" style="font-size:1rem;font-weight: bold;">
        <img src="https://raw.githubusercontent.com/JosManoel/Dart-Study/main/images/icons/voltar_ao_topo.png" height="32">
    </a>
</p>

***

<h2 id="leitura_e_link">📚 Leitura e links recomendado</h2>

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
* [🎯 DART - DECLARAÇÕES DE CONTROLE DE LOOP (INTERROMPER E CONTINUAR)](https://acervolima.com/dart-declaracoes-de-controle-de-loop-interromper-e-continuar/)
* [🎯 Video: Realizando Repetições (Loops)](https://www.youtube.com/watch?v=PAv1k0z4wrI&list=PLR5GUTqrcwXhVV-jNR38vfAZabkmGGKfO&index=8)

<p align="right">
    <a href="#sumario" style="font-size:1rem;font-weight: bold;">
        <img src="https://raw.githubusercontent.com/JosManoel/Dart-Study/main/images/icons/voltar_ao_topo.png" height="32">
    </a>
</p>

***

<h2 id="licenca">🧾Licença</h2>

Este projeto está sob a licença [Apache 2.0](https://github.com/JosManoel/Dart-Study/blob/main/LICENSE).

<p align="right">
    <a href="#sumario" style="font-size:1rem;font-weight: bold;">
        <img src="https://raw.githubusercontent.com/JosManoel/Dart-Study/main/images/icons/voltar_ao_topo.png" height="32">
    </a>
</p>
