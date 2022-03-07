<img src="https://i.imgur.com/pJqSuWm.png"> 

<p>

**Autor:**
  <a href="https://github.com/JosManoel">Manoel Freitas</a>
</p>

As operações, assim como na matemática, executam ações específicas entre um ou dois operandos, conforme sua função. Alguns operadores variam em funcionalidade conforme o tipo de dado selecionado. No Dart, os operadores são semelhantes aos já bastante utilizados em outras linguagens, contanto com operadores aritméticos, operadores de incremento e operadores relacionais.

***

<h2>🧮 Sumário</h2>
   
* <a href="#operadores_aritimeticos">Operadores aritiméticos</a>
  * <a href="#soma">Soma</a>
  * <a href="#subtracao">Subtração</a>
  * <a href="#multiplicacao">Multiplicação</a>
  * <a href="#divisao">Divisão</a>
  * <a href="#modulo">Módulo</a>
  * <a href="#invertendo_sinais">Invertendo sinais</a>
* <a href="#operadores_de_atribuicao">Operadores de atribuição</a>
  * <a href="#atribuicao_null">Tratamento de valores nulos</a>
* <a href="#operadores_de_incremento">Operadores de incremento</a>
  * <a href="#prefixo">Prefixo</a>
  * <a href="#postfix">Postfix</a>
* <a href="#operadores_relacionais">Operadores relacionais</a>
* <a href="#licenca">🧾Licença</a>
* <a href="#leitura_e_link">📚 Leitura e links recomendado</a>

***

<h2 id="operadores_aritimeticos">Operadores aritiméticos</h2>

Os operadores aritméticos possuem as mesmas propriedades dos operadores utilizados comumente nas operações matemáticas do dia-a-dia, com a diferença que o operador de adição também é capaz e somar strings.

|Operador    | Descrição                                            |
|------------|------------------------------------------------------|
|+           | soma                                                 |
|-           | Subtração                                            |
|*           | Multiplicação                                        |
|/           | Divisão                                              |
|~/          | Divisão (Retorna apenas a parte inteira do resultado)|
|%           | Módulo (Retorna o resto da divisão)                  |
|-(expressão)| Inverte o sinais de uma expressão                    |


<h2 id="soma">Soma</h2>

* Você pode realizar a soma direto na atribução do valor da variável.


<h3 align="center">Operação de soma</h3>

~~~dart
void main(){ 
  var soma = 12 + 24; // = 36
  print(soma);
  // Saida: 36

  // Também é possível realizar a soma posteriormente:

  var numero1 = 3000;
  var numero2 = 2500;
  print(numero1 + numero2);
  // Saida: 5500
}
~~~

<p align="center">
    <a href="https://dartpad.dev/?id=16ce763deeda85641030d0372a1eda92">
        <img src="https://i.imgur.com/6k2HyUP.png" height="24">
    </a>
</p>

<h3 align="center">Somando strings</h3>

~~~dart
void main(){
  // Somando strings no print:

  print("Aprendendo " + "dart " + "para " + "usar " + "no " + "Flutter");
  // Saida: Aprendendo dart para usar no Flutter

  // Somando strings de variaveis:
  var titulo = "As aventuras de TIN-TIN";
  var subtitulo = "O carangueijo das Pinças de ouro";

  print(titulo + " Episodio: " + subtitulo);
  // Saida: As aventuras de TIN-TIN Episodio: O carangueijo das Pinças de ouro
}
~~~

<p align="center">
    <a href="https://dartpad.dev/?id=431ed119a4e2624fe86818fcec69a4d0">
        <img src="https://i.imgur.com/oNy4KAY.png" height="24">
    </a>
</p>


<h2 id="subtracao">Subtração</h2>

<h3 align="center">Subtraindo valores</h3>

~~~dart
void main(){
  var sub = 57 - 15; // = 42
  print(sub);
  // Saida: 42

  var numero1 = 456;
  var numero2 = 123;
  print(numero1 - numero2);
  // Saida: 333
}
~~~

<p align="center">
    <a href="https://dartpad.dev/?id=2a8ba58a4dc726f82903a00595526e7e">
        <img src="https://i.imgur.com/JD3klOy.png" height="24">
    </a>
</p>

<h2 id="multiplicacao">Multiplicação</h2>

<h3 align="center">Multiplicação de valores</h3>

~~~dart
void main(){
  var mult = 26 * 45; // = 1170
  print(mult);
  // Saida: 1170

  var numero1 = 456;
  var numero2 = 123;
  print(numero1 - numero2);
  // Saida: 333
}
~~~

<p align="center">
    <a href="https://dartpad.dev/?id=2dc1089b8ab6693d0e85129b71c81f58">
        <img src="https://i.imgur.com/2upiQRu.png" height="24">
    </a>
</p>


<h2 id="divisao">Divisão</h2>

<h3 align="center">Divisão de valores</h3>

~~~dart
void main(){
  var divi = 45 / 15; // = 3
  print(divi);
  // Saida: 3

  var numero1 = 234;
  var numero2 = 120;
  print(numero1 / numero2);
  // Saida: 1.95
}
~~~

<p align="center">
    <a href="https://dartpad.dev/?id=c131501144e17723e1d76043ec2e2bc1">
        <img src="https://i.imgur.com/XMzTKe1.png" height="24">
    </a>
</p>


<h3 align="center">Obtendo apenas a parte inteira da divisão</h3>

~~~dart
void main(){
  var numero1 = 234;
  var numero2 = 120;
  print(numero1 ~/ numero2);
  // Saida: 1
}
~~~

<p align="center">
    <a href="https://dartpad.dev/?id=9d4279013613130a4348cc7ad52a6a64">
        <img src="https://i.imgur.com/ZXaSamu.png" height="24">
    </a>
</p>


<h2 id="modulo">Módulo</h2>

<h3 align="center">Retornando apenas o resto da divisão</h3>

~~~dart
void main(){
  var numero1 = 5;
  var numero2 = 2;
  print(numero1 % numero2);
  // Saida: 1
}
~~~

<p align="center">
    <a href="https://dartpad.dev/?id=d8f1879c82184a6e60886c5765bd0d99">
        <img src="https://i.imgur.com/rvpRHl4.png" height="24">
    </a>
</p>


<h2 id="invertendo_sinais">Invertendo sinais</h2>

A inversão de sinais é semelhante ao já utilizado em cálculos, onde basta colocar o sinal de subtração a frente da operação.

<h3 align="center">Invertendo os sinais</h3>

~~~dart
void main(){
  var inver = -(-2);
  print(inver);
  // Saida: 2
}
~~~

<p align="center">
    <a href="https://dartpad.dev/?id=77236e7ce30df202f083c2a03ce33451">
        <img src="https://i.imgur.com/lXH9Iai.png" height="24">
    </a>
</p>

***

<h2 id="operadores_de_atribuicao">Operadores de atribuição</h2>

Os operadores de atribuição permitem conferir um valor a uma variável, podendo ser combinado com diversos outros operadores para a construção de instruções abreviadas. 

<h3 align="center">Operadores de atribuição</h3>

|Operador | Descrição                                                        |
|---------|------------------------------------------------------------------|
|  =      | Utilizado para atribuir um valor a uma variável.                 |
|  +=     | Soma um valor ao dado já existente na variável.                  |
|  -=     | Subtrai um valor ao dado já existente na variável.               |
|  *=     | Multiplica um valor ao dado já existente na variável.            |
|  /=     | Divide o valor já existente na variável pelo valor informado.    |
|  %=     | Atribui o resto da divisão entre o valor já existente e o valor informado. |
|  ~/=     | Atribui o resultado de uma divisão entre o valor já existente e o valor informado, porém arredondado para baixo. |
|  ??=   | Atribui um valor caso o dado existente na variável seja nulo.     | 

<h3 align="center">Utilizando os operadores de atribuição</h3>

~~~dart
void main(){
  var mortes_kuririn;
  
  print("Operador de atribuição '='");
  mortes_kuririn = 5;
  print("N° de mortes de Kuririn: ${mortes_kuririn} \n"); // 5

  print("Operador de atribuição '+='");
  mortes_kuririn += 2;
  print("N° de mortes de Kuririn: ${mortes_kuririn} \n"); // 7
  
  print("Operador de atribuição '-='");
  mortes_kuririn -= 4;
  print("N° de mortes de Kuririn: ${mortes_kuririn} \n"); // 3
  
  print("Operador de atribuição '*='");
  mortes_kuririn *= 5;
  print("N° de mortes de Kuririn: ${mortes_kuririn} \n"); // 15
  
  print("Operador de atribuição '/='");
  mortes_kuririn /= 3;
  print("N° de mortes de Kuririn: ${mortes_kuririn} \n"); // 5
  
  print("Operador de atribuição '%='");
  mortes_kuririn %= 2;
  print("N° de mortes de Kuririn: ${mortes_kuririn} \n"); // 1
  
  print("Operador de atribuição '~/='");
  mortes_kuririn ~/= 2;
  print("N° de mortes de Kuririn: ${mortes_kuririn} \n"); // 0
  
}
~~~

<p align="center">
    <a href="https://dartpad.dev/?id=14d53543686c36868560d7e0b063cc08">
        <img src="https://i.imgur.com/7IzI2Yh.png" height="24">
    </a>
</p>

<h2 id="atribuicao_null">Tratamento de valores nulos</h2>

Durante o desenvolvimento de aplicações é comum que seja necessário atribuir certos valores **_default_** para variáveis que não podem receber um **_null_** por atribuição. Para estes casos o Dart possui um operador de atribuição que simplifica o tratamento de valores nulos, denominados [operadores null-aware](https://dart.dev/codelabs/dart-cheatsheet#null-aware-operators). Os operadores **_null-aware_** são operadores de atribuição que conferem um valor a uma variável apenas se o seu valor atual for nulo. 

<h3 align="center">Utilizando o operador null-aware '??='</h3>

~~~dart
void main(){
  var yamcha_vitorias = null;
  
  print("Vitórias do Yancha: ${yamcha_vitorias}");
  yamcha_vitorias ??= 1;
  // Como inicialmente a variável possui o valor null, 
  // será atribuido o valor 1
  print("Vitórias do Yancha (contra o vento): ${yamcha_vitorias} \n");
  
  
  // Perceba que a variável não será atribuída caso
  // o valor inicial seja diferente de null
  
  var goku_power = 8001; // valor inicial diferente de null
  goku_power ??= 7999; 
  print("Poder Goku: ${goku_power}");
}
~~~

<p align="center">
    <a href="https://dartpad.dev/?id=65e5f16636c9ec52d42f51fd865faad7">
        <img src="https://i.imgur.com/0THnfFo.png" height="24">
    </a>
</p>

> Caso já tenha visto o tópico sobre operadores ternários, poderá notar alguma semelhança com o funcionamento do null-aware, pois ambos podem ser usados para o tratamento de valores nulos. Cabe ao desenvolvedor determinar qual o método mais apropriado para o seu caso.

***

<h2 id="operadores_de_incremento">Operadores de incremento</h2>

Os operadores de incremento são utilizados para diminuir ou incrementar uma variável em **1 unidade**. Normalmente são utilizados em laços como o for, que será abordado posteriormente. Os operadores de incremento são dividos em **prefixo**, que altera a variável antes de avaliar a expressão de condição, e o **postfix**, que altera a variável após avaliar a expressão de condição.


<h3 align="center">Prefixo</h3>

~~~dart
void main(){
  var variavel;
  ++variavel; // Incremento
  --variavel; // Decremento
}
~~~

<p align="center">
    <a href="https://dartpad.dev/?id=f5c1bba79853e0e5f5e4bdf350b554f4">
        <img src="https://i.imgur.com/LuFA6jB.png" height="24">
    </a>
</p>

<h3 align="center">Postfix</h3>

~~~dart
void main(){
  var variavel;
  variavel++; // Incremento
  variavel--; // Decremento
}
~~~

<p align="center">
    <a href="https://dartpad.dev/?id=a2294e0023377d3903ded95c5e7725d6">
        <img src="https://i.imgur.com/M2sg4Vs.png" height="24">
    </a>
</p>

***

<h2 id="operadores_relacionais">Operadores relacionais</h2>


Os operadores relacionais são destinados a comparações entre fatores, normalmente utilizados em condicionais, que serão abordados posteriormente. Os operadores relacionais retornam valores booleanos (**true**/**false**).


<h3 align="center">Operadores relacionais</h3>

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
|   !     | Operador lógico NOT.                                             |
|  is     | Verifica se o item é do mesmo tipo de outro.                     |
|  !is    | Verifica se o tipo do item é diferente do tipo de outra variável.|

> A utilização destes operadores será melhor abordada no tópico sobre operadores condicionais.


<h3 align="center">Utilização dos operadores relacionais</h3>

~~~dart
void main(){
  var arroz = 1;
  var feijao = 2;
  var verdadeiro = true;
  var falso = false;

  // Operador: ==
  print(arroz == feijao); 
  // Saida: false

  // Operador: !=
  print(arroz != feijao); 
  // Saida: true

  // Operador: >
  print(arroz > feijao); 
  // Saida: false

  // Operador: <
  print(arroz < feijao); 
  // Saida: true

  // Operador: <=
  print(arroz <= feijao); 
  // Saida: true

  // Operador: >=
  print(arroz >= feijao); 
  // Saida: false

  // Operador logico: &&
  print(verdadeiro && falso);
  // Saida: false

  // Operador logico: ||
  print(verdadeiro || falso);
  // Saida: true

  // Operador logico: !
  print(!verdadeiro);
  // Saida: falso

  // Operador logico: is
  print(verdadeiro is bool); 
  // Saida: true

  // Operador
  print(verdadeiro is! int);
  // Saida: true
}
~~~

<p align="center">
    <a href="https://dartpad.dev/?id=87e38dd4c9f8ca9fb532e4d929d7f8f4">
        <img src="https://i.imgur.com/IMAodDj.png" height="24">
    </a>
</p>

***

<h2 id="leitura_e_link">📚 Leitura e links recomendado</h2>

* [📝 Dart - Documentação](https://dart.dev/guides)
* [🎯 Introdução à programação com Dart](https://dev.to/madebyluque/introducao-a-programacao-com-dart-aji)
* [🎯 Linguagem Dart: operadores](https://www.devmedia.com.br/linguagem-dart-operadores/40724)
* [🎯 Video: Realizando Operações Aritméticas](https://www.youtube.com/watch?v=mp7lNJH8Ws0&list=PLR5GUTqrcwXhVV-jNR38vfAZabkmGGKfO&index=3)
* [🎯 Video: Realizando Operações Lógicas](https://www.youtube.com/watch?v=1QQhZ61dg9k&list=PLR5GUTqrcwXhVV-jNR38vfAZabkmGGKfO&index=4)

***
<h2 id="licenca">🧾Licença</h2>

Este projeto está sob a licença [Apache 2.0](https://github.com/JosManoel/Dart-Study/blob/main/LICENSE).
