<img src="https://i.imgur.com/mW5RYw5.png"> 

<p>

**Autor:**
  <a href="https://github.com/JosManoel">Manoel Freitas</a>
</p>

A necessidade de generalizar algoritmos no desenvolvimento de aplicações é algo que acompanha as tecnologias de programação desde o seu surgimento. Ao utilizar técnicas de generalização de algoritmos para diminuir a complexidade de um software não estamos apenas reduzindo o tamanho que ele ocupa no armazenamento, como também otimizando suas funcionalidade e tornando-o mais seguro e confiável. 

Dessa necessidade surgiram alguns paradigmas de programação para facilitar a criação de estruturas e regras de negócios, como a **programação orientada a objetos** e os **generics**, assunto que será abordado nesse tópico.

***
<h2 id="sumario">🧮 Sumário</h2>

  * <a href="#intro">Introdução a generics</a>
  * <a href="#generics">Utilizando generics</a>
    * <a href="#convencao">Convenções mnemônicas de utilização</a>
    * <a href="#collections">Collections literals</a>
  * <a href="#class">Generics e classes</a>
    * <a href="#class_methods">Métodos genéricos</a>
    * <a href="#class_restricted">Restringindo tipos genéricos</a>
  * <a href="#function">Generics e funções</a>
  * <a href="#leitura_e_link">📚 Leitura e links recomendados</a>
  * <a href="#licenca">🧾Licença</a>

***

<h2 id="intro">Introdução a generics</h2>

Os **generics** surgiram como mais uma ferramenta de generalização de algoritmos. Assim como na **programação orientada a objetos**, a principal função desse paradigma é evitar a repetição de código e tornar o script mais confiável, especialmente quando uma mesma função é utilizada com mais de um tipo de objeto. O conceito de **generic programming** funciona atribuindo itens genéricos às funções estabelecidas que serão substituídos no momento de sua atribuição a algum objeto ou utilização, agindo como um _"template"_ durante o desenvolvimento, evitando possíveis erros com tipos de dados.

De certo modo, o funcionamento dos **generics** é análogo às variáveis do tipo [**var**](https://github.com/JosManoel/Dart-Study/blob/main/topics/1-2_Declarando_variaveis.md#var), que inicialmente podem receber qualquer tipo de dado, mas mantém sua tipagem após a atribuição. Por essas características, o conceito de **generic programming** é algo específico de linguagens fortemente tipadas, como o Dart, o C# e o C++. No caso do C++ essa funcionalidade possui um nome mais descritivo, nomeada como _"template"_.

No Dart os **generics** são utilizados principalmente com [**Lists**](https://github.com/JosManoel/Dart-Study/blob/main/topics/1-2_Declarando_variaveis.md#list), [**Sets**](https://github.com/JosManoel/Dart-Study/blob/main/topics/1-2_Declarando_variaveis.md#sets), [**Maps**](https://github.com/JosManoel/Dart-Study/blob/main/topics/1-2_Declarando_variaveis.md#maps) e **Futures**, sendo esse último um modelo de programação assíncrona que será abordado nos próximos tópicos. A utilização de **generics** é vista como uma boa prática no desenvolvimento de aplicações com a linguagem Dart, visto que traz mais segurança para o software ao passo em que garante que os tipos dos dados serão respeitados.


<p align="right">
    <a href="#sumario">
        <img src="https://raw.githubusercontent.com/JosManoel/Dart-Study/main/images/icons/voltar_ao_topo.png" height="32">
    </a>
</p>

***

<h2 id="generics">Utilizando generics</h2>

Como mencionado anteriormente, os **generics** funcionam como um template para os tipos de dados atribuídos as coleções. Sua notação utiliza apenas os símbolos matemáticos **"<"** e **">"** para adicionar os argumentos genéricos ou outros parâmetros as coleções. Em versões anteriores do Dart a sua sintaxe também incluía o modificador **"new"**, assim como em outras estruturas, mas a sua obrigatoriedade foi removida nas versões mais recentes.

<h3 align="center">Generics - sintaxe</h3>

~~~dart

var variavel = Tipo_colecao <tipo_parametro ou letter_name> valores; 

~~~

Normalmente o parâmetro **_"Tipo_colecao"_** é atribuído com [**Lists**](https://github.com/JosManoel/Dart-Study/blob/main/topics/1-2_Declarando_variaveis.md#list), [**Sets**](https://github.com/JosManoel/Dart-Study/blob/main/topics/1-2_Declarando_variaveis.md#sets), [**Maps**](https://github.com/JosManoel/Dart-Study/blob/main/topics/1-2_Declarando_variaveis.md#maps) ou **Futures**, enquanto que o **_"tipo_parametro"_** segue o tipo dos dados adicionados. Nos generics o **_"letter_name"_** servirá como _"template"_ e pode assumir qualquer letra como nome, apesar de existir uma convenção recomendada quanto a sua utilização. 

Em contraste com outras linguagens como o Java, o Dart mantém o tipo **generic** durante a execução do código. Deste modo, torna-se possível verificar se uma variável é do tipo **generic** utilizando expressões booleanas comuns.

<h3 align="center">Verificando o tipo de um generic</h3>

~~~dart

var variavel = Tipo_colecao <tipo_parametro> valores; 

print(variavel is Tipo_colecao<tipo_paramentro>);

~~~

<p align="right">
    <a href="#sumario">
        <img src="https://raw.githubusercontent.com/JosManoel/Dart-Study/main/images/icons/voltar_ao_topo.png" height="32">
    </a>
</p>


<h2 id="convencao">Convenções mnemônicas de utilização</h2>

Apesar do **letter-name**, também chamado de **single-letter**, receber qualquer letra como nome, por convenção utiliza-se apenas as letras **E**, **T**, **S**, **K**, **U** e **V** para a atribuição de novos **generics**, onde cada uma dela possui uma função específica, como demonstrado a seguir:

* **E** - Utilizado quando a coleção recebe um **Elemento**;
* **K** e **V** - Atribuídos em pares, normalmente com maps, para **Keys** e **Values**;
* **R** - Recomendado em situações que o **generic** será utilizado para retornar valores;
* **T**, **U** e **S** - Recomendado para situações onde as **single-letters** anteriores já foram utilizadas.

Caso nenhum dos **single_letters** anteriores esteja disponível, recomenda-se utilizar um nome mnemônico que remeta a sua finalidade, costumando ser a primeira letra do nome da variável que será atribuída. Para informações mais detalhadas a respeito das boas práticas de utilização, acesse a [documentação oficial](https://dart.dev/guides/language/effective-dart/design#do-follow-existing-mnemonic-conventions-when-naming-type-parameters).


<p align="right">
    <a href="#sumario">
        <img src="https://raw.githubusercontent.com/JosManoel/Dart-Study/main/images/icons/voltar_ao_topo.png" height="32">
    </a>
</p>

<h2 id="collections">Collections literals</h2>

No desenvolvimento de software, um **literal** representa a notação de um valor fixo no código. Deste modo, as **collections literals** surgem como uma expressão sintática para a agregados de valores de um mesmo tipo, normalmente atribuídas as **Lists**, **Sets** e **Maps**. No Dart a sintaxe de uma **collection literal** segue a mesma estrutura da definição de um **generic**, excluindo apenas a utilização da **single-letter**.

<h3 align="center">Generics e collections literals - sintaxe</h3>

~~~dart

// Sintaxe de utilizacao com Lists
var colecao_1 = <tipo_valor>[valor1, valor2, valor3]; 

//Sintaxe de utilizacao com Sets
var colecao_2 = <tipo_valor>{valor1, valor2, valor3};

//Sintaxe de utlizacao com Maps
var colecao_3 = <tipo_key, tipo_valor>{
    key1 : valor1,
    key2 : valor2,
    key3 : valor3
};

~~~

Apesar de aparentar possuir uma sintaxe redundante, a utilização desse recurso permite restringir a entrada de novos valores nas coleções a apenas valores do tipo especificado, garantindo uma maior segurança na adição de dados durante a execução do algoritmo.

<p align="right">
    <a href="#sumario">
        <img src="https://raw.githubusercontent.com/JosManoel/Dart-Study/main/images/icons/voltar_ao_topo.png" height="32">
    </a>
</p>


***

<h2 id="class">Generics e classes</h2>

Vimos anteriormente que as classes possuem diversos elementos de abstração de algoritmo para reduzir a complexidade das estruturas de negócios e evitar a reescrita desnecessária de código. Com os **generics** as classes ganham um novo elemento para auxiliar no desenvolvimento de projetos, especialmente no uso de parâmetros com construtores e métodos. A sintaxe de utilização dos **generics** com classes segue os modelos anteriores, utilizando o tipo do parâmetro ou **single-letters** em sua atribuição, diferentemente do chamado de uma classe, que obrigatoriamente deve possuir o tipo do parâmetro que será atribuído.

<h3 align="center">Generics e classes - sintaxe</h3>

~~~dart

modificador class Classe_nome<tipo_parametro ou letter_name> {

    // metodos, construtores e outros elementos
}

void main(){
    var objeto = Classe_nome<tipo_parametro>();
}

~~~

<p align="right">
    <a href="#sumario">
        <img src="https://raw.githubusercontent.com/JosManoel/Dart-Study/main/images/icons/voltar_ao_topo.png" height="32">
    </a>
</p>


<h2 id="class_methods">Métodos genéricos</h2>

Apesar de inicialmente o Dart oferecer um suporte limitado a utilização de **generics** em classes, com a chegada das versões mais recentes os métodos das classes passaram a suportar o tipo genérico em seus parâmetros e em elementos de retorno. A utilização de um **generic** em um método segue a mesma sintaxe de método comuns, uma vez que as **single-letters** são tratadas como tipos convencionais, estendendo-se aos métodos **getters** e **setters**.

<h3 align="center">Métodos genéricos - sintaxe</h3>

~~~dart

modificador class Classe_nome<letter_name> {
    letter_name valor;

    // Metodo set
    void set_classe(letter_name valor);
    // Metodo get
    letter_name get_classe => valor;

    // Declarando um metodo com generics
    letter_name metodo_classe<letter_name>(letter_name parametro){
        //instrucoes
    }
}

void main(){
    var objeto = Classe_nome<tipo_parametro>();

    objeto.set_classe(valor);
}

~~~

Observe que, apesar de possuir uma sintaxe específica para a atribuição de **generics** nos métodos da classe, a utilização se dá mesma forma que um método convencional. Isso se deve ao fato de que após sua inicialização o objeto passa a possuir o tipo especificado em seus parâmetros, assim como ocorre com as varáveis do tipo **var**.

<h3 align="center">Métodos genéricos - Exemplo prático</h3>

~~~dart

import 'dart:math';

class Yugioh {
  late String name;
  late int atk;
  late int def;
  
  Yugioh(this.name, this.atk, this.def);
}

class Uno {
  late String name;
  
  Uno(this.name);
}

class Baralho<E> {
  final List<E> cards = [];
  
  void addCard(E card){
    cards.add(card);
  }
  
  E getRandomCard() => cards[Random().nextInt(cards.length)];
}

void main() {
  var deck = Baralho<Yugioh>();
  var baralho = Baralho<Uno>();

  deck.addCard(Yugioh("Kuriboh", 300, 200));
  deck.addCard(Yugioh("Dark Magician Girl", 2000, 1700));
  deck.addCard(Yugioh("Elfa Mistica", 800, 2000));
  var yugiohCard = deck.getRandomCard();
  print("Yugioh card: ${yugiohCard.name} Atk: ${yugiohCard.atk} Def: ${yugiohCard.def}");
  
  baralho.addCard(Uno("9"));
  baralho.addCard(Uno("reverso"));
  baralho.addCard(Uno("+4"));
  print("Uno card: ${(baralho.getRandomCard()).name}");
  
}
  
~~~

<p align="center">
    <a href="https://dartpad.dev/?id=22da8bc98351bf79ba10328e38f67820">
        <img src="https://i.imgur.com/knz0UaD.png" height="24">
    </a>
</p>

> Nesse exemplo utilizamos duas classes distintas para formar dois baralhos diferentes, um apenas com cards de Yu-Gi-Oh e outro apenas com cards de Uno. Note que, apesar de ser dois baralhos diferentes, os métodos e construtores utilizados são os mesmos. Além disso, observe que o próprio compilador se encarrega de impedir a adição de um elemento de um tipo diferente do especificado na criação do baralho.

<p align="right">
    <a href="#sumario">
        <img src="https://raw.githubusercontent.com/JosManoel/Dart-Study/main/images/icons/voltar_ao_topo.png" height="32">
    </a>
</p>


<h2 id="class_restricted">Restringindo tipos genéricos</h2>

Como observado anteriormente, os **generics** possuem um funcionamento semelhante às variáveis do tipo **var**, que após a implementação inicial de um valor assume o tipo do dado atribuído. Apesar de bastante útil durante o desenvolvimento, diferentemente de um **var** convencional, ainda podemos executar processos de atribuição de outros tipos de dados. Para solucionar este problema o Dart possui algumas ferramentas de restrição que limitam a entrada de valores. A sintaxe utiliza apenas a palavra-chave **extends** para informar a **single-letter** qual tipo de objeto ela deve aceitar.


<h3 align="center">Restrição de generics - sintaxe</h3>

~~~dart

class Classe_objeto{
    // Metodos, construtores, etc
}

class Classe_nome<letter_name extends Classe_objeto> {
    // Metodos, construtores, etc
}

void main(){
    var objeto = Classe_nome<Classe_objeto>();
}

~~~

<h3 align="center">Restrição de generics - Exemplo prático</h3>

~~~dart

import 'dart:math';

class Yugioh {
  late String name;
  Yugioh(this.name);
}

class Monster extends Yugioh{
  late int atk;
  late int def;
  
  Monster(String nome, this.atk, this.def) : super(nome);
  
  int getAtk() => atk;
  int getDef() => def;
}

class Spell extends Yugioh{
  late String descricao;
  
  Spell(String name, this.descricao) : super(name);
  String getDescricao() => descricao;
}

class Deck<E extends Yugioh> {
  final List<E> cards = [];
  
  void addCard(E card) => cards.add(card);
  E getRandomCard() => cards[Random().nextInt(cards.length)];
}

void main() {
  var deck = Deck<Yugioh>();

  deck.addCard(Monster("Kuriboh", 300, 200));
  deck.addCard(Monster("Dark Magician Girl", 2000, 1700));
  deck.addCard(Monster("Elfa Mistica", 800, 2000));
  deck.addCard(Spell("Buraco Negro", "Destrua todos os monstros em campo."));
  deck.addCard(Spell("Tufão Espacial Místico", "Escolha 1 Card Magia/Armadilha no campo; destrua o alvo."));

  print("Yugioh card: ${(deck.getRandomCard()).name}");
  
}
  
~~~

<p align="center">
    <a href="https://dartpad.dev/?id=b39861bd74cf4e81b985e823484a5b13">
        <img src="https://i.imgur.com/zt1oZjZ.png" height="24">
    </a>
</p>


<p align="right">
    <a href="#sumario">
        <img src="https://raw.githubusercontent.com/JosManoel/Dart-Study/main/images/icons/voltar_ao_topo.png" height="32">
    </a>
</p>

***

<h2 id="function">Generics e funções</h2>

Apesar de inicialmente o suporte a **generics** está limitado apenas as classes, com a chegada das versões mais recentes do Dart seu uso passou a ser suportado também por funções convencionais, com utilização semelhante aos métodos de uma classe. Sua sintaxe segue a mesma estrutura de um método convencional, sendo necessário adicionar as **single-letters** necessárias aos parâmetros da função.

<h3 align="center">Generics e funções - sintaxe</h3>

~~~dart

single-letter nome_da_funcao<single-letter>(Colecao<single-letter> parametro){
    // instrucoes
}


void main(){
    nome_da_funcao<tipo_parametro>();
}

~~~

> Note que o tipo da função é dado pelo seu retorno. Se a função não retornar nenhum valor, seu tipo será _void_. Caso ela retorne um elemento do mesmo tipo do **generic**, seu tipo será a mesma _named-letter_ utilizada.

<h3 align="center">Generics e funções - Exemplo prático</h3>

~~~dart

import 'dart:math';

class Yugioh {
  late String name;
  Yugioh(this.name);
}

class Monster extends Yugioh{
  late int atk;
  late int def;
  
  Monster(String nome, this.atk, this.def) : super(nome);
  
  int getAtk() => atk;
  int getDef() => def;
}

class Spell extends Yugioh{
  late String descricao;
  
  Spell(String name, this.descricao) : super(name);
  
  String getDescricao() => descricao;
}

class Deck<E extends Yugioh> {
  final List<E> cards = [];
  
  void addCard(E card) => cards.add(card);
  E getRandomCard() => cards[Random().nextInt(cards.length)];
  
  List<String> getDeck(){
    final List<String> cardsName = [];
    
    for(E card in cards){
      cardsName.add(card.name);  
    }
    return cardsName;
  }
}

void listDeck<D>(List<D> deck){
  print("Deck atual: ");
  for(D card in deck){print("${deck.indexOf(card) + 1}: ${card}");}
}

void main() {
  var deck = Deck<Yugioh>();

  deck.addCard(Monster("Kuriboh", 300, 200));
  deck.addCard(Monster("Dark Magician Girl", 2000, 1700));
  deck.addCard(Monster("Elfa Mistica", 800, 2000));
  deck.addCard(Spell("Buraco Negro", "Destrua todos os monstros em campo."));
  deck.addCard(Spell("Tufão Espacial Místico", "Escolha 1 Card Magia/Armadilha no campo; destrua o alvo."));

  print("Random card: ${(deck.getRandomCard()).name}");
  
  listDeck<String>(deck.getDeck());
  
}
  
~~~

<p align="center">
    <a href="https://dartpad.dev/?id=f77263778e7316ac3ac7f6841d151123">
        <img src="https://i.imgur.com/Fv9xlo5.png" height="24">
    </a>
</p>

<p align="right">
    <a href="#sumario">
        <img src="https://raw.githubusercontent.com/JosManoel/Dart-Study/main/images/icons/voltar_ao_topo.png" height="32">
    </a>
</p>

***

<h2 id="leitura_e_link">📚 Leitura e links recomendados</h2>


* [📝 Dart - Documentação](https://dart.dev/guides/language/language-tour#generics)
* [🎯 Dart - mnemonic conventions when naming type parameters](https://dart.dev/guides/language/effective-dart/design#do-follow-existing-mnemonic-conventions-when-naming-type-parameters)
* [🎯 Generics in Dart and Flutter](https://dart.academy/generics-in-dart-and-flutter/)
* [🎯 Como utilizar generics no Dart](https://www.treinaweb.com.br/blog/como-utilizar-generics-no-dart)
* [🎯 Video: Introdução a generics](https://www.youtube.com/watch?v=CG0tZFCXU5w)
* [🎯 Video: Restringindo o tipo parametrizado](https://www.youtube.com/watch?v=gB-kSTNTXIQ)
* [🎯 Video: Genérics em funções](https://www.youtube.com/watch?v=Rn1hBudNFKc)


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
