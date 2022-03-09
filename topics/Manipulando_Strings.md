<img src="https://i.imgur.com/zkhiREQ.png"> 

<p>

**Autor:**
  <a href="https://github.com/JosManoel">Manoel Freitas</a>
</p>

As Strings são utilizadas principalmente para apresentar texto, funcionando basicamente como uma **lista de caracteres**. O Dart representa uma String como uma sequência de unidades de código **UTF-16**, onde cada caractere pode ser representado por uma ou mais unidades, como é comumente utilizado em **emojis**, que necessitam de pelo menos duas unidades de código.  

***
<h2 id="sumario">🧮 Sumário</h2>

 * <a href="#formato_UTF16">Formato UTF-16</a> 
 * <a href="#linha-unica_multilinha">Strings de linha única e multilinhas</a>
 * <a href="#operacoes">Modificando e realizando operações</a>
 * <a href="#interpolando_variaveis">Interpolando variáveis</a>
 * <a href="#contando_caracteres">Contando caracteres</a>
 * <a href="#principais_metodos">Principais métodos utilizados para String</a>
     * <a href="#ToLowerCase()">ToLowerCase()</a>
     * <a href="#ToUpperCase()">ToUpperCase()</a>
     * <a href="#Contains()">Contains()</a>
     * <a href="#StartsWith()">StartsWith()</a>
     * <a href="#EndsWith()">EndsWith()</a>
     * <a href="#ReplaceAll()">ReplaceAll()</a>
     * <a href="#IndexOf()">IndexOf()</a>
     * <a href="#LastIndexOf()">LastIndexOf()</a>
     * <a href="#Trim()">Trim()</a>
     * <a href="#PadLeft()">PadLeft()</a>
     * <a href="#PadRight()">PadRight()</a>
     * <a href="#Split()">Split()</a>
 * <a href= "#problema_do_String">Problemas ao Utilizar a String: Utilização de Emojis</a>
 * <a href="#leitura_e_link">📚 Leitura e links recomendado</a>
 * <a href="#licenca">🧾Licença</a>

***

<h2 id="formato_UTF16">Formato UTF-16</h2>

No formato UTF-16 os caracteres são codificados em duas ou mais palavras ( unidades de códigos,também chamadas de **code units** ). Um fator importante sobre o formato UTF-16 é que os códigos em **UNICODE**, de **U+0000 a U+FFFF**, são representados pelo seu próprio valor, ocorrendo apenas a substituição do **U+** pelo **0x**.

| UTF-16 | UNICODE | Saída |
|--------|---------|-------|
| 0x007A | U+007A  |   z   |

Durante a programação, utilizando a linguagem Dart, o conhecimento completo do formato UTF-16 não se faz necessário. Entretanto, é preciso ter em mente que esse formato possui algumas peculiaridades em relação à representação de emojis que podem resultar em possíveis erros. O tratamento desses casos será abordado em um futuro tópico.

<p align="right">
    <a href="#sumario" style="font-size:1rem;font-weight: bold;">Voltar ao topo ↑ </a>
</p>

***

<h2 id="linha-unica_multilinha">Strings de linha única e multilinhas</h2>

O Dart possui várias maneiras para a declaração de uma String, em que podem ser declaradas usando aspas pares simples ou duplas. Em casos de Strings com múltiplas linhas, a declaração deve ocorrer com o uso de aspas triplas.

<h3 align="center">Declaração das Strings</h3>

~~~dart
void main(){
  // Strings de linhas unicas

  var titulo = 'Evangelion: 3.0+1.0';
  var subtitulo = "Thrice Upon a Time";

  // Strings de multiplas linhas

  var sinopse = '''
  Evangelion: 3.0+1.0 Thrice Upon a Time 
  é um filme japonês de anime, 
  dirigido por Hideaki Anno.
  ''';

  var nota = """
  Disponível apenas no Amazon Prime
  ou no torrent mais próximo de você;
  """;
}    
~~~

<p align="center">
    <a href="https://dartpad.dev/?id=2be4e27378bc7ce22ce6393ce5de86b3">
        <img src="https://i.imgur.com/nGorhGM.png" height="24">
    </a>
</p>
 
 <p align="right">
    <a href="#sumario" style="font-size:1rem;font-weight: bold;">Voltar ao topo ↑ </a>
</p>

***

<h2 id="operacoes">Modificando e realizando operações</h2>

Em suma, as strings são imutáveis. No entanto, é possível realizar operações com uma string, resultando na criação de uma nova. Como exemplo disso temos a concatenação de strings, que resulta numa nova string que contém a informação de todas as outras.

<h3 align="center">Concatenação de Strings</h3>

~~~dart
void main(){
  var conc = "Kobayashi-san " + "Chi no " + "Maid Dragon";

  //Também é possível concatenar strings sem utilizar o operador '+'

  var conc = "Kobayashi-san " "Chi no " "Maid Dragon";
}    
~~~

<p align="center">
    <a href="https://dartpad.dev/?id=7f4578cee462e0d132447adf12330037">
        <img src="https://i.imgur.com/aAmgwbD.png" height="24">
    </a>
</p>

<p align="right">
    <a href="#sumario" style="font-size:1rem;font-weight: bold;">Voltar ao topo ↑ </a>
</p>

***
 
<h2 id="interpolando_variaveis">Interpolando variáveis</h2>

O processo de interpolação de variáveis acontece de maneira semelhante ao JavaScript, em que a variável é incluída entre chaves.

~~~dart
void main(){
  var episodios = 13;
  print ("Numero de episodios da 1 temporada: ${episodios}");
}    
~~~

<p align="center">
    <a href="https://dartpad.dev/?id=af353b1831d090ddc813a29ce472d39c">
        <img src="https://i.imgur.com/VKAcDlK.png" height="24">
    </a>
</p>
 
 <p align="right">
    <a href="#sumario" style="font-size:1rem;font-weight: bold;">Voltar ao topo ↑ </a>
</p>

***
 
<h2 id="contando_caracteres">Contando caracteres</h2>

No Dart os caracteres são contados a partir do **Code Units** e, para isso, são utilizadas diferentes funções, de acordo com cada necessidade. Em um primeiro cenário, podemos utilizar o **length** para descobrir quantos caracteres existem dentro de uma string, da mesma forma que ocorre com as **listas**. Isso acontece porque uma string nada mais é que uma lista de caracteres, que podem ser acessados individualmente através do índice.

<h3 align="center">Utilização do lenght</h3>

~~~dart
void main(){
  var frase = "Em todos esses anos nessa industria vital, essa é a 1 vez que isso me acontece";

  print(frase.length);

  // imprimindo um caractere pelo indice
  print(frase[1]);

  //Saida: m 
}    
~~~

<p align="center">
    <a href="https://dartpad.dev/?id=c96b83f4c6b34d74e9daac2c4e4f060e">
        <img src="https://i.imgur.com/OMywOLE.png" height="24">
    </a>
</p>
 
O Dart também permite recuperar o Code Unit de cada caractere, utilizando o **codeUnitAt**, que retorna o número de um caractere específico, ou o **codeUnits**, que retorna uma lista com todos os códigos.

<h3 align="center">Utilização o Code Units</h3>

~~~dart
void main(){
  // CodeUnits
  var nome = "Jaden";
  print(nome.codeUnits);
  // Saida: [74, 97, 100, 101, 110]

  // CodeUnitsAt
  print(nome.codeUnitAt(1));
  // Saida: 97
}
~~~

<p align="center">
    <a href="https://dartpad.dev/?id=44eac3084853846ce071d6909f8c3075">
        <img src="https://i.imgur.com/Bggo8Zv.png" height="24">
    </a>
</p>
 
<p align="right">
    <a href="#sumario" style="font-size:1rem;font-weight: bold;">Voltar ao topo ↑ </a>
</p>

***

<h2 id="principais_metodos">Principais métodos utilizados para String</h2>

<h3 id="ToLowerCase()">ToLowerCase()</h3>

O método **toLowerCase()** é utilizado para converter a String passada para o formato **minúsculo**.

<h3 align="center">Utilização do método toLowerCase()</h3>

~~~dart
void main(){
  var name = "RANMA SAOTOME";
  print(name.toLowerCase());

  //Saida: ranma saotome
}    
~~~

<p align="center">
    <a href="https://dartpad.dev/?id=cdfff6216e1e76f73d547b4ed5150a62">
        <img src="https://i.imgur.com/BGauhI9.png" height="24">
    </a>
</p>
 
 <p align="right">
    <a href="#sumario" style="font-size:1rem;font-weight: bold;">Voltar ao topo ↑ </a>
</p>

 
<h3 id="ToUpperCase()">ToUpperCase()</h3>

O método **toUpperCase()**, assim como o método **toLowerCase()**, é utilizado para alterar a formatação da String, convertendo os caracteres para **maíusculo**.

<h3 align="center">Utilização do método toUpperCase()</h3>

~~~dart
void main(){
  var name = "genma saotome";
  print(name.toUpperCase()); 

  //Saida: GENMA SAOTOME
}    
~~~

<p align="center">
    <a href="https://dartpad.dev/?id=3e710b128d7ee5d464236d0365f7952d">
        <img src="https://i.imgur.com/ofI3qzf.png" height="24">
    </a>
</p>
 
<p align="right">
    <a href="#sumario" style="font-size:1rem;font-weight: bold;">Voltar ao topo ↑ </a>
</p>
 
<h3 id="Contains()">Contains()</h3>

O método **contains()** é utilizado para verificar a existência de alguma correspondência dentro da String, retornando um valor booleano.

<h3 align="center">Utilização do método contains()</h3>

~~~dart
void main(){
  var str = "Mussum Ipsum, cacilds vidis litro abertis";
  print(str.contains("M"));

  //Saida: true


  // O Método contains é case-sensitive. Atente-se a String utilizada.

  print(str.contains("D"));

  //Saida: false
  
}    
~~~

<p align="center">
    <a href="https://dartpad.dev/?id=f1eec23c3ddb0be5991e16ed8b518985">
        <img src="https://i.imgur.com/ASGgVPG.png" height="24">
    </a>
</p>

<p align="right">
    <a href="#sumario" style="font-size:1rem;font-weight: bold;">Voltar ao topo ↑ </a>
</p>

<h3 id="StartsWith()">StartsWith()</h3>

O **startsWith()** permite verificar se a string inicia com os caracteres especificados, retornando um valor booleano. Caso seja informado um valor de índice, o método passa a verificar a substring.

<h3 align="center">Utilização do método startsWith()</h3>

~~~dart
void main(){
  var ranma = "Yopapa, foi você que chegou e brincou com meu coração";
  print(ranma.startsWith("Yopapa"));

  //Saida: true
  
  
  // Utilização do método startsWith() com índice

  var ranma = "Yopapa, foi você que chegou e brincou com meu coração";
  print(ranma.startsWith("Yopapa"), 1);

  //Saida: false
}    
~~~

<p align="center">
    <a href="https://dartpad.dev/?id=78755e7b6b5aef10beb3606c545c186d">
        <img src="https://i.imgur.com/ie1PGxj.png" height="24">
    </a>
</p>
 
<p align="right">
    <a href="#sumario" style="font-size:1rem;font-weight: bold;">Voltar ao topo ↑ </a>
</p>

<h3 id="EndsWith()">EndsWith()</h3>

O **endsWith** funciona de uma maneira semelhante ao **startsWith()**, porém de maneira invertida. O **endsWith()** permite verificar se a string termina com os caracteres definidos, retornando um valor booleano. Outra diferença é que este método não permite o uso de índices, verificando sempre o final de uma string.

<h3 align="center">Utilização do método endsWith()</h3>

~~~dart
void main(){
  var ranma = "Yopapa Yopapa, eu não sei como pode buscar apenas a razão";
  print(ranma.endsWith("razão"));

  //Saida: true
}    
~~~

<p align="center">
    <a href="https://dartpad.dev/?id=c57c8069c7e76f0576535534052bdee3">
        <img src="https://i.imgur.com/hKP8aOH.png" height="24">
    </a>
</p>
  
<p align="right">
    <a href="#sumario" style="font-size:1rem;font-weight: bold;">Voltar ao topo ↑ </a>
</p>

<h3 id="ReplaceAll()">ReplaceAll()</h3>

Este método pode ser bem útil para adicionar ou remover a acentuação de alguns caracteres. O método **replaceAll()** substitui todas as ocorrências de um caractere ou substring por outra previamente informada.

 
<h3 align="center">Utilização do método replaceAll()</h3>

~~~dart
void main(){
  // texto.replaceAll(String original, String substituta);

  var name = "fafnir";
  print(name.replaceAll( 'f', 'd'));

  //Saída: dadnir
}    
~~~

<p align="center">
    <a href="https://dartpad.dev/?id=47cdc1317d61990da4b0678bbee89fae">
        <img src="https://i.imgur.com/izTI10K.png" height="24">
    </a>
</p>
 
<p align="right">
    <a href="#sumario" style="font-size:1rem;font-weight: bold;">Voltar ao topo ↑ </a>
</p>

<h3 id="IndexOf()">IndexOf()</h3>

O método **indexOf()** retorna o índice da primeira correspondência do caractere informado na string passada. Caso não exista nenhuma correspondência, o valor retornado é **-1**.

<h3 align="center">Utilização do método indexOf()</h3>

~~~dart
void main(){
  var name = "Akane Tendo";
  print(name.indexOf("ane"));

  //Saida: 2


  print(name.indexOf("y")); 

  //Saida: -1
}    
~~~

<p align="center">
    <a href="https://dartpad.dev/?id=aee1c15f0064eeb9ed5940d91cd04126">
        <img src="https://i.imgur.com/zMvQRrO.png" height="24">
    </a>
</p>
 
<p align="right">
    <a href="#sumario" style="font-size:1rem;font-weight: bold;">Voltar ao topo ↑ </a>
</p>

<h3 id="LastIndexOf()">LastIndexOf()</h3>

O método **lastIndexOf()** retorna o índice da última correspondência da string fornecida, retornando **-1** caso não exista nenhuma correspondência.

<h3 align="center">Utilização do método LastIndexOf()</h3>

~~~dart
void main(){
  var name = "Megane";
  print(name.lastIndexOf("e"));

  // Saída: 5
}    
~~~

<p align="center">
    <a href="https://dartpad.dev/?id=b636d1b88f745d95364fd5c214ec7e41">
        <img src="https://i.imgur.com/He9tbRK.png" height="24">
    </a>
</p>
 
<p align="right">
    <a href="#sumario" style="font-size:1rem;font-weight: bold;">Voltar ao topo ↑ </a>
</p>

<h3 id="Trim()">Trim()</h3>

O método **trim()** é utilizado para retirar os espaços no começo e final de uma string. Caso não exista espaço antes ou depois da string, a string original é retornada.

<h3 align="center">Utilização do método Trim()</h3>

~~~dart
void main(){
  var name = "    A Turma do Barulho    ";
  print(name.trim()); 

  //Saida: "A turma do Barulho"
 }    
~~~

<p align="center">
    <a href="https://dartpad.dev/?id=19fb26c4a9869e60c29da47e151b1dea">
        <img src="https://i.imgur.com/V85BQlR.png" height="24">
    </a>
</p>
 

<h3 align="center">Removendo apenas os espaços da esquerda - TrimLeft()</h3>

~~~dart
void main(){
  var name = "    A Turma do Barulho    ";
  print(name.trimLeft());

//Saida: "A Turma do Barulho    "   
}    
~~~

<p align="center">
    <a href="https://dartpad.dev/?id=87c3dee82c2f7b9fb2d6985bb9fe0d77">
        <img src="https://i.imgur.com/zqIQ3rq.png" height="24">
    </a>
</p>
 
 
<h3 align="center">Removendo apenas os espaços da direita - TrimRight()</h3>

~~~dart
void main(){
  var name = "    A Turma do Barulho    ";
  print(name.trimRight());

  //Saida: "    A Turma do Barulho"
}    
~~~

<p align="center">
    <a href="https://dartpad.dev/?id=fee5743af87f38b5ba895239fe15a672">
        <img src="https://i.imgur.com/YeL8eEw.png" height="24">
    </a>
</p>

<p align="right">
    <a href="#sumario" style="font-size:1rem;font-weight: bold;">Voltar ao topo ↑ </a>
</p>
  
<h3 id="PadLeft()">PadLeft()</h3>

O método **padLeft()** é utilizado para preencher uma string a esquerda, caso a string seja menor que a largura indicada, com outra string ou caractere.

<h3 align="center">Utilização do método PadLeft()</h3>

~~~dart
void main(){
  // texto.padLeft(int largura, [String preenchimento = 'x']);

  var name = "Doquinha";
  print(name.padLeft(12, 'D'));

  //Saída: DDDDDoquinha
}    
~~~

<p align="center">
    <a href="https://dartpad.dev/?id=250b64a44f7343d3d0aa5490f44563e0">
        <img src="https://i.imgur.com/NeIla6b.png" height="24">
    </a>
</p>
 
<p align="right">
    <a href="#sumario" style="font-size:1rem;font-weight: bold;">Voltar ao topo ↑ </a>
</p>

<h3 id="PadRight()">PadRight()</h3>

O método **padRight()** funciona da mesma maneira que o método **padLeft()**, preenchendo uma string a direita com um caractere caso a string seja menor que a largura informada.

<h3 align="center">Utilização do método PadRight()</h3>

~~~dart
void main(){
  // texto.padRight(int largura, [String preenchimento = 'x']);

  var name = "Doquinha";
  print(name.padRight(12, 'D'));

  //Saída: DoquinhaDDDD
}    
~~~

<p align="center">
    <a href="https://dartpad.dev/?id=5796560ca9a2e611d0c20cc8591deed6">
        <img src="https://i.imgur.com/bQaxOLC.png" height="24">
    </a>
</p>

<p align="right">
    <a href="#sumario" style="font-size:1rem;font-weight: bold;">Voltar ao topo ↑ </a>
</p>

<h3 id="Split()">Split()</h3>

O método **split()** pode ser útil na divisão de uma string. Sua função é dividir a string em várias substrings conforme o caractere informado, retornando uma lista com as strings informadas.
 
<h3 align="center">Utilização do método split()</h3>

~~~dart
void main(){
  // texto.split(parametro);

  var citypop = "For tonight you better stay with me";

  // Divide a string a partir dos espaços
  print(citypop.split(' '));

  //Saída: [For, tonight, you, better, stay, with, me]
}    
~~~

<p align="center">
    <a href="https://dartpad.dev/?id=0eabfc1f44aba03e6c2ba74064c1bf53">
        <img src="https://i.imgur.com/KfrbYp0.png" height="24">
    </a>
</p>
  
<p align="right">
    <a href="#sumario" style="font-size:1rem;font-weight: bold;">Voltar ao topo ↑ </a>
</p>

***

<h3 id="problema_do_String">Problemas ao Utilizar a String: Utilização de Emojis</h3>

Como informado acima, o Dart, assim como outras linguagens criadas antes da popularização dos emojis, utiliza uma sequência de unidades de código UTF-16, trazendo algumas particularidades ao uso de caracteres especiais. 

Algumas da anomalias podem ocorrer na contagem de caracteres, como, por exemplo na string "Hello👋", que claramente possui 6 caracteres, no entando, ao utilizar o método length, obtemos 7 como resultado. Este fenômeno ocorre devido a uma particularidade do Dart, que utiliza duas ou mais code units para formar o emojis.

Caracteres | H | e | l | l | o | 👋
-----------|---|---|---|---|---|---
Code Unitis|72 |101|108|108|111|55357 + 56395

Esta situação pode ser facilmente resolvida utilizando o package characters, que identifica o uso de emojis em uma string e retorna o numero real de caracteres. 


<h3 align="center">Utilizaçção do package characters</h3>

~~~dart
void main(){
    var texto = "Eu vim em paz 🖖"
    print("Caracteres: ${texto.length}");
    // Saída: 16 caracteres.

    print("Caracteres: ${texto.characters.length}");
    // Saída: 15 Caracteres
}    
~~~

<p align="center">
    <a href="https://dartpad.dev/?id=d37931a5b8c2155d06db8d3f6150ee6f">
        <img src="https://i.imgur.com/LwodHaW.png" height="24">
    </a>
</p>
 
> O package characters não é suportado pelo DartPad.
> Para implementar o package characters em seu projeto Flutter acesse a sua [documentação](https://pub.dev/packages/characters/install).

> Existe outros possíveis erros não tão comuns na utilização de Emojis dentro de projetos com o Dart e o Flutter. Caso queira se inteirar, acesse o [artigo](https://medium.com/dartlang/dart-string-manipulation-done-right-5abd0668ba3e) escrito por Tao dong.


<p align="right">
    <a href="#sumario" style="font-size:1rem;font-weight: bold;">Voltar ao topo ↑ </a>
</p>

***

<h2 id="leitura_e_link">📚 Leitura e links recomendado</h2>

* [📝 Dart - Documentação](https://dart.dev/guides)
* [🎯 String class](https://api.dart.dev/stable/2.13.4/dart-core/String-class.html)
* [🎯 Top 10 String utility methods you should know (Dart)](https://codeburst.io/top-10-string-utility-methods-you-should-know-dart-b51ef65b3cc2)
* [🎯 Dart string manipulation done right](https://medium.com/dartlang/dart-string-manipulation-done-right-5abd0668ba3e)
* [📝 Transformação entre as representações UTF-8 e UTF-16](http://www4.inf.puc-rio.br/~inf1018//2013.1/trabs/t1/trab1.html)

<p align="right">
    <a href="#sumario" style="font-size:1rem;font-weight: bold;">Voltar ao topo ↑ </a>
</p>

***

<h2 id="licenca">🧾Licença</h2>

Este projeto está sob a licença [Apache 2.0](https://github.com/JosManoel/Dart-Study/blob/main/LICENSE).

<p align="right">
    <a href="#sumario" style="font-size:1rem;font-weight: bold;">Voltar ao topo ↑ </a>
</p>
