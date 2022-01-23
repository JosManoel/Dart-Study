<img src="https://i.imgur.com/0jqXRoa.png"> 

<p>

**Autor:**
  <a href="https://github.com/JosManoel">Manoel Freitas</a>
</p>

As estruturas condicionais permitem executar determinados trechos do código caso alguma condição seja obedecida. Através destes operadores é possível manipular o fluxo natural de execução do código, otimizando-o e reduzindo o número de linhas necessárias para construção de uma função.

***
<h2>🧮 Sumário</h2>
 
 * <a href="#If_else">If... else</a>
 * <a href="#operador_ternario">Operador Ternário</a>
 * <a href="#switch_case">Switch/Case</a> 
 * <a href="#leitura_e_link">📚 Leitura e links recomendado</a>
 * <a href="#licenca">🧾Licença</a>

***

<h2 id="If_else">If... else</h2>

Os operadores **if/else** em dart possuem a mesma função e sintaxe como encontradas em outras linguagens. Sua função, em resumo, é executar um trecho do código caso a operação condicional retorne um valor true. O **if** pode ser utilizado sem a presença do **else**, porém o seu uso é recomendado para evitar possíveis erros de exceção.

<h3 align="center">Sintaxe do if/else</h3>

~~~dart
void main(){
  var pokebola = true; 

  if (pokebola == true){
      print("Capturar pokemon");
  } else{
      print("Não capturar pokemon");
  }
}
~~~

<p align="center">
    <a href="https://dartpad.dev/?id=cba06ee4f69bb6a5449bbe58069bc6b2">
        <img src="https://i.imgur.com/Th1bhfw.png" height="24">
    </a>
</p>

> Você também pode adicionar outras condições através do uso de operadores lógicos.


<h3 align="center">Utilização de dois fatores condicionais</h3>


~~~dart

void main(){
  var pokebola = true; 
  var pokebola_vazia = true; 

  // Caso 1: Operador logico AND (&&)

  // caso a pokebola exista E ela esteja vazia, o pokemon sera capturado.
  if (pokebola == true && pokebola_vazia == true){
      print("Capturar pokemon");
  } else{
      print("Não capturar pokemon");
  }


  // Caso 2: Operador logico OR (&&)

  // caso exista alguma pokebola, seja ela vazia OU nao, o treinar tera pokebolas.
  if(pokebola == true || pokebola_vazia == true){
      print("Tenho pokebolas");
  } else{
      print("Não tenho pokebolas");
  }
}
~~~

<p align="center">
    <a href="https://dartpad.dev/?id=1be08c78aaaf002b2517313660002907">
        <img src="https://i.imgur.com/JjPrPJY.png" height="24">
    </a>
</p>


<h3 align="center">Concatenando if/else</h3>

~~~dart

void main(){
  var estrelas = 0;
  var delito = true;

  if(delito == true){
      estrelas = 2;
  }else if(estrelas > 0){
      print("Voce e procurado, CJ");
      print("Estrelas: " + estrelas.toString());
  }else{
      print("Tudo limpo, CJ");
  }
}
~~~

<p align="center">
    <a href="https://dartpad.dev/?id=26e7730a602ba955bdd872508807bc8d">
        <img src="https://i.imgur.com/RwckPTV.png" height="24">
    </a>
</p>

> Atente-se a necessidade do seu código, se esta estrutura for necessária, talvez seja melhor utilizar um switch/case.

> O ".toString()", utilizado no código acima é uma função que converte uma variável para uma String. Esta função será abordada melhor num futuro tópico.

***

<h2 id="operador_ternario">Operador Ternário</h2>

O operador ternário é uma forma compacta de realizar o if/else, ideal para pequenas condicionais que podem ser escritas em apenas uma linha. 


<h3 align="center">Estruturua de um operador ternário</h3>

|Variavel| Condição | Operador | Retorno caso a variável seja _true_ | Operador | Retorno caso a variável seja _false_| Resultado |
|-|-|-|-|-|-|-|
|Cavaleiro =  | true |  ?  |"Espada"| : |"Cajado"| Cavaleiro = "Espada"|
|Mago = | false| ?| "Espada"| : | "Cajado"| Mago = "Cajado"|


<h3 align="center">Utilização do operador ternário</h3>


~~~dart

void main(){
  bool divida = false;
  String conta;

  conta = divida ? "saldo devedor" :"possui credito";
  print(conta);

  //Caso a divida seja true, sera retornado um saldo devedor, caso contrario, sera retornado que a conta possui credito 
}
~~~

<p align="center">
    <a href="https://dartpad.dev/?id=4463a88159e43d273134c92b78d5f81f">
        <img src="https://i.imgur.com/lYuGTWg.png" height="24">
    </a>
</p>

> Atente-se: O valor booleano da condição deve ser declarado (se é true ou false), caso contrário, será atribuído um valor null, causando um erro no código.

<h3 align="center">Outra maneira de declarar um operador ternário</h3>

O operador possui uma forma ainda mais contraída, que atribui um valor padrão caso uma valor que está sendo recebido seja nulo:

|Variável| Valor repassado | Operador | Valor caso o a variável repassada seja nula|
|-|-|-|-|
|guilda = |"Almas da Ofensa" | ?? | "Sem guilda"


<h3 align="center">Utilização da segunda forma do operador ternário</h3>

~~~dart

void main(){
  String nome = "Ataru";
  String usuario = nome ?? "Não informado";

  print(usuario);

  //Caso o nome tenha um valor diferente de null, ele sera atribuido ao usuario. Caso contrario, sera colocado como Nao informado
}
~~~

<p align="center">
    <a href="https://dartpad.dev/?id=47aef25f6e6c71ce95adf0fd622bc3cc">
        <img src="https://i.imgur.com/dfLJsKH.png" height="24">
    </a>
</p>


<h2 id="switch_case">Switch/Case</h2>


O **Switch/Case** é uma estrutura condicional de decisões limitadas, isto é, uma estrutura onde todos os possíveis resultados já foram predefinidos. O Switch/Case funciona comparando o valor de uma variável aos valores já definidos. Caso exista uma correspondência, o código dentro daquele caso será executado.


<h3 align="center">Utilização do Switch/Case</h3>


~~~dart

void main(){
  var cond = 1;

  switch (cond) {
      case 1:
          print("Caso 1");
          break;
      case 2:
          print("Caso 2");
          break;
      default:
          print("Nenhum caso");
  }
}
~~~

<p align="center">
    <a href="https://dartpad.dev/?id=0f25d0a6524159eb5e995fed7ea8518d">
        <img src="https://i.imgur.com/xC0vnp4.png" height="24">
    </a>
</p>

Repare que nós temos a presença de um caso **default**. O default contem um código que será executado caso nenhuma das opções seja atendida.

> Neste exemplo, caso a variável cond não seja igual à 1 ou 2, será exibido "Nenhum caso".

No Switch/Case também fazemos uso da palavra **break**. O break é utilizado para indicar que o código dentro da condicional foi finalizado, passando para as setenças seguintes. O uso do break é obrigatório. Caso ele não seja utilizado, ocorrerá um erro durante a execução.

> O uso excessivo dessa condicional não é recomendado por questões de performance. 

***

<h2 id="leitura_e_link">📚 Leitura e links recomendado</h2>

* [📝 Dart - Documentação](https://dart.dev/guides)
* [🎯 Introdução à programação com Dart](https://dev.to/madebyluque/introducao-a-programacao-com-dart-aji)
* [🎯 Linguagem Dart: Controle de Fluxo](https://www.devmedia.com.br/linguagem-dart-controle-de-fluxo/40758)
* [🎯 Estruturas condicionais e de repetição no Dart](https://www.treinaweb.com.br/blog/estruturas-condicionais-e-de-repeticao-no-dart)
* [🎯 toString method](https://api.flutter.dev/flutter/dart-core/num/toString.html)
* [🎯 Video: Tomando Decisões (Condicionais)](https://www.youtube.com/watch?v=_FMjnxwxGzA&list=PLR5GUTqrcwXhVV-jNR38vfAZabkmGGKfO&index=5)

***

<h2 id="licenca">🧾Licença</h2>

Este projeto está sob a licença [Apache 2.0](https://api.flutter.dev/flutter/dart-core/num/toString.html).
