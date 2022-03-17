<img src="https://i.imgur.com/3xkglsn.png"> 

<p>

**Autor:**
  <a href="https://github.com/JosManoel">Manoel Freitas</a>
</p>

Agora que você já passou pelo módulo básico, deve ter sentido a necessidade de exportar partes do código, para serem utilizadas quando necessário, ao invés de reescrever tudo novamente. No Dart e em outras linguagens de programação essa tarefa é executada pelas funções, pequenas estruturas de código independentes. 
***
<h2 id="sumario">🧮 Sumário</h2>
  
  * <a href="#o_que_e_funcao">O que é uma função ?</a>
  * <a href="#sintaxe_da_funcao">A sintaxe de uma função</a>
  * <a href="#parametros">Parâmetros de uma função</a>
  * <a href="#parametros_opcionais">Parâmetros opcionais</a>
    * <a href="#nomeados_opcionais">Parâmetros nomeados opcionais</a>
    * <a href="#posicionais_opcionais">Parâmetros posicionais opcionais</h2>
  * <a href="#retorno">Valores de retorno</a>
    * <a href="#void">Funções sem retorno</a>
  * <a href="#recursiva">Funções recursivas</a>
    * <a href="#declarando_recursiva">Declarando funções recursivas</a>
  * <a href="#anonima">Funções anonimas</a>
    * <a href="#anonima">Big Arrow Function</a>
  * <a href="#main">Função principal</a>
  * <a href="#leitura_e_link">📚 Leitura e links recomendado</a>
  * <a href="#licenca">🧾Licença</a>

***

<h2 id="o_que_e_funcao">O que é uma função ?</h2>

Uma função, de maneira direta, é uma pequena estrutura de código encapsulada de modo a tornar possível sua reutilização durante todo o código sem a necessidade de reescrever as instruções quando for necessário utiliza-las, bastando apenas "chamar" a função construída. 

Sua principal vantagem está na capacidade de reutilização, que garante um script "enxuto" e sem repetição de código, facilitando o seu desenvolvimento. Além disso, a utilização das funções garante uma maior independência do programa, já que ela não depende de quem a chamou e sim dos valores passados em seus parâmetros. 

<p align="right">
    <a href="#sumario" style="font-size:1rem;font-weight: bold;">
        <img src="https://raw.githubusercontent.com/JosManoel/Dart-Study/main/images/icons/voltar_ao_topo.png" height="32">
    </a>
</p>

***

<h2 id="sintaxe_da_funcao">A sintaxe de uma função</h2>

As funções em Dart possuem uma sintaxe simples, semelhante à sintaxe utilizada em linguagens como o C e Javascript. Sua estrutura pode ser dividida em **_Function Name_**, onde é determinado o nome e os parâmetros da função, e **_Function Body_**, responsável por conter as instruções da função. 

<h3 align="center">Estrutura de uma Função</h3>


~~~dart
tipo_de_retorno nome_da_funcao (parametro1, parametro2){

    // instruções

    return valor;
}
~~~

Observe que uma função pode ter nenhum ou vários **parâmetros**, da mesma forma que pode ou não **retornar** algum valor, que está atrelado a necessidade de identificar um **tipo de retorno** para a função. 

O processo para invocar uma função é bem simples e ocorre de maneira semelhante aos métodos utilizados em outras funções, onde basta chamar a função pelo seu nome e atribuir os parâmetros necessários dentro dos parênteses.

<h3 align="center">Realizando o chamado de função</h3>


~~~dart
tipo_de_retorno nome_da_funcao (parametro1, parametro2){

    // instruções

    return valor;
}

// chamando a função
nome_da_funcao(parametro1, parametro2);
~~~
<h3 align="center">Exemplo de aplicação</h3>


~~~dart
void main() {
  retornarPowerRanger();
}

// Nova funcao
retornarPowerRanger(){
  print("Ranger vermelho");
}
~~~

<p align="center">
    <a href="https://dartpad.dev/?id=65fefe04704c61e95f6c47fc2af49d77">
        <img src="https://i.imgur.com/jIuDwcm.png" height="24">
    </a>
</p>

A função ainda pode receber uma sintaxe contraída, semelhante ao que acontece com o operador ternário, onde toda a função é declarada em apenas uma linha. Essa forma de construção é indicada para funções simples, como meio de reduzir o código.

<h3 align="center" id="sintaxe_constraida">Exemplo de aplicação: Sintaxe contraída</h3>


~~~dart
void main() {
  retornarPowerRanger();
}

// Nova funcao em apenas uma linha
retornarPowerRanger() => print("Ranger vermelho");
~~~

<p align="center">
    <a href="https://dartpad.dev/?id=68f23c85397960f7dbb67d3fcbe77f2c">
        <img src="https://i.imgur.com/9vU9E7y.png" height="24">
    </a>
</p>


<p align="right">
    <a href="#sumario" style="font-size:1rem;font-weight: bold;">
        <img src="https://raw.githubusercontent.com/JosManoel/Dart-Study/main/images/icons/voltar_ao_topo.png" height="32">
    </a>
</p>

***

<h2 id="parametros">Parâmetros de uma função</h2>

Os parâmetros em uma função possuem a responsabilidade de receber os dados a serem trabalhados. Através deles é possível passar diversos valores e até mesmo outras funções que sejam necessárias para a execução do código. 


<h3 align="center">Utilizando parâmetros</h3>


~~~dart
void main() {
  retornarPowerRanger("Vermelho");
}

retornarPowerRanger(String cor){
  print("Ranger " + cor);
}
~~~

<p align="center">
    <a href="https://dartpad.dev/?id=5725ed68da63db87424e087cc1485399">
        <img src="https://i.imgur.com/hwd1Cn9.png" height="24">
    </a>
</p>

> Note que o tipo de parâmetro que será recebido foi especificado pela função. Apesar desta propriedade pôde ser omitida, a prática de utilizá-la em suas aplicações pode tornar o código mais legível, além de evitar possíveis erros de implementação.

Além das [variáveis](https://github.com/JosManoel/Dart-Study/blob/main/topics/Declarando_variaveis.md) já estudadas, o dart também possui suporte a utilização de outras funções como parâmetros, visto que as funções também são objetos, podendo ou não ter seu tipo especificado pela função. A sua utilização é ocorre de maneira semelhante as variáveis comuns, onde basta passar o nome da função que será utilizada como parâmetro em sua declaração.

<h3 align="center">Passando outra função como parâmetro</h3>


~~~dart
void main() {
  retornarPowerRanger("Vermelho", retornarEquipe);
}

retornarEquipe(){
  print("Equipe: Dino Trovão");
}

retornarPowerRanger(String cor, Function equipe){
  print("Ranger " + cor);
  equipe();
}
~~~

<p align="center">
    <a href="https://dartpad.dev/?id=a98f4f4644520f56146a5da65dd6e6ff">
        <img src="https://i.imgur.com/AFnKyb4.png" height="24">
    </a>
</p>

<p align="right">
    <a href="#sumario" style="font-size:1rem;font-weight: bold;">
        <img src="https://raw.githubusercontent.com/JosManoel/Dart-Study/main/images/icons/voltar_ao_topo.png" height="32">
    </a>
</p>

***

<h2 id="parametros_opcionais">Parâmetros opcionais</h2>

Em alguns casos será necessário definir parâmetros que possuem valores padrão, que permaneceram inalterados caso nenhum valor seja passado durante o chamado da função. Esses parâmetros recebem o nome **_Argumentos Opcionais_**, que podem possuir valores predefinidos e não necessitam de definição quando a função é invocada. Os parâmetros opcionais podem ser definidos de duas maneiras, seja como um **_parâmetro nomeado opcional_** ou como um **_parâmetro posicionado opcional_**.


<h2 id="nomeados_opcionais">Parâmetros nomeados opcionais</h2>

Os parâmetros nomeados opcionais são argumentos opcionais que possuem nomes que funcionam como "keys", sendo obrigatório a sua especificação no momento da chamada. A sua sintaxe é bem simples, bastando incluir as variáveis opcionais dentro chaves **(** _{ }_ **)**. A atribuição de valores padrão acontece da mesma forma como é observado em outras linguagens, como o Javascript, através do operado de atribuição no momento da definição do parâmetro na função.


<h3 align="center">Utilizando parâmetros nomeados opcionais</h3>

~~~dart
// Experimente apagar o trecho [cor:"Azul"] do chamado da 
// função para observar o resultado.

void main() {
  // Chamado de uma função atribuindo valor a variável opcional
  retornarPowerRanger(retornarEquipe, cor:"Azul");
  
  // Chamado de uma função sem a atribução da variável opcional
  retornarPowerRanger(retornarEquipe);
}

retornarEquipe(){
  print("Equipe: Dino Trovão \n");
}

retornarPowerRanger(Function equipe, {String cor = "Vermelho"}){
  // Note que, caso a variavel cor não fosse informada na chamada,
  // o valor seria "Vermelho".
  
  print("Ranger " + cor);
  equipe();
}
~~~

<p align="center">
    <a href="https://dartpad.dev/?id=272a3f7c6d9eff46e2a9b40890b01739">
        <img src="https://i.imgur.com/MfWUbpo.png" height="24">
    </a>
</p>

> Perceba que por ser um argumento opcional, o valor do parâmetro cor não precisa ser necessariamente definido quando a função for evocada.

<h2 id="posicionais_opcionais">Parâmetros posicionais opcionais</h2>

Os parâmetros posicionais opcionais funcionam de maneira semelhante aos parâmetros nomeados, porém, nesse caso, a necessidade de especificar o nome do parâmetro é trocado pela necessidade de manter a ordem em que foi implementado na função. De maneira direta, caso seja necessário atribuir um valor ao segundo parâmetro de uma função, é necessário que antes seja atribuído um valor ao primeiro.

Sua sintaxe também é bem simples, onde basta adicionar as variáveis entre colchetes **(** _[ ]_ **)**. Os valores que serão atribuídos aos parâmetros da função devem obedecer à ordem de implementação.

<h3 align="center">Utilizando parâmetros posicionais opcionais</h3>


~~~dart
void main() {
  // Utilizando parâmetros posicionais na ordem correta
  retornarPowerRanger(retornarEquipe, "Azul", false);
  // ↑ Experimente inverter a ordem dos parâmetros
  
  // Chamado de uma função sem a atribução da variável opcional
  retornarPowerRanger(retornarEquipe);
}

retornarEquipe(){
  print("Equipe: Dino Trovão \n");
}

retornarPowerRanger(Function equipe, [String cor = "Vermelho",
                                      bool lider = true,
                                     ]){
  
  print("Ranger: " + cor);
  
  if(lider){
    print("Ranger Lider");
  }
  
  equipe();
  
}
~~~

<p align="center">
    <a href="https://dartpad.dev/?id=0cab1dabe8248ccc498ea614bc3a5ed5">
        <img src="https://i.imgur.com/FPt9Avp.png" height="24">
    </a>
</p>

> Note que, caso as variáveis sejam atribuídas fora da ordem correta, será retornado um erro, informando que era esperado outro tipo de valor.

<p align="right">
    <a href="#sumario" style="font-size:1rem;font-weight: bold;">
        <img src="https://raw.githubusercontent.com/JosManoel/Dart-Study/main/images/icons/voltar_ao_topo.png" height="32">
    </a>
</p>

***

<h2 id="retorno">Valores de retorno</h2>

Assim como em outras linguagens, as funções na linguagem Dart podem retornar diversos tipos de valores, que podem ser observados no artigo ["Declarando variáveis em Dart"](https://github.com/JosManoel/Dart-Study/blob/main/topics/Declarando_variaveis.md). Esses valores de retorno podem ser extremamente úteis quando é necessário atribuir um valor diretamente a uma variável, como em situações onde é necessário utilizar funções para a realização de cálculos matemáticos.

<h3 align="center">Funções com retorno de valores</h3>

~~~dart
void main() {
  // Atribuindo valor a variável através do retorno da função
  String equipeRanger = retornarEquipe();
  
  retornarPowerRanger(equipeRanger, cor:"Azul");
}

// Implementando uma função que retorna uma string
String retornarEquipe(){
  String equipe = "Dino Trovão";
  
  // Retornando o valor da variável local
  return equipe;
  
  // Experimente retornar o valor sem utilizar a variável
  // Desta forma: return "Dino Trovão";
}

retornarPowerRanger(String equipe, {String cor = "Vermelho"}){
  print("Ranger: " + cor);
  print("Equipe: " + equipe);

}
~~~

<p align="center">
    <a href="https://dartpad.dev/?id=8d45a76f08967bf236304b2c59c52391">
        <img src="https://i.imgur.com/n6rDioU.png" height="24">
    </a>
</p>

<h2 id="void">Funções sem retorno</h2>

Em alguns casos, não será necessário que a função retorne algum valor ou resultado. Para estas ocasiões o dart possui um recurso que permite informar ao compilador quando uma função não possui um valor a ser retornado. Para utilizá-lo basta atribuir o valor **_void_** ao tipo da função.

<h3 align="center">Declarando funções sem valor de retorno</h3>


~~~dart
void main() {
  retornarPowerRanger(retornarEquipe, cor:"Azul");
  
}

// Declarando uma função sem valor de retorno
void retornarEquipe(){
  print("Equipe: Dino Trovão \n");
  
}

retornarPowerRanger(Function equipe, {String cor = "Vermelho"}){
  print("Ranger " + cor);
  equipe();
  
}
~~~

<p align="center">
    <a href="https://dartpad.dev/?id=424349115b44e8066206a661cf9bdeab">
        <img src="https://i.imgur.com/PKbQbxt.png" height="24">
    </a>
</p>

> O valor **void** também pode ser omitido da declaração da função, caso ela não retorne nenhum valor. No entanto, mantê-lo em seu código pode ajudá-lo durante o desenvolvimento. 

<p align="right">
    <a href="#sumario" style="font-size:1rem;font-weight: bold;">
        <img src="https://raw.githubusercontent.com/JosManoel/Dart-Study/main/images/icons/voltar_ao_topo.png" height="32">
    </a>
</p>


***

<h2 id="recursiva">Funções recursivas</h2>

As **funções recursivas** são funções capazes de chamar a si mesma até que uma condição estabelecida seja atendida. A utilização das funções recursivas pode ser de grande ajuda quando necessário realizar cálculos complexos, como cálculos de arranjos e problemas de probabilidade. 

As **funções recursivas** são bastantes uteis para quebrar grandes problemas em problemas menores, resolvendo uma seção por vez. Deste modo, **o problema obrigatoriamente deve ficar menor que o problema anterior a cada nova recursão**, caso contrário, a função entrará em um loop infinito, causando o estouro da memória utilizada para a resolução do problema. 

Normalmente, a estrutura de uma função recursiva é composta de duas partes:

  * **Base**: Onde acontece a verificação da condição de parada da recursividade e o retorno do valor final.

  * **Recursive**: Parte da função que chama a si mesma, mas desta vez, atribuindo novos valores aos parâmetros.

<h3 align="center">Estrutura de uma função recursiva</h3>

~~~dart
int recursiveFun(int n) {
  if(condition){
    // Base code
    return n;
    
  } 

  // Recursive code
  return recursiveFun(n);
  
}
  
~~~


<h2 id="declarando_recursiva">Declarando funções recursivas</h2>

Desta vez teremos um problema um pouco mais complexo para solucionar. Neste caso, calcularemos de quantas maneiras possíveis os Power Rangers podem combinar os ataques para formarem combos. Matematicamente este problema poderá ser resolvido através do cálculo de **arranjos simples**, que utiliza a seguinte fórmula:


<h3 align="center">Formula: Calculo de arranjos simples</h3>

<p align="center">
    <img src="https://images.educamaisbrasil.com.br/content/banco_de_imagens/mb/d/analise-combinatoria-arranjos-simples.jpg">
</p>

> De maneira resumida, um arranjo simples pode ser definido como todos os agrupamentos ordenados e sem repetição que podem ser formados a partir de um determinado conjunto de elementos.

Onde:

  * **Anp** -> Arranjo de **n** elementos por grupos de **p** em **p**
  * **n** -> Quantidade total de elementos
  * **p** -> Quantidade de elementos por grupamento

No nosso caso, como será um arranjo que engloba todos os elementos do conjunto, podemos resumir a função a apenas o cálculo de n! (fatorial), onde:

<p align="center">
    Resultado = n * (n-1) * (n-2) * ... * (1)
</p>

<h3 align="center">Declarando funções recursivas</h3>

~~~dart
void main() {

  // Experimente adicionar mais rangers a lista
  var listRangers = [
    "Ranger Rosa", 
    "Ranger Amarelo", 
    "Ranger Preto"
  ];
  
  print("Quant de combos: ${comboAtaqueRanger(listRangers.length)}");
}

// Função recursiva
int comboAtaqueRanger(int quantRangers){
  if(quantRangers <= 1){
    // Base code
    return 1;
    
  } else {
    // Recursive code
    return quantRangers*comboAtaqueRanger(quantRangers-1);
    
  }
}
  
~~~

<p align="center">
    <a href="https://dartpad.dev/?id=ed31db71e4e4e863dee74a8bb8d4d2e6">
        <img src="https://i.imgur.com/cvfueex.png" height="24">
    </a>
</p>


<p align="right">
    <a href="#sumario" style="font-size:1rem;font-weight: bold;">
        <img src="https://raw.githubusercontent.com/JosManoel/Dart-Study/main/images/icons/voltar_ao_topo.png" height="32">
    </a>
</p>

***

<h2 id="anonima">Funções anonimas</h2>

As **funções anônimas**, também chamadas de **funções lambda**, são importantes recursos presentes na maioria das linguagens de programação utilizadas no mercado. Através delas é possível passar funções inteiras para outros objetos sem a necessidade de atribuir um nome, simplificando a escrita do código. 

As funções anônimas podem possuir nenhum ou vários parâmetros e possuem todas as propriedades e sintaxe de uma função convencional, com exceção da necessidade de um nome.

<h3 align="center">Estrutura de uma função anônima</h3>

~~~dart
(lista_de_paranmetros) {
  // instruções
  return;
} 
~~~

Observe sua utilização usando o mesmo exemplo mostrado na utilização de funções como parâmetros, porém agora utilizando uma função anônima:

<h3 align="center">Utilizando uma função anônima</h3>

~~~dart
void main() {
  retornarPowerRanger("Vermelho", (){print("Equipe: Dino Trovão");});
}

retornarPowerRanger(String cor, Function equipe){
  print("Ranger " + cor);
  equipe();
}
~~~

<p align="center">
    <a href="https://dartpad.dev/?id=14c4c674a5cf676503650044b30df444">
        <img src="https://i.imgur.com/Ys7jUs9.png" height="24">
    </a>
</p>

<h2 id="anonima">Big Arrow Function</h2>

Caso você já utilize outras linguagens, pode ter sentido alguma estranheza ao verificar a [sintaxe contraída](#sintaxe_constraida) de uma função convencional e a sintaxe de uma função anônima, pela falta de uma **_arrow_** **(** _=>_ **)**.

Apesar do Dart também possuir suporte a utilização de uma **arrow** em funções, é importante destacar que, quando utilizado nesta linguagem, quando utilizado as chaves **(** _{ }_ **)** após uma **(** _=>_ **)** não é aberto um escopo de função e sim um [Map](https://github.com/JosManoel/Dart-Study/blob/main/topics/Declarando_variaveis.md#maps) ou um [Set](https://github.com/JosManoel/Dart-Study/blob/main/topics/Declarando_variaveis.md#maps), necessitando de uma sintaxe interna que corresponde a estes tipos, com a utilização de **virgula** para separar as instruções, ao invés do **ponto e virgula** convencional.

<h3 align="center">Estrutura de uma função anônima com arrow</h3>

~~~dart
(lista_de_paranmetros) => {
  instrucao1(),
  instrucao2()
} 
~~~


<h3 align="center">Utilizando uma função anônima com arrow</h3>

~~~dart
void main() {
  var listRangers = [
    "Rosa", 
    "Amarelo", 
    "Preto",
    "Azul",
    "Vermelho"
  ];
  
  listRangers.forEach((ranger) => {
      print("Ranger: " + ranger),
      print("Equipe: Dino Trovão \n")
    });
}
~~~

<p align="center">
    <a href="https://dartpad.dev/?id=975426b8c0489cf6d3e7b011d64ac1f6">
        <img src="https://i.imgur.com/lQP7q6K.png" height="24">
    </a>
</p>

<p align="right">
    <a href="#sumario" style="font-size:1rem;font-weight: bold;">
        <img src="https://raw.githubusercontent.com/JosManoel/Dart-Study/main/images/icons/voltar_ao_topo.png" height="32">
    </a>
</p>

***

<h2 id="main">Função principal</h2>

Até esse momento, você já deve ter notado que a função **main()** é necessária para o desenvolvimento em Dart, devido a sua presença em todos os exemplos. A função é um método predefinido no Dart usado para iniciar a aplicação. É dentro da **main()** que deve ser declarada todas as instruções do usuário, seja chamar outra função ou exibir valores na tela.

A função **main()** possui uma estrutura bem simples, sendo tipada como **void**, já que não retorna nenhum valor. Além disso, ela também possui os parâmetros opcionais **_List < String >_**, que podem ser utilizados em ocasiões que é necessário passar parâmetros para a aplicação através de outros meios, como o terminal ou prompt de comando. 

> Em sua maioria, os parâmetros opcionais da função main() não são utilizados no desenvolvimento convencional de aplicações, ficando a cargo de apps em command-line ou para fins didáticos. Caso seja necessário utilizar este recurso em sua aplicação, consulte a [documentação oficial](https://dart.dev/tutorials/server/cmdline).

<h3 align="center">Utilizando a função principal</h3>

~~~dart
void main() {
  var listRangers = [
    "Ranger Rosa", 
    "Ranger Amarelo", 
    "Ranger Preto",
    "Ranger Azul",
    "Ranger Vermelho"
  ];
  
  listRangers.forEach((ranger) => {print(ranger)});
}
  
~~~

<p align="center">
    <a href="https://dartpad.dev/?id=975426b8c0489cf6d3e7b011d64ac1f6">
        <img src="https://i.imgur.com/OwoPbEv.png" height="24">
    </a>
</p>


<p align="right">
    <a href="#sumario" style="font-size:1rem;font-weight: bold;">
        <img src="https://raw.githubusercontent.com/JosManoel/Dart-Study/main/images/icons/voltar_ao_topo.png" height="32">
    </a>
</p>

***
<h2 id="leitura_e_link"> 📚 Leitura e links recomendados </h2>

* [📝 Dart - Documentação](https://dart.dev/guides)
* [🎯 Funções em Dart #2](https://medium.com/@marcusedu7/fun%C3%A7%C3%B5es-em-dart-2-1f515dcab16)
* [🎯 Functions - Dart Fundamentals](https://androidatc.com/articles/Eng/Functions---Dart-Fundamentals#:~:text=A%20function%20in%20Dart%20or,result%2C%20or%20performs%20some%20operations.)
* [🎯 DART - FUNÇÕES](https://acervolima.com/dart-funcoes/)
* [🎯 DART - RECURSÃO](https://acervolima.com/dart-recursao/#:~:text=Recurs%C3%A3o%20em%20qualquer%20linguagem%20de,implementa%20recurs%C3%A3o%20de%20forma%20semelhante.)
* [🎯 DART - FUNÇÃO PRINCIPAL()](https://acervolima.com/dart-funcao-principal/)
* [🎯 Dart – Anonymous Functions](https://www.geeksforgeeks.org/dart-anonymous-functions/)
* [🎯 Como dart interpreta uma arrow em funções lambda/anônima](https://pt.stackoverflow.com/questions/450690/como-dart-interpreta-uma-x-y-z-arrow-em-fun%C3%A7%C3%B5es-lambda-an%C3%B4nima)
* [🎯 Video: Funções (Declaração, Parâmetros e Retorno)](https://www.youtube.com/watch?v=yjFNHxqM_Rw)
* [🎯 Video: Funções (Parâmetros Opcionais e Anônimos)](https://www.youtube.com/watch?v=mSO02fc3pwU)
* [🎯 Video: Dart - Curso Completo: Passando como parâmetro outra função](https://www.youtube.com/watch?v=m-u6J2QcTXw)
* [🎯 Video: Dart - Curso Completo: Funções Anônimas](https://www.youtube.com/watch?v=-pluRR798mc)

<p align="right">
    <a href="#sumario" style="font-size:1rem;font-weight: bold;">
        <img src="https://raw.githubusercontent.com/JosManoel/Dart-Study/main/images/icons/voltar_ao_topo.png" height="32">
    </a>
</p>

***
<h2 id="licenca"> 🧾Licença </h2>

Este projeto está sob a licença [Apache 2.0](https://github.com/JosManoel/Dart-Study/blob/main/LICENSE).

<p align="right">
    <a href="#sumario" style="font-size:1rem;font-weight: bold;">
        <img src="https://raw.githubusercontent.com/JosManoel/Dart-Study/main/images/icons/voltar_ao_topo.png" height="32">
    </a>
</p>
