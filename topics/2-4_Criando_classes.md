<img src="https://i.imgur.com/svJjUJv.png"> 

<p>

**Autor:**
  <a href="https://github.com/JosManoel">Manoel Freitas</a>
</p>
 
Assim como o Java, C# e o Python, o Dart também oferece suporte a **programação orientada a objetos (POO)**, um paradigma da programação que utiliza o conceito de objetos no desenvolvimento de software. Utilizar a orientação a objetos no desenvolvimento de aplicações pode trazer diversas vantagens, como a facilidade de leitura e compreensão do código e a facilidade para criar grandes programas. Neste tópico, compreenderemos o POO e como utilizá-lo com o Dart.

***
<h2 id="sumario">🧮 Sumário</h2>

  * <a href="#introPoo">Introdução a POO</a>
    * <a href="#Class_object">Classes e objetos</a>
    * <a href="#Encapsulamento">Encapsulamento</a>
    * <a href="#Herança">Herança</a>
    * <a href="#Poliformismo">Polimorfismo</a>
  * <a href="#classes">Programação Orientada a objetos com Dart</a>
    * <a href="#objetos">Criando classes</a>
  * <a href="#atributos">Atributos variáveis de instância</a>
  * <a href="#construtores">Utilizando construtores</a>
      * <a href="#constDefault">Default constructor</a>
      * <a href="#constNamed">Named constructor</a>
      * <a href="#constRedirect">Redirect constructor</a>
      * <a href="#constConstant">Constant constructor</a>
      * <a href="#constFactory">Factory constructor</a> 
  * <a href="#metodos">Métodos</a>
      * <a href="#gets_sets">Gets e sets</a>
      * <a href="#operators">Operators</a>
  * <a href="#Extends">Herança e extends</a>
    * <a href="#Abstradas">Classes abstratas</a>
    * <a href="#interface_implicita">Interfaces implicitas</a>
    * <a href="#Mixins">Mixins</a>
  * <a href="#enumerated">Enumerated types</a> 
    * <a href="#enhanced">Enhanced Enums</a>
  * <a href="#leitura_e_link">📚 Leitura e links recomendados</a>
  * <a href="#licenca">🧾Licença</a>

***
<h2 id="introPoo">Introdução a POO</h2>

A programação orientada a objetos surgiu como uma alternativa a **programação estruturada**, que utilizamos nos exemplos até este momento, com comandos executados em sequências controladas por condicionais e repetições. 

Um dos diferenciais entre  a **programação estruturada (PE)** e a **POO** está no acesso á variáveis, que na **PE** se limita a apenas ao escopo de uma função ou a utilização de modificadores, como o **const** e o **final**, já na **POO** temos a possibilidade de deixá-la disponível para apenas algumas rotinas do software.

O desenvolvimento com **POO** pode abrir inúmeras novas possibilidades, mas antes de utilizá-lo é necessário compreender seus pilares e conceitos chaves.

<h2 id="Class_object">Classes e objetos</h2>

As **classes** e **objetos** são a base da **POO**. Podemos definir as **classes** como um conjunto de características e comportamentos que compreendem um conjunto de objetos. Já os **objetos** podem ser entendidos como entidades ou elementos dotados de atributos e métodos, atribuidos pela classe.

Podemos tomar como exemplo os pokemons, que possuem tipos e habilidades. Poderíamos definir uma **classe** que contém o _tipo_ fogo e a _habilidade_ blaze. Ao definir esta classe, teríamos como objetos alguns pokemons que possuem essas características, como o Charmander, o Charizard e o Combusken.

<h3 align="center">Classes, objetos e pokemons</h3>

<p align="center">
    <img src="https://i.imgur.com/oGzDYTy.png" width="600"> 
</p>

Observe que a classe é um elemento abstrato. O ato de atribuir as características de uma classe a um objeto para torná-lo concreto é chamado de **instanciação da classe**.

<p align="right">
    <a href="#sumario">
        <img src="https://raw.githubusercontent.com/JosManoel/Dart-Study/main/images/icons/voltar_ao_topo.png" height="32">
    </a>
</p>

<h2 id="Encapsulamento">Encapsulamento</h2>

Apesar de bastante úteis, os métodos e atributos possuem um pequeno problema: o acesso por outras partes do software. Dado que um objeto é definido por seus atributos e métodos, deixá-los expostos pode causa sérios problemas para a execução do programa. Como exemplo disto, poderíamos ter alguma função causando a modificação indesejada de algum atributo de objeto importante, gerando inúmeros erros de execução. 

Para contornar este problema, a programação orientada a objetos possui um conceito bastante útil, denominado **encapsulamento**. 

O encapsulamento é uma característica presente em todos os objetos e determina a visibilidade de um atributo ou método ao mesmo tempo em que garante a sua imutabilidade. Seguindo o exemplo dos pokemons, poderíamos dizer que _tipo_ e a _habilidade_ do pokemon estão encapsulados, sendo possível apenas visualizá-los.

<h3 align="center">Encapsulamento de um objeto</h3>

<p align="center">
    <img src="https://i.imgur.com/0xiBWQX.png" width="600"> 
</p>

> Quando um objeto possui atributos encapsulados a única maneira de alterá-los é efetuada através das ferramentas de **getters** e **setters**, que serão abordados posteriormente.

<p align="right">
    <a href="#sumario">
        <img src="https://raw.githubusercontent.com/JosManoel/Dart-Study/main/images/icons/voltar_ao_topo.png" height="32">
    </a>
</p>

<h2 id="Herança">Herança</h2>

Na programação orientada a objetos o conceito de herança é responsável por permitir o compartilhamento de funcionalidades entre classes, evitando assim a reescrita desnecessária de código, também chamada por código duplicado. Normalmente a herança acontece em níveis de hierarquia, onde a classe mais abaixo sempre herda os atributos das classes acima na hierarquia. 

<h3 align="center">Herança de propriedades</h3>

<p align="center">
    <img src="https://i.imgur.com/7jpaShI.png" width="500"> 
</p>

> É comum a utilização dos termos "Pai" e "Filho" para representar o nível hierárquico entre as classes.

Perceba que, neste exemplo, temos "Charmander", classe pai, compartilhando os atributos de _tipo_ e _habilidade_ com as outras duas classes filho: "Charmeleon" e "Charizard". Deste modo, temos a mesma habilidade sendo utilizada por todas as classes, eliminando a necessidade de duplicar esta informação. 

No Dart, ainda possuímos uma segunda maneira de compartilhar métodos entre classes, denominada **Mixins**, que será abordada posteriormente.

<p align="right">
    <a href="#sumario">
        <img src="https://raw.githubusercontent.com/JosManoel/Dart-Study/main/images/icons/voltar_ao_topo.png" height="32">
    </a>
</p>

<h2 id="Poliformismo">Polimorfismo</h2>

Tomando o caso anterior como exemplo, vimos que as funcionalidades podem ser compartilhadas entre classes, como no caso do "Charmander" e do "Charizard". No entanto, a herança não se restringe apenas as classes de mesmo tipo, nesse caso, pokemons. Partindo da classe "Charmander", podemos definir a habilidade "Blaze" para qualquer outra classe que herde essa função, mesmo que ela não funcione da mesma maneira que na classe pai. Quando ambas as classes possuem o mesmo método, mas com implementações diferentes, temos o que na POO é denominado **polimorfismo**. 

O Polimorfismo, de maneira geral, pode ser entendido como a implementação de um mesmo método de maneira distinta em ambas as classes.

<h3 align="center">Aplicações do polimorfismo</h3>

<p align="center">
    <img src="https://i.imgur.com/DvHOdq0.png" width="500"> 
</p>

Note que a habilidade "Blaze" pode ser utilizada tanto pelo "Charizard" como também pelo "Lança-chamas", apesar das duas clases executarem essa função de maneira diferente.

<p align="right">
    <a href="#sumario">
        <img src="https://raw.githubusercontent.com/JosManoel/Dart-Study/main/images/icons/voltar_ao_topo.png" height="32">
    </a>
</p>


***

<h2 id="classes">Programação Orientada a objetos com Dart</h2>

Assim como mencionado anteriormente, o Dart é uma linguagem orientada a objetos com herança baseada em mixins, que assegura que todas as classes possuam uma **superclasse**. Deste modo, podemos atribuir um conjunto de características a uma classe sem a necessidade de usar o método de herança convencional. 

Estas e outras peculiaridades da **POO** em Dart serão abordadas posteriormente. Por hora, definiremos a implementação e sintaxes das classes e objetos.

<h2 id="objetos">Criando Classes</h2>

A sintaxe de uma classe em dart é bastante semelhante as utilizadas em outras linguagens, como o javascript e o C. Nela, além da palavra-chave **class**, que determina o início de uma classe, também possuímos outros elementos como o **nome da classe** e seu corpo, responsável por conter os construtores, métodos, etc.

<h3 align="center">Sintaxe de uma classe</h3>

~~~dart

class Nome_da_classe{
    //Construtores, metodos e outros atributos

}

~~~

<h3 align="center">Construindo uma classe - Exemplo prático</h3>

~~~dart

class Pokemon {
    //Construtores, metodos e outros atributos
}

main() { 
   
}   
~~~

<p align="center">
    <a href="https://dartpad.dev/?id=b469098e84a931f282dff439e038a259">
        <img src="https://i.imgur.com/7NrzeaR.png" height="24">
    </a>
</p>

<p align="right">
    <a href="#sumario">
        <img src="https://raw.githubusercontent.com/JosManoel/Dart-Study/main/images/icons/voltar_ao_topo.png" height="32">
    </a>
</p>

***

<h2 id="atributos">Atributos e variáveis de instância</h2>

As classes em Dart podem possuir alguns atributos, como os tipos de um pokemon, mencionados nos tópicos acima. Os atributos podem ser descritos como pequenas informações armazenadas pelo objeto que serão utilizadas posteriormente para retornar outros valores. Os atributos podem possuir qualquer um das categorias de [variáveis](https://github.com/JosManoel/Dart-Study/blob/main/topics/1-2_Declarando_variaveis.md) suportados pelo Dart.

<h3 align="center">Sintaxe de uma classe - Atributos</h3>

~~~dart

class Nome_da_classe{
    //Atributos
    int atributo1 = 1;
    bool atributo2 = true;
    String atributo3 = "nome";

    //Construtores, metodos e etc

}

~~~


Os atributos de um objeto podem ser modificados ou recuperados através dos métodos getters e setters, sejam eles implícitos ou explícitos. A utilização desses métodos será abordada posteriormente.

Existem casos em que será necessário adicionar variáveis que terão seus valores atribuídos apenas na criação do objeto. A essas variáveis damos o nome de variáveis de instância. Sua utilização é bastante semelhante aos atributos convencionais, porém com a adição de algumas palavras reservadas para atribuição de instâncias, sendo uma delas a **"late"**, que antecede uma variável de instância que será inicializada apenas no momento da construção do objeto, evitando erros de atribuição.

<h3 align="center">Sintaxe de uma classe - Variáveis de instância</h3>

~~~dart

class Nome_da_classe{
    //Atributos
    late String instancia1;
    String? instancia2;

    //Construtores, metodos e etc

}

~~~

> Note que a variável _"instancia2"_ foi definida como uma String **?**. Esta modificação é necessária porque a variável do tipo String não pode ser inicializada com valor nulo. Ao adicionar este modificador, o Dart entende que essa variável será iniciada com valor nulo, cessando os erros. Esta mesma função pode ser executada ao adicionar o modificador _"late"_.

Assim como outras partes do código, também podemos utilizar os modificadores de imutabilidade para atribuir instâncias a classe, como o **final**. Entretanto, ainda será necessário o uso do **late** com variáveis que não suportam a inicialização com valor nulo, como as _Strings_.

<h3 align="center">Variáveis de instância - Utilizando modificadores</h3>

~~~dart

class Nome_da_classe{
    //Atributos
    late final String instancia1;
    //Construtores, metodos e etc

}

~~~

<h3 align="center">Instanciando uma variável - Exemplo prático</h3>

~~~dart

class Pokemon {
    late final String tipo;

    //Construtores, metodos e outros atributos
}

main() { 
   
}   
~~~

<p align="center">
    <a href="https://dartpad.dev/?id=38542155ee65f6bbcc681b965b448a43">
        <img src="https://i.imgur.com/uBF2PTa.png" height="24">
    </a>
</p>

<p align="right">
    <a href="#sumario">
        <img src="https://raw.githubusercontent.com/JosManoel/Dart-Study/main/images/icons/voltar_ao_topo.png" height="32">
    </a>
</p>

*** 

<h2 id="construtores">Utilizando construtores</h2>

Quando estamos trabalhando como a programação orientada a objetos é comum a utilização de construtores, pequenos métodos responsáveis por realizar as inicializações dos objetos, quando são chamados. Assim como os outros métodos de uma classe, um construtor pode ser entendido como uma função exclusiva da classe que é invocada no momento da inicialização. No entanto, apesar da semelhança com outras funções de uma classe, uma **subclasse não pode herdar os construtores de sua superclasse**, sendo necessário mencioná-la quando esta operação for necessária, através da palavra-chave **"super"**, que será abordada nesse tópico.

Os construtores possuem uma sintaxe semelhante à atribuição de uma variável convencional. Observe que, na prática, um objeto é declarado utilizando os mesmos operadores de atribuição de uma variável convencional.

<h3 align="center">Construtores - Iniciando um objeto</h3>

~~~dart

class Nome_da_classe{
    //Atributos
    late final String instancia1;
    //Construtores, metodos e etc

}

main(){
    Nome_da_classe nome_do_objeto = Nome_da_classe();
    // Nesse exemplo, o construtor é o "Nome_da_classe()"
    // que é atribuido ao objeto "nome_do_objeto"
}
~~~

> Note que o objeto possui o tipo da classe a qual ele será construído. O Dart também suporta o uso do tipo **var** para tipos de objetos, apesar de seu uso excessivo não ser recomendado.

<p align="right">
    <a href="#sumario">
        <img src="https://raw.githubusercontent.com/JosManoel/Dart-Study/main/images/icons/voltar_ao_topo.png" height="32">
    </a>
</p>

<h2 id="constDefault">Default constructor</h2>


No Dart, todas classes por padrão recebem um **"default constructor"**, que não possui nenhum argumento ou tratamento de instância. O **default constructor** pode ser utilizado diretamente na instanciação de uma classe, sem a necessidade de outros elementos, como no exemplo anterior.

<h3 align="center">Default Constructor - Criando um objeto</h3>

~~~dart

class Pokemon {
    late final String tipo;

    //Construtores, metodos e outros atributos
}

main() { 
  
  Pokemon pokemon_4 = Pokemon();
   
} 
~~~

<p align="center">
    <a href="https://dartpad.dev/?id=cdbc31a8bc87c65df992877dbe5cb520">
        <img src="https://i.imgur.com/xAqFCMT.png" height="24">
    </a>
</p>

Note que podemos utilizar o **construtor padrão** de diferentes formas, incluindo opções onde é são incluídas as variáveis de instância, para serem atribuídas no momento da criação do artigo. Abaixo teremos algumas sintaxes suportadas para os construtores pelo Dart.

<h3 align="center">Construtor padrão - Construtor parametrizado</h3>

~~~dart

class Nome_da_classe{
    //Atributos
    late String instancia1;
    late String instancia2;

    //Construtor
    Nome_da_classe(String instancia1, String instancia2){
        this.instancia1 = instancia1;
        this.instancia2 = instancia2;

        // Atribuindo o valor dos parametros do construtor
        // nas variáveis de instancia
    }
    
    // Metodos e etc
}

main(){
    Nome_da_classe nome_do_objeto = Nome_da_classe("string 1", "string2");
    // Criando o objeto "nome_do_objeto" e atribuindo "string1" para o
    // parametro "instancia1" e "string2" para o parametro "instancia2"
}
~~~

<h3 align="center">Construtor parametrizado - Sintaxe reduzida</h3>

~~~dart

class Nome_da_classe{
    //Atributos
    late String instancia1;
    late String instancia2;

    //Construtor
    Nome_da_classe(this.instancia1, this.instancia2);
    // Funciona da mesma forma que a anterior, porém reduzida
    
    // Metodos e etc
}

main(){
    Nome_da_classe nome_do_objeto = Nome_da_classe("string 1", "string2");
    // Criando o objeto "nome_do_objeto" e atribuindo "string1" para o
    // parametro "instancia1" e "string2" para o parametro "instancia2"
}
~~~

<h3 align="center">Construtor parametrizado - outra sintaxe</h3>

~~~dart

class Nome_da_classe{
    //Atributos
    late String instancia1;
    late String instancia2;

    //Construtor
    Nome_da_classe(String instancia1, String instancia2):
        instancia1 = instancia1,
        instancia2 = instancia2;
    
    // Metodos e etc
}

main(){
    Nome_da_classe nome_do_objeto = Nome_da_classe("string 1", "string2");
}
~~~

> Apesar de ter várias formas de declaração, a documentação do dart considera como "boa prática" apenas a utilização da sintaxe reduzida.

<p align="right">
    <a href="#sumario">
        <img src="https://raw.githubusercontent.com/JosManoel/Dart-Study/main/images/icons/voltar_ao_topo.png" height="32">
    </a>
</p>

<h2 id="constNamed">Named constructor</h2>

Os construtores do tipo **"named constructor"** possuem um funcionamento semelhante ao **default constructor**, porém com adição de uma "tag" que identifica seu chamado. A utilização de um **"named constructor"** permite que uma mesma classe tenha inúmeros construtores além do construtor padrão, bastante útil quando são necessários diferentes tipos de tratamento para uma mesma instancia em uma classe.

<h3 align="center">Construtor nomeado - sintaxe</h3>

~~~dart

class Nome_da_classe{
    //Atributos
    late String instancia1;
    late String instancia2;

    //Construtor 1
    Nome_da_classe(this.instancia1, this.instancia2);


    //Construtor 2
    Nome_da_classe.construtor2(String instancia1, String instancia2):
        instancia1 = instancia1,
        instancia2 = instancia2;
    
    // Metodos e etc
}

main(){
    Nome_da_classe nome_do_objeto = Nome_da_classe.construtor2("string 1", "string2");
}
~~~


<h3 align="center">Construtor nomeado - exemplo prático</h3>

~~~dart

class Pokemon {
  late String tipo;
  late String nome;
  
  Pokemon.fogo(this.nome){
    tipo = "Fogo";
  }
  
  //Metodos e outros atributos
}

main() { 
  Pokemon pokemon_4 = Pokemon.fogo("Charmander");

  //Imprime o nome do pokemon
  print(pokemon_4.nome);
  //Imprime o tipo do pokemon
  print(pokemon_4.tipo);
   
} 

~~~

<p align="center">
    <a href="https://dartpad.dev/?id=214de8a179a166a80b50300f7c29db4c">
        <img src="https://i.imgur.com/jA2vB5x.png" height="24">
    </a>
</p>

> Para recuperar o valor de um parâmetro, utilizamos o nome da instância após o objeto. A recuperação de valores.

> Experimente criar outro pokemon utilizando o construtor padrão.

Note que ao utilizar um construtor nomeado é possível atribuir valores as propriedades do objeto sem modificar o construtor padrão. 

<p align="right">
    <a href="#sumario">
        <img src="https://raw.githubusercontent.com/JosManoel/Dart-Study/main/images/icons/voltar_ao_topo.png" height="32">
    </a>
</p>

<h2 id="constRedirect">Redirect constructor</h2>

Durante o desenvolvimento em Dart, com a utilização de construtores nomeados, existirão situações onde o propósito de um construtor é redirecionar para outro construtor da mesma classe, tendo apenas algum tratamento simples de parâmetros, como ocorreu no exemplo prático anterior. Para esses casos o Dart possui um terceiro construtor chamado **"redirect construtor"**, responsável por chamar outro construtor.

<h3 align="center">Redirect constructor - sintaxe</h3>

~~~dart

class Nome_da_classe{
    //Atributos
    late String instancia1;
    late String instancia2;

    //Construtor 1
    Nome_da_classe(this.instancia1, this.instancia2);

    //Construtor redirecionado
    Nome_da_classe.construtor2(String inst1) : this(inst1, "string2");
    
    // Metodos e etc
}

main(){
    Nome_da_classe nome_do_objeto = Nome_da_classe.construtor2("string 1");
}

~~~

> Perceba que, para redirecionar para o construtor padrão, utilizamos a palavra-chave _"this"_.

<h3 align="center">Redirect constructor - exemplo prático</h3>

~~~dart

class Pokemon {
  late String tipo;
  late String nome;
  
  Pokemon(this.tipo, this.nome);
  
  Pokemon.fogo(String nome) : this("fogo", nome);
  Pokemon.agua(String nome) : this("agua", nome);

  //Metodos e outros atributos
}

main() { 
  Pokemon pokemon_4 = Pokemon.fogo("Charmander");
  Pokemon pokemon_7 = Pokemon.agua("Squirtle");
  
  print("Pokemon 004: ${pokemon_4.nome} | tipo: ${pokemon_4.tipo}");
  print("Pokemon 007: ${pokemon_7.nome} | tipo: ${pokemon_7.tipo}");
   
} 

~~~

> Neste exemplo é utilizado dois construtores nomeados que redirecionam para o construtor padrão.

<p align="center">
    <a href="https://dartpad.dev/?id=beb219c1af66c631745aea5345e19884">
        <img src="https://i.imgur.com/l3wPd9K.png" height="24">
    </a>
</p>

O **redirect constructor** também pode ser utilizado para redirecionar um construtor para um contrutor de uma superclasse, bastante útil quando considerado que os construtores não herdados.

<h3 align="center">Redirect constructor com superclass</h3>

~~~dart

class Classe_pai{
    late int inst_pai;

    Classe_pai.construtor_pai(int inst){
        this.inst_pai = inst + 1;
    }
}

class Classe_filho extends Classe_pai{
    late int inst_filho;

    //Construtor redirecionado
    Classe_filho.construtor_filho(int inst) : super.construtor_pai(inst);
    
    // Metodos e etc
}

main(){
    Classe_filho objeto = Classe_filho.construtor_filho(1);
}

~~~

> Uma **superclasse** é a classe que está acima da classe atual na hierarquia da herança de classes. Este assunto será melhor abordado no tópico sobre herança e mixins.

> "Extends" e "super" são palavras utilizadas para referenciar a superclasse. A utilização delas será detalhada nas discussões sobre herança.

<p align="right">
    <a href="#sumario">
        <img src="https://raw.githubusercontent.com/JosManoel/Dart-Study/main/images/icons/voltar_ao_topo.png" height="32">
    </a>
</p>

<h2 id="constConstant">Constant constructor</h2>

O **constant constructor** é utilizado em situações onde o objeto criado não irá mudar, existindo a necessidade de manter suas instâncias imutáveis durante a execução de todo o código. Sua sintaxe é bastante simples, se assemelhando a utilização do **Default constructor**, exigido apenas que as variáveis de instância possuam o modificador **_final_**.

<h3 align="center">Constant constructor - sintaxe</h3>

~~~dart

class Classe_imutavel{
    final int instancia;

    // Constant constructor
    const Classe_imutavel(this.instancia);
}

main(){
    Classe_imutavel objeto = const Classe_imutavel(1);
}

~~~

Entretanto, apesar de se chamar **constant constructor**, nem sempre o uso desse construtor irá retornar um objeto constante, visto que isso também depende da forma que o objeto é criado, sendo necessário utilizar o modificador **"const"** na invocação. 

<h3 align="center">Constant constructor - objetos</h3>

~~~dart

main(){
    // Esse chamado cria um objeto constante
    Classe_imutavel objeto = const Classe_imutavel(1);

    // Esse chamado não cria um objeto constante
    Classe_imutavel objeto = Classe_imutavel(1);
}

~~~

<p align="right">
    <a href="#sumario">
        <img src="https://raw.githubusercontent.com/JosManoel/Dart-Study/main/images/icons/voltar_ao_topo.png" height="32">
    </a>
</p>

<h2 id="constFactory">Factory constructor</h2>

O **constructor factory** possui um funcionamento um pouco diferente do que estamos habituados até agora. Enquanto os outros **generative constructors** ( default, named, constant e redirect) sempre retornam um novo objeto, independente de já existir ou não outro objeto com o mesmo nome e mesmos atributos, o **constructor factory** permite executar uma série de tratamentos e verificações antes de retornar o elemento. Outra diferença dele com os construtores vistos até agora é a necessidade da palavra-chave **"return"** e do modificador **factory** antes da declaração do construtor.

<h3 align="center">Factory constructor - exemplo de sintaxe</h3>

~~~dart

class Classe_pai{
    int inst_pai;

    // Factory constructor
    factory Classe_pai(this.inst_pai){
        // Tratamento de instancia

        if(inst_pai == 1){
            // retorna um objeto do tipo classe_filho1
            return Classe_filho1(inst_pai);
        }
        else{
            // retorna um objeto do tipo classe_filho2
            return Classe_filho2(inst_pai);
        }

        // Esse procedimento só é executado com subclasses
    }

    // Métodos, etc
}

class Classe_filho1 extends Classe_pai{
    int instancia;
    Classe_filho1(this.instancia);
}

class Classe_filho2 extends Classe_pai{
    int instancia;
    Classe_filho1(this.instancia);
}

main(){
    var objeto = Classe_pai(1);
    //retorna um objeto do tipo Classe_filho1
}

~~~

Normalmente, o **constructor factory** desempenha dois papeis, dependendo da necessidade, sendo um deles o papel de "esconder" a lógica de negócios do cliente, que em nosso caso é o método **main()**. Esta função é bastante útil em situações em que possuímos uma classe estendendo seus métodos para outras subclasses, mas queremos manter uma interface de simples, invocando apenas a superclasse, como no exemplo anterior. 

<h3 align="center">Factory constructor - exemplo prático</h3>

~~~dart

class Pokemon {
  late String tipo;
  late String nome;
  
  Pokemon(this.tipo, this.nome);
  
  factory Pokemon.criarPokemon(String tipo, String nome){
    if(tipo == "Fogo") return Fogo("Fogo",nome);
    if(tipo == "Agua") return Agua("Agua",nome);
    if(tipo == "Grama") return Grama("Grama", nome);
    
    return Pokemon(tipo, nome);
  }
}

class Fogo extends Pokemon{
  Fogo(String tipo, String nome) : super(tipo, nome);
}

class Agua extends Pokemon{
  Agua(String tipo, String nome) : super(tipo, nome);
}

class Grama extends Pokemon{
  Grama(String tipo, String nome) : super(tipo, nome);
}

main() { 
  Pokemon pokemon_1 = Pokemon.criarPokemon("Grama","Bulbasaur");
  Pokemon pokemon_4 = Pokemon.criarPokemon("Fogo","Charmander");
  Pokemon pokemon_7 = Pokemon.criarPokemon("Agua","Squirtle");
  
  print("Pokemon 001: ${pokemon_1.nome} | tipo: ${pokemon_1.tipo}");
  print("Pokemon 004: ${pokemon_4.nome} | tipo: ${pokemon_4.tipo}");
  print("Pokemon 007: ${pokemon_7.nome} | tipo: ${pokemon_7.tipo}");
   
} 

~~~

> Observe que, apesar de ter uma implementação parecida com apenas uma função nomeada, a criação de um novo Pokemon ficou bem mais legível, além de manter o código melhor organizado.

<p align="center">
    <a href="https://dartpad.dev/?id=d2f69592d38d527c98ba79158e729b82">
        <img src="https://i.imgur.com/ymD1m0l.png" height="24">
    </a>
</p>

O **factory constructor** também possui um importante papel no auxílio com objetos em ambientes limitados. Em alguns casos, teremos elementos que proporcionarão uma alta taxa de consumo de recursos, como memória, diminuindo o desempenho da aplicação quando temos a criação de diversos elementos desnecessários. Para estes casos, com o auxílio de um **cache**, o **factory constructor** pode verificar se um objeto já existe antes de criá-lo novamente, impedindo o desperdício de recursos.

Normalmente esta função é exemplificada utilizando a construção de um logger, como no exemplo abaixo:

<h3 align="center">Factory constructor - Utilizando um cache</h3>

~~~dart

class Logger {
  final String name;
  
  // Cache utilizando um Map
  static final Map<String, Logger> _cache =
      <String, Logger>{};

  // Factory constructor
  factory Logger(String name) {
    return _cache.putIfAbsent(
        name, () => Logger._internal(name));
  }
  
  // Construtor interno para o factory constructor
  Logger._internal(this.name){
     print("Novo objeto criado com o nome ${this.name}");
  }
}

class A{
  late final Logger _logger;
  
  A(){
    _logger = Logger("A");
  }
}

main() {
   for(int i=1;i<=5;i++){
     print("Criando um objeto. Ciclo: ${i}");
     A a = A();
     print(""); //newline
   }
}

~~~


<p align="center">
    <a href="https://dartpad.dev/?id=aa518428f3e76f3cbe850f981aa4f2c5">
        <img src="https://i.imgur.com/UwMCHhv.png" height="24">
    </a>
</p>

> Neste exemplo é utilizado o método **_"putIfAbsent"_**, da biblioteca **dart:core**, no **factory constructor**. O **_"putIfAbsent"_** tem o papel de verificar se um elemento criada já exise no cache e, caso não exista, chama o construtor interno para criar um novo objeto. Mas, para o caso do elemento já existir, ele apenas retorna o objeto já criado. Para mais informações, acesse sua [documentação](https://api.dart.dev/stable/2.17.5/dart-core/Map/putIfAbsent.html).

> Experimente modificar o nome do objeto "A" a cada ciclo.

Note que, ao executar este código, o objeto nomeado com "A" é criado apenas no primeiro ciclo. Para os outros ciclos, o construtor apenas retornar o elemento já criado. 

<p align="right">
    <a href="#sumario">
        <img src="https://raw.githubusercontent.com/JosManoel/Dart-Study/main/images/icons/voltar_ao_topo.png" height="32">
    </a>
</p>

***

<h2 id="metodos">Métodos</h2>

Na programação orientada a objetos as classes podem possuir sub-rotinas em seu escopo que são análogas às [funções](https://github.com/JosManoel/Dart-Study/blob/main/topics/2-1_Criando_funcoes.md) que vimos recentemente. Além de executar sub-rotinas, os **métodos** também podem mudar o estado de uma instância, como no caso dos **getters** e **setters**, e realizarem operações entre os objetos, com o uso de **operators**.

A sintaxe de um método é algo que já estamos habituados, visto que é a mesma de uma função convencional.

<h3 align="center">Métodos - sintaxe</h3>

~~~dart

class Classe{
    late int instancia;
    // Construtor
    Classe(this.instancia);

    // Metodo
    tipo_de_retorno nome_do _metodo (var parametro){
        // instruções

        return valor;
    }
}


main(){
    Classe objeto = Classe(instancia);

    //Chamando o metodo de um objeto
    var valor = objeto.nome_do_metodo(var paramentro);
}

~~~

<h3 align="center">Métodos- exemplo prático</h3>

~~~dart

class Pokemon {
  late String tipo;
  late String nome;
  
  Pokemon(this.tipo, this.nome);
  
  factory Pokemon.criarPokemon(String tipo, String nome){
    if(tipo == "Fogo") return Fogo("Fogo",nome);
    if(tipo == "Agua") return Agua("Agua",nome);
    if(tipo == "Grama") return Grama("Grama", nome);
    
    return Pokemon(tipo, nome);
  }
  
  String habilidade(){
    return "Sem habilidade";
  }
}

class Fogo extends Pokemon{
  Fogo(String tipo, String nome) : super(tipo, nome);
  
  String habilidade(){
    return "Blaze";
  }
}

class Agua extends Pokemon{
  Agua(String tipo, String nome) : super(tipo, nome);
  
  String habilidade(){
    return "Torrent";
  }
}

class Grama extends Pokemon{
  Grama(String tipo, String nome) : super(tipo, nome);
  
  String habilidade(){
    return "Overgrow";
  }
}

main() { 
  var pokemon_1 = Pokemon.criarPokemon("Grama","Bulbasaur");
  var pokemon_4 = Pokemon.criarPokemon("Fogo","Charmander");
  var pokemon_7 = Pokemon.criarPokemon("Agua","Squirtle");
  
  
  print("Pokemon 001: ${pokemon_1.nome} | hab: ${pokemon_1.habilidade()}");
  print("Pokemon 004: ${pokemon_4.nome} | hab: ${pokemon_4.habilidade()}");
  print("Pokemon 007: ${pokemon_7.nome} | hab: ${pokemon_7.habilidade()}");
   
}  

~~~


<p align="center">
    <a href="https://dartpad.dev/?id=4f9576193f614d0197ad43098511160a">
        <img src="https://i.imgur.com/LcfpWbh.png" height="24">
    </a>
</p>

> Repare que neste exemplo o método **habilidade()**, presente nas classes _Grama_, _Agua_ e _Fogo_ está sobrescrevendo o método **habilidade()** da superclasse _Pokemon_. Esta é uma das propriedades dos métodos herdados, que podem ser modificados em suas subclasses para retornar valores diferentes. Esse e outras características serão abordadas mais a fundo nos tópicos seguintes sobre herança.

<p align="right">
    <a href="#sumario">
        <img src="https://raw.githubusercontent.com/JosManoel/Dart-Study/main/images/icons/voltar_ao_topo.png" height="32">
    </a>
</p>
 
<h2 id="gets_sets">Gets e sets</h2>

Os **getters** e **setters** são métodos especializados na leitura e gravação das propriedades de um objeto. Através desses métodos é possível recuperar os valores das instâncias de um objeto e modificá-los conforme a necessidade do projeto. 

Note que até o momento os exemplos acima retornaram os valores das instâncias de um objeto sem o uso de alguma palavra-chave **get** ou **set**. Isto aconteceu porque todos objetos criados em Dart possuem um **método getter** implícito para cada uma de suas variáveis. 

Para os casos onde apenas o método implicito não é suficiente, o Dart possui as palavras-chave **get** e **set** para definir os métodos para cada instância desejada. Sua sintaxe segue os modelos que vimos até momento, com a necessidade do modificador **set** na função **set** e de especificar um tipo de retorno para a função **get**, além do uso do **return**. Todas as sintaxes das funções convencionais são válidas para estes métodos, incluindo a [big arrow function](https://github.com/JosManoel/Dart-Study/blob/main/topics/2-1_Criando_funcoes.md#BigArrowF).

<h3 align="center">Métodos set e get - sintaxe</h3>

~~~dart

class Classe{
    late int instancia;
    // Construtor
    Classe(this.instancia);

    // Metodo get
    int get nome_metodo_get{
        return instancia;
    }

    //Metodo set
    void set nome_metodo_set(int inst){
        instancia = inst;
    }
}


main(){  
    Classe objeto = Classe(valor_1);

    //Setando um novo valor para a instancia
    objeto.nome_metodo_set = valor_2;
  
    //recuperando o valor da instancia com get
    var valor = objeto.nome_metodo_get;
}

~~~

<h3 align="center">Métodos set e get - sintaxe contraída</h3>

~~~dart

class Classe{
    late int instancia;
    // Construtor
    Classe(this.instancia);

    // Metodo get
    int get nome_metodo_get => instancia;

    //Metodo set
    void set nome_metodo_set(int inst) => instancia = inst;

}


main(){  
    Classe objeto = Classe(valor_1);

    //Setando um novo valor para a instancia
    objeto.nome_metodo_set = valor_2;
  
    //recuperando o valor da instancia com get
    var valor = objeto.nome_metodo_get;
}

~~~

<h3 align="center">Setters e Getters - exemplo prático</h3>

~~~dart

class Pokemon {
  late String tipo;
  late String nome;
  
  String hab = "Sem habilidade";
  
  Pokemon(this.tipo, this.nome);
  
  factory Pokemon.criarPokemon(String tipo, String nome){
    if(tipo == "Fogo") return Fogo("Fogo",nome);
    if(tipo == "Agua") return Agua("Agua",nome);
    if(tipo == "Grama") return Grama("Grama", nome);
    
    return Pokemon(tipo, nome);
  }
  
  void set setHabilidade(String valor) => hab = valor; 
  
  String habilidade(){
    return hab;
  }
}

class Fogo extends Pokemon{
  Fogo(String tipo, String nome) : super(tipo, nome);
  
  String habilidade(){
    return "Blaze";
  }
}

class Agua extends Pokemon{
  Agua(String tipo, String nome) : super(tipo, nome);
  
  String habilidade(){
    return "Torrent";
  }
}

class Grama extends Pokemon{
  Grama(String tipo, String nome) : super(tipo, nome);
  
  String habilidade(){
    return "Overgrow";
  }
}

main() { 
  var pokemon_1 = Pokemon.criarPokemon("Grama","Bulbasaur");
  var pokemon_4 = Pokemon.criarPokemon("Fogo","Charmander");
  var pokemon_7 = Pokemon.criarPokemon("Agua","Squirtle");
  
  print("Pokemon 001: ${pokemon_1.nome} | hab: ${pokemon_1.habilidade()}");
  print("Pokemon 004: ${pokemon_4.nome} | hab: ${pokemon_4.habilidade()}");
  print("Pokemon 007: ${pokemon_7.nome} | hab: ${pokemon_7.habilidade()}");
  
  //Criando um novo pokemon com tipo nao catalogado
  var pokemon_10 = Pokemon.criarPokemon("Inseto", "Caterpie");
  // Setando nova habilidade para o novo pokemon
  pokemon_10.setHabilidade = "Shield Dust";
  
  print("Pokemon 010: ${pokemon_10.nome} | hab: ${pokemon_10.habilidade()}");
   
}

~~~

> Observe que, apesar de ser um pokemon não catalogado, com tipo diferente dos esperados _Grama_, _Fogo_ ou _Agua, ainda utilizamos o mesmo construtor para criar um novo pokemon, sendo necessário apenas atribuir uma nova habilidade.

<p align="center">
    <a href="https://dartpad.dev/?id=52768bb8085dd8882e9da6ec4cbf21c7">
        <img src="https://i.imgur.com/COn190U.png" height="24">
    </a>
</p>

<p align="right">
    <a href="#sumario">
        <img src="https://raw.githubusercontent.com/JosManoel/Dart-Study/main/images/icons/voltar_ao_topo.png" height="32">
    </a>
</p>

<h2 id="operators">Operators</h2>

O Dart também oferece suporte ao procedimento de **sobrecarga de operadores**, que redefine a função de um operador da função, mais comumente utilizado para operadores matemáticos. Com os métodos **operators** podemos determinar novas funções para as operações entre objetos sem a necessidade de criar métodos nomeados para cada necessidade, tornando o código mais legível e amigável ao desenvolvedor.

A sintaxe de um método **operator** também segue os modelos vistos até o momento, utilizando a palavra-chave **operator** após o tipo do valor que será retornado, possuindo a necessidade de um **return**, como no método **get**. Além disso, o escopo do método conta ainda com o nome do operador que será definido, podendo ser qualquer um dos operadores suportados pelo dart, com exceção do **!=**, que tem sua ausência justificada na documentação pelo fato de ser apenas um syntactic sugar para a expressão !(e1 == e2).

> O termo syntactic sugar é utilizado para se referir às expressões que são apenas convenções simplificadas de alguma outra sintaxe.

> Para mais informações, retorne ao artigo sobre [operadores](https://github.com/JosManoel/Dart-Study/blob/main/topics/1-4_Operadores_e_operacoes.md#operadores_aritimeticos).

<h3 align="center">Operadores suportados</h3>

<p align="center">
    <table style="border-collapse:collapse;border-spacing:0" class="tg"><thead><tr><th style="background-color:#ffffff;border-color:#000000;border-style:solid;border-width:1px;color:#333333;font-family:Arial, sans-serif;font-size:14px;font-weight:bold;overflow:hidden;padding:6px 20px;text-align:center;vertical-align:top;word-break:normal">&lt;</th><th style="background-color:#ffffff;border-color:#000000;border-style:solid;border-width:1px;color:#333333;font-family:Arial, sans-serif;font-size:14px;font-weight:bold;overflow:hidden;padding:6px 20px;text-align:center;vertical-align:top;word-break:normal">+</th><th style="background-color:#ffffff;border-color:#000000;border-style:solid;border-width:1px;color:#333333;font-family:Arial, sans-serif;font-size:14px;font-weight:bold;overflow:hidden;padding:6px 20px;text-align:center;vertical-align:top;word-break:normal">|</th><th style="background-color:#ffffff;border-color:#000000;border-style:solid;border-width:1px;color:#333333;font-family:Arial, sans-serif;font-size:14px;font-weight:bold;overflow:hidden;padding:6px 20px;text-align:center;vertical-align:top;word-break:normal">&gt;&gt;&gt;</th></tr></thead><tbody><tr><td style="background-color:#ffffff;border-color:#000000;border-style:solid;border-width:1px;color:#333333;font-family:Arial, sans-serif;font-size:14px;font-weight:bold;overflow:hidden;padding:6px 20px;text-align:center;vertical-align:top;word-break:normal">&gt;</td><td style="background-color:#ffffff;border-color:#000000;border-style:solid;border-width:1px;color:#333333;font-family:Arial, sans-serif;font-size:14px;font-weight:bold;overflow:hidden;padding:6px 20px;text-align:center;vertical-align:top;word-break:normal">/</td><td style="background-color:#ffffff;border-color:#000000;border-style:solid;border-width:1px;color:#333333;font-family:Arial, sans-serif;font-size:14px;font-weight:bold;overflow:hidden;padding:6px 20px;text-align:center;vertical-align:top;word-break:normal">^</td><td style="background-color:#ffffff;border-color:#000000;border-style:solid;border-width:1px;color:#333333;font-family:Arial, sans-serif;font-size:14px;font-weight:bold;overflow:hidden;padding:6px 20px;text-align:center;vertical-align:top;word-break:normal">[]</td></tr><tr><td style="background-color:#ffffff;border-color:#000000;border-style:solid;border-width:1px;color:#333333;font-family:Arial, sans-serif;font-size:14px;font-weight:bold;overflow:hidden;padding:6px 20px;text-align:center;vertical-align:top;word-break:normal">&lt;=</td><td style="background-color:#ffffff;border-color:#000000;border-style:solid;border-width:1px;color:#333333;font-family:Arial, sans-serif;font-size:14px;font-weight:bold;overflow:hidden;padding:6px 20px;text-align:center;vertical-align:top;word-break:normal">~/</td><td style="background-color:#ffffff;border-color:#000000;border-style:solid;border-width:1px;color:#333333;font-family:Arial, sans-serif;font-size:14px;font-weight:bold;overflow:hidden;padding:6px 20px;text-align:center;vertical-align:top;word-break:normal">&amp;</td><td style="background-color:#ffffff;border-color:#000000;border-style:solid;border-width:1px;color:#333333;font-family:Arial, sans-serif;font-size:14px;font-weight:bold;overflow:hidden;padding:6px 20px;text-align:center;vertical-align:top;word-break:normal">[]=</td></tr><tr><td style="background-color:#ffffff;border-color:#000000;border-style:solid;border-width:1px;color:#333333;font-family:Arial, sans-serif;font-size:14px;font-weight:bold;overflow:hidden;padding:6px 20px;text-align:center;vertical-align:top;word-break:normal">&gt;=</td><td style="background-color:#ffffff;border-color:#000000;border-style:solid;border-width:1px;color:#333333;font-family:Arial, sans-serif;font-size:14px;font-weight:bold;overflow:hidden;padding:6px 20px;text-align:center;vertical-align:top;word-break:normal">*</td><td style="background-color:#ffffff;border-color:#000000;border-style:solid;border-width:1px;color:#333333;font-family:Arial, sans-serif;font-size:14px;font-weight:bold;overflow:hidden;padding:6px 20px;text-align:center;vertical-align:top;word-break:normal">&lt;&lt;</td><td style="background-color:#ffffff;border-color:#000000;border-style:solid;border-width:1px;color:#333333;font-family:Arial, sans-serif;font-size:14px;font-weight:bold;overflow:hidden;padding:6px 20px;text-align:center;vertical-align:top;word-break:normal">~</td></tr><tr><td style="background-color:#ffffff;border-color:#000000;border-style:solid;border-width:1px;color:#333333;font-family:Arial, sans-serif;font-size:14px;font-weight:bold;overflow:hidden;padding:6px 20px;text-align:center;vertical-align:top;word-break:normal">-</td><td style="background-color:#ffffff;border-color:#000000;border-style:solid;border-width:1px;color:#333333;font-family:Arial, sans-serif;font-size:14px;font-weight:bold;overflow:hidden;padding:6px 20px;text-align:center;vertical-align:top;word-break:normal">%</td><td style="background-color:#ffffff;border-color:#000000;border-style:solid;border-width:1px;color:#333333;font-family:Arial, sans-serif;font-size:14px;font-weight:bold;overflow:hidden;padding:6px 20px;text-align:center;vertical-align:top;word-break:normal">&gt;&gt;</td><td style="background-color:#ffffff;border-color:#000000;border-style:solid;border-width:1px;color:#333333;font-family:Arial, sans-serif;font-size:14px;font-weight:bold;overflow:hidden;padding:6px 20px;text-align:center;vertical-align:top;word-break:normal">==</td></tr></tbody></table>
</p>

<h3 align="center">Operators - sintaxe</h3>

~~~dart

class Classe{
    late int instancia;
    // Construtor
    Classe(this.instancia);

    //Metodo operator
    tipo operator operador(tipo variavel){
        // 
        return this.instancia + variavel
    }
}


main(){  
    Classe objeto_1 = Classe(valor_1);
    var valor;
  
    //realizando a operação reescrita
    var valor = (objeto_1 operador valor);
}

~~~

<h3 align="center">Operators - exemplo prático</h3>

~~~dart

class Pokemon {
  late String tipo;
  late String nome;
  
  String hab = "Sem habilidade";
  
  Pokemon(this.tipo, this.nome);
  
  factory Pokemon.criarPokemon(String tipo, String nome){
    if(tipo == "Fogo") return Fogo("Fogo",nome);
    if(tipo == "Agua") return Agua("Agua",nome);
    if(tipo == "Grama") return Grama("Grama", nome);
    
    return Pokemon(tipo, nome);
  }
  
  void set setHabilidade(String valor) => hab = valor; 
  
  String habilidade(){
    return hab;
  }
  
  bool operator &(Pokemon pok){
    if(tipo == pok.tipo){
      return true;
    }
    return false;
  }
}

class Fogo extends Pokemon{
  Fogo(String tipo, String nome) : super(tipo, nome);
  
  String habilidade(){
    return "Blaze";
  }
}

class Agua extends Pokemon{
  Agua(String tipo, String nome) : super(tipo, nome);
  
  String habilidade(){
    return "Torrent";
  }
}

class Grama extends Pokemon{
  Grama(String tipo, String nome) : super(tipo, nome);
  
  String habilidade(){
    return "Overgrow";
  }
}

main() { 
  var pokemon_1 = Pokemon.criarPokemon("Grama","Bulbasaur");
  var pokemon_4 = Pokemon.criarPokemon("Fogo","Charmander");
  var pokemon_152 = Pokemon.criarPokemon("Grama","Chikorita");
  
  //Verifica se pokemon_1 E pokemon_152 possuem o mesmo tipo
  print("${pokemon_1.nome} e ${pokemon_152.nome}: ${pokemon_1 & pokemon_152}");
  //Verifica se pokemon_1 E pokemon_4 possuem o mesmo tipo
  print("${pokemon_1.nome} e ${pokemon_4.nome}: ${pokemon_1 & pokemon_4}");
   
}

~~~

<p align="center">
    <a href="https://dartpad.dev/?id=dd4a73573f26dbeb8adc67eaec2cc170">
        <img src="https://i.imgur.com/T6PNiYH.png" height="24">
    </a>
</p>


<p align="right">
    <a href="#sumario">
        <img src="https://raw.githubusercontent.com/JosManoel/Dart-Study/main/images/icons/voltar_ao_topo.png" height="32">
    </a>
</p>


***

<h2 id="Extends">Herança e extends</h2>

A herança é um dos pilares da programação orientada a objetos. Sua principal finalidade é tornar o desenvolvimento mais simples e aproximar a programação da realidade, acompanhada de uma hierarquia de classes que ditam a ordem de herança entre os objetos, baseada nos conceitos de **superclasse** e **subclasse**, sendo elas respectivamente as classes acima e abaixo da classe atual. 

No Dart, assim como o Java, tudo pode ser um objeto, como foi mostrado nos exemplos acima. A sintaxe da herança a objetos é algo que já estamos bastante habituados, utilizando o modificador **extends** para indicar a classe atual qual será sua **superclasse**. Quando na **subclasse**, utilizamos a palavra-chave **super** para nos referir a algum elemento da classe acima.

<h3 align="center">Factory constructor - exemplo de sintaxe</h3>

~~~dart

class Classe_pai{
    int inst_pai;
    Classe_pai(this.inst_pai);
}

class Classe_filho extends Classe_pai{
    int inst_filho;
    Classe_filho1(int instancia): super(instancia);
}

main(){
    var objeto = Classe_filho(valor);
}

~~~

> Nesse exemplo estamos utilizando a palavra-chave **super** para nos referir ao construtor da Classe_pai e reutilizá-lo na Classe_filho.

O **extends** no dart segue o exemplo de outras linguagens, permitindo a **subclasse** herdar métodos e outras características, com exceção dos construtores, como vimos anteriormente.

Ao estender métodos para outras subclasses, podemos reescrever os métodos e valores da classe pai, alterando os valores e as funções conforme for necessário. Apesar de não ser obrigatório, o date possui a notação **"@override"** para sinalizar elementos reescritos.

<h3 align="center">Extends - exemplo prático</h3>

~~~dart

class Pokemon {
  late String tipo;
  late String nome;
  
  String hab = "Sem habilidade";
  
  Pokemon(this.tipo, this.nome);
  
  factory Pokemon.criarPokemon(String tipo, String nome){
    if(tipo == "Fogo") return Fogo("Fogo",nome);
    if(tipo == "Agua") return Agua("Agua",nome);
    if(tipo == "Grama") return Grama("Grama", nome);
    
    return Pokemon(tipo, nome);
  }
  
  void set setHabilidade(String valor) => hab = valor;  
  String get getHabilidade => hab;
  
  bool operator &(Pokemon pok){
    return (tipo == pok.tipo) ? true : false;
  }
  
  void atacar() => print("${nome} ataca com ${hab}");
}

class Fogo extends Pokemon{
  Fogo(String tipo, String nome) : super(tipo, nome);
  
  @override
  String hab = "Blaze";
}

class Agua extends Pokemon{
  Agua(String tipo, String nome) : super(tipo, nome);
  
  @override
  String hab = "Torrent";
}

class Grama extends Pokemon{
  Grama(String tipo, String nome) : super(tipo, nome);
  
  @override
  String hab = "Overgrow";
}

main() { 
  var pokemon_1 = Pokemon.criarPokemon("Grama","Bulbasaur");
  var pokemon_4 = Pokemon.criarPokemon("Fogo","Charmander");
  var pokemon_152 = Pokemon.criarPokemon("Grama","Chikorita");
  
  pokemon_1.atacar();
  pokemon_4.atacar();
}

~~~

<p align="center">
    <a href="https://dartpad.dev/?id=acdb9ff4ad8e403e5309fb11fe1c0ea9">
        <img src="https://i.imgur.com/ZCVr02r.png" height="24">
    </a>
</p>


<p align="right">
    <a href="#sumario">
        <img src="https://raw.githubusercontent.com/JosManoel/Dart-Study/main/images/icons/voltar_ao_topo.png" height="32">
    </a>
</p>

> Nesse exemplo as classes _Grama_, _Agua_ e _Fogo_ herdam todos os métodos da classe **Pokemon**, com exceção dos contrutores, recuperados através da palavra-chave **super**.

<h2 id="Abstradas">Classes abstratas</h2>

Apesar da herança funcionar bem no Dart, temos uma pequena limitação quanto a herdar mais de uma classe, visto que a herança múltipla tende a gerar problemas de conflitos com métodos de mesma nomenclatura. Para solucionar esse problema o Dart possui as **classes abstratas**, úteis para definir **interfaces implícitas**. As **interfaces**, na programação orientada a objetos, são constituídas por conjuntos de elementos que definem as formas de interação com os objetos, possuindo **getters**, **setters** e diversos conjuntos de métodos.

A **abstract class** não pode ser instanciada. Para que elas possam ser instanciadas em outras classes, é utilizado o **factory constructor** para retornar todos os métodos necessários. Além disso, a sintaxe da classe abstrata utiliza o modificador **abstract** e permite tanto o emprego do **extends** como também do **implements**, que permite implementar múltiplas classes.

<h3 align="center">Abstract class - exemplo de sintaxe</h3>

~~~dart

abstract class Classe_abstrata{
    factory Classe_abstrata() => CLasse_pai();

    // Metodos
}

class Classe_pai implements Classe_abstrata{
    late int inst_pai;
    Classe_pai(this.inst_pai);
}

class Classe_filho extends Classe_pai{
    late int instancia;
  
    Classe_filho(int instancia): super(instancia);
}

main(){
    var objeto = Classe_filho(valor);
}

~~~

Os métodos definidos em uma **classe abstrata** podem ou não serem abstratos. Quando não são declarados como um **abstract method**, a sintaxe utilizada é a mesma de um método convencional e sua substituição reescrita na subclasse é dispensada, a menos que a **classe abstrata** seja implementada com a palavra-chave **implements**.

Já quando o método é definido como um **método abstrato**, sua sintaxe contém apenas o nome e o tipo da função, sem seu escopo, sendo necessário reescrevê-lo na classe em que será implementada. 

<h3 align="center">Abstract class - exemplo prático</h3>

~~~dart

abstract class Animal{
  late String nome;
  
  void comer() => print("${nome} está comendo");

  void dormir() => print("${nome} está dormindo");
  
  void atacar(); //Metodo abstrato
}

class Pokemon extends Animal{
  @override
  late String nome;
  
  late String tipo;
  
  String hab = "Sem habilidade";
  
  Pokemon(this.tipo, this.nome);
  
  factory Pokemon.criarPokemon(String tipo, String nome){
    if(tipo == "Fogo") return Fogo("Fogo",nome);
    if(tipo == "Agua") return Agua("Agua",nome);
    if(tipo == "Grama") return Grama("Grama", nome);
    
    return Pokemon(tipo, nome);
  }
  
  void set setHabilidade(String valor) => hab = valor;  
  String get getHabilidade => hab;
  
  bool operator &(Pokemon pok){
    return (tipo == pok.tipo) ? true : false;
  }
  
  @override
  void atacar() => print("${nome} ataca com ${hab}");
}

class Fogo extends Pokemon{
  Fogo(String tipo, String nome) : super(tipo, nome);
  
  @override
  String hab = "Blaze";
}

class Agua extends Pokemon{
  Agua(String tipo, String nome) : super(tipo, nome);
  
  @override
  String hab = "Torrent";
}

class Grama extends Pokemon{
  Grama(String tipo, String nome) : super(tipo, nome);
  
  @override
  String hab = "Overgrow";
}

main() { 
  var pokemon_1 = Pokemon.criarPokemon("Grama","Bulbasaur");
  var pokemon_4 = Pokemon.criarPokemon("Fogo","Charmander");
  var pokemon_152 = Pokemon.criarPokemon("Grama","Chikorita");
  
  pokemon_1.atacar();
  pokemon_4.atacar();
  
  pokemon_1.comer();
  pokemon_152.dormir();
}

~~~

<p align="center">
    <a href="https://dartpad.dev/?id=7868c90f1ef9a2623e8bb99f58fd2391">
        <img src="https://i.imgur.com/bexV8Jj.png" height="24">
    </a>
</p>

<p align="right">
    <a href="#sumario">
        <img src="https://raw.githubusercontent.com/JosManoel/Dart-Study/main/images/icons/voltar_ao_topo.png" height="32">
    </a>
</p>


<h2 id="interface_implicita">Interfaces implicitas</h2>

No Dart, além dos métodos implícitos, também podemos ter **interfaces implicitas**. As **interfaces implicitas** solucionam parte dos problemas da multipla herança, por permitirem a implementação de várias interfaces enquanto mantem o tipo da classe implementada sem herdar seus métodos. Por não herdar seus métodos, surge a necessidade de reescrever as funções desejadas na subclasse, como vimos anteriormente com os métodos abstratos. 

> As **interfaces implicitas** não possuem uma palavra reservada para a sua sintaxe, empregando o _"implements"_ para em sua implementação.

<h3 align="center">Implicit interfaces - exemplo de sintaxe</h3>

~~~dart

abstract class Classe_abstrata{
    // Metodo 
    void abstract_function() => print("metodo abstrato");
}

class Classe implements Classe_abstrata{
    // Metodo da classe abstrata reescrito
    @override
    void abstract_function() => print("metodo reescrito");
}

main(){
    var objeto = Classe();
}

~~~

<p align="right">
    <a href="#sumario">
        <img src="https://raw.githubusercontent.com/JosManoel/Dart-Study/main/images/icons/voltar_ao_topo.png" height="32">
    </a>
</p>


<h2 id="Mixins">Mixins</h2>

Apesar das **interfaces implícitas** solucionarem parte dos problemas da herança múltipla, ainda temos uma grande recorrência de código duplicado em métodos que serão implementados. Para estes casos o Dart recomenda o uso de **mixins**, que permitem adicionar recursos a uma classe sem a necessidade de utilizar os métodos de herança convencional.

Os **mixins** funcionam como uma forma flexível de disponibilizar métodos criados de forma isolada, sem a necessidade de estarem incluídos diretamente em uma classe. Dessa forma, podemos criar diversos métodos e adicioná-los posteriormente as classes conforme o necessário. A sintaxe de um **mixin** utiliza a palavra-chave **mixin** para determinar a sua implementação e **with** para ser incluindo em uma classe.

<h3 align="center">Mixins - exemplo de sintaxe</h3>

~~~dart

mixin novo_mixin{
    // Metodo 
    void mixin_function() => print("metodo mixin");
}

class Classe with novo_mixin{
    //Metodos
}

main(){
    var objeto = Classe();  

    objeto.mixin_function();
}

~~~

> Mixins não utilizam construtores em sua sintaxe.

O **with** também pode ser utilizado com **classes comuns** e **classes abstratas**, indicado quando se deseja que a classe possua tanto o comportamento de uma classe regular como também o de um mixin.

<h3 align="center">With - Classes abstratas</h3>

~~~dart

abstract class Classe_abstrata{
    // Metodo 
    void abstract_function() => print("metodo abstrato");
}

class Classe with Classe_abstrata{
  // Metodos
}

main(){
    var objeto = Classe();
    
    objeto.abstract_function();
}
~~~

<h3 align="center">Mixins - exemplo prático</h3>

~~~dart

import 'dart:math';

mixin pokebola{
  var random = Random();
  void capturar() => (random.nextBool()) ? print("Capturado!") : print("Fugiu!");
}

abstract class Animal{
  late String nome;
  
  void comer() => print("${nome} está comendo");
  void dormir() => print("${nome} está dormindo");
  
  void atacar(); //Metodo abstrato
}

class Pokemon extends Animal with pokebola{
  @override
  late String nome;
  
  late String tipo;
  
  String hab = "Sem habilidade";
  
  Pokemon(this.tipo, this.nome);
  
  factory Pokemon.criarPokemon(String tipo, String nome){
    if(tipo == "Fogo") return Fogo("Fogo",nome);
    if(tipo == "Agua") return Agua("Agua",nome);
    if(tipo == "Grama") return Grama("Grama", nome);
    
    return Pokemon(tipo, nome);
  }
  
  void set setHabilidade(String valor) => hab = valor;  
  String get getHabilidade => hab;
  
  bool operator &(Pokemon pok){
    return (tipo == pok.tipo) ? true : false;
  }
  
  @override
  void atacar() => print("${nome} ataca com ${hab}");
}

class Fogo extends Pokemon{
  Fogo(String tipo, String nome) : super(tipo, nome);
  
  @override
  String hab = "Blaze";
}

class Agua extends Pokemon{
  Agua(String tipo, String nome) : super(tipo, nome);
  
  @override
  String hab = "Torrent";
}

class Grama extends Pokemon{
  Grama(String tipo, String nome) : super(tipo, nome);
  
  @override
  String hab = "Overgrow";
}

main() { 
  var pokemon_1 = Pokemon.criarPokemon("Grama","Bulbasaur");
  var pokemon_4 = Pokemon.criarPokemon("Fogo","Charmander");
  var pokemon_152 = Pokemon.criarPokemon("Grama","Chikorita");
  
  pokemon_1.atacar();
  pokemon_4.atacar();
  
  pokemon_1.capturar();
}

~~~

<p align="center">
    <a href="https://dartpad.dev/?id=501b1b5c25198031e9966a325222565b">
        <img src="https://i.imgur.com/mWbKloK.png" height="24">
    </a>
</p>

<p align="right">
    <a href="#sumario">
        <img src="https://raw.githubusercontent.com/JosManoel/Dart-Study/main/images/icons/voltar_ao_topo.png" height="32">
    </a>
</p>


***

<h2 id="enumerated">Enumerated types</h2>

Além das classes convencionais e seus métodos de herança, o Dart também possui um terceiro tipo de classe denominado **Enum**, destinado à representação de valores fixos, semelhante às listas. A implementação e utilização de um **Enum** simples utiliza apenas a palavra-chave **"enum"**, excluindo a necessidade de getters, setters ou outros elementos. Além disso, um **Enum** convencional não pode ser implementado, explicitamente instanciado ou estendido a outras subclasses.

<h3 align="center">Enum - exemplo de sintaxe</h3>

~~~dart

enum Enumerado{
  item_1,
  item_2,
  item_3
}

void main(){
  
  // Retorna uma lista com todos os valores
  print(Enumerado.values);
  
  // Retorna o elemento
  print(Enumerado.item_1);
  
  // Retorna apenas o valor do elemento
  print(Enumerado.item_1.name);
}

~~~

<p align="right">
    <a href="#sumario">
        <img src="https://raw.githubusercontent.com/JosManoel/Dart-Study/main/images/icons/voltar_ao_topo.png" height="32">
    </a>
</p>

<h2 id="enhanced">Enhanced Enums</h2>

Após o lançamento da versão 2.17 o Dart também passou a suportar os **Enhanced Enums**, classes enums aprimoradas que suportam a declaração de métodos e construtores próprios. Apesar de incluir novas funcionalidades, a utilização de um **Enhanced Enum** ainda possui algumas limitações, sendo elas:

* Todas as variáveis de instância devem possuir o modificador **"final"**;
* Todos os construtores devem ser do tipo **"const"**;
* O factory constructor, se utilizado, deve retornar apenas uma das instâncias enum;
* Todas as instâncias do **Enum** devem ser declaradas no início, sendo obrigatório a declaração de no mínimo uma.

Além disso, para evitar conflitos, fica impedido o uso das palavras _"index"_, _"hashCode"_, _"values"_ e o operador _"=="_ nas declarações de novos métodos.

Na prática, ao utilizar um enum aprimorado, podemos implementar outros métodos para o tratamento de enums diretamente na classe, tornando nossa aplicação mais robusta. No exemplo de utilização disponibilizado pela documentação, podemos observar como a sintaxe de um **Enhanced Enum** é implementada, empregando a mesma palavra-chave de um enum convencional.

<h3 align="center">Utilizando um Enhanced Enum</h3>

~~~dart

enum Vehicle implements Comparable<Vehicle> {
  car(tires: 4, passengers: 5, carbonPerKilometer: 400),
  bus(tires: 6, passengers: 50, carbonPerKilometer: 800),
  bicycle(tires: 2, passengers: 1, carbonPerKilometer: 0);

  const Vehicle({
    required this.tires,
    required this.passengers,
    required this.carbonPerKilometer,
  });

  final int tires;
  final int passengers;
  final int carbonPerKilometer;

  int get carbonFootprint => (carbonPerKilometer / passengers).round();

  @override
  int compareTo(Vehicle other) => carbonFootprint - other.carbonFootprint;
}

void main(){
  // Retorna uma lista com todos os valores
  print(Vehicle.values);
  
  // Retorna o valor "passengers" do item "car"
  print(Vehicle.car.passengers);
  
  // Utilizando o get "carbonFootprint"
  print(Vehicle.car.carbonFootprint);
  
  // Utilizando o metodo "compateTo" com o outro elemento "bus"
  print(Vehicle.car.compareTo(Vehicle.bus));
}

// Exemplo retirado da documentação
// link: https://dart.dev/guides/language/language-tour#enumerated-types

~~~

<p align="center">
    <a href="https://dartpad.dev/?id=76566138d1ce961f21ccd2869dda6433">
        <img src="https://i.imgur.com/kYwizMw.png" height="24">
    </a>
</p>

<p align="right">
    <a href="#sumario">
        <img src="https://raw.githubusercontent.com/JosManoel/Dart-Study/main/images/icons/voltar_ao_topo.png" height="32">
    </a>
</p>

***
<h2 id="leitura_e_link"> 📚 Leitura e links recomendados</h2>

* [🎯 Programação orientada a objetos e programação estruturada](https://www.alura.com.br/artigos/poo-programacao-orientada-a-objetos)
* [📝 Dart - Documentação](https://dart.dev/guides)
* [🎯 Introdução à programação com Dart](https://dev.to/madebyluque/introducao-a-programacao-com-dart-aji)
* [🎯 Language Tour - Classes](https://dart.dev/guides/language/language-tour#classes)
* [🎯 Creating Objects and Classes in Dart and Flutter](https://dart.academy/creating-objects-and-classes-in-dart-and-flutter/)
* [🎯 Orientação à Objetos em Dart](https://medium.com/flutterbrasil/3-1-orienta%C3%A7%C3%A3o-%C3%A0-objetos-em-dart-classes-atributos-e-objetos-dfaa137828b4)
* [🎯 Exploring the 3 Types of Constructors in Dart](https://betterprogramming.pub/exploring-the-3-types-of-constructors-in-dart-e2e2d4d6f710)
* [🎯 O que são mixins e qual sua importância no Dart](https://www.treinaweb.com.br/blog/o-que-sao-mixins-e-qual-sua-importancia-no-dart)
* [🎯 Factory Constructor in Dart — Part 1](https://medium.com/nerd-for-tech/factory-constructor-in-dart-part-1-1bbdf0d0f7f0)
* [🎯 Factory Constructor in Dart — Part 2](https://medium.com/nerd-for-tech/factory-constructor-in-dart-part-2-7db2a5981ac3)
* [🎯 Dart getters and setters](https://dev.to/newtonmunene_yg/dart-getters-and-setters-1c8f)
* [🎯 Sobrecarga de Operadores com Dart](https://medium.com/flutter-comunidade-br/sobrecarga-de-operadores-com-dart-84d94842ce89)
* [🎯 Orientação à Objetos em Dart: Herança](https://medium.com/flutterbrasil/3-4-orienta%C3%A7%C3%A3o-%C3%A0-objetos-em-dart-heran%C3%A7a-2b149b98285)
* [🎯 Orientação à Objetos em Dart: Classes Abstratas](https://medium.com/flutterbrasil/3-6-orienta%C3%A7%C3%A3o-%C3%A0-objetos-em-dart-classes-abstratas-7f4a6fcdab5e)
* [🎯 Abstract Classes and Abstract Methods in Dart](https://medium.com/jay-tillu/abstract-class-and-abstract-methods-in-dart-4630f1e39f64)
* [🎯 Dart: extends vs implements vs with](https://medium.com/@manoelsrs/dart-extends-vs-implements-vs-with-96abd515f04e)
* [🎯 Dart: What are mixins?](https://medium.com/flutter-community/dart-what-are-mixins-3a72344011f3)

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
