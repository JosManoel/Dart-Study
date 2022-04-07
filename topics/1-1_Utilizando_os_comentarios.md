<img src="https://i.imgur.com/HNJ5tWE.png"> 

<p>

**Autor:**
  <a href="https://github.com/JosManoel">Manoel Freitas</a>
</p>

Atualmente, grande parte das linguagens de programação apresentam o conceito de comentários, que servem majoritariamente para indicar ao compilador ou interpretador que um determinado bloco de texto não deverá ser incluído na compilação ou interpretação do código final. Os comentários são comumente utilizados para auxiliar na interpretação do código pelo programador, seja identificando um determinado bloco de código, especificando algum processo ou na documentação de alguns métodos.

Esse método ainda pode ser utilizado para criar pequenas anotações, muito presentes durante o desenvolvimento de aplicações em equipe, ou para ocultar determinados trechos de código para o compilador. Os comentários podem desempenhar diversas funções, dependendo apenas da criatividade do programador, sempre prezando por uma boa organização e formatação do código. 

***
<h2 id="sumario">🧮 Sumário</h2>
 
  * <a href="#comentarios_dart">🗨️ Comentários em Dart</a> 
    * <a href="comentario_linha_unica">Comentários de linha única</a>
    * <a href="comentario_multipla_linha">Comentários de múltiplas linhas</a>
  * <a href="#comentarios_documentação">💬 Comentários de documentação</a> 
    * <a href="comentario_linha_unica_documentacao">Comentários de documentação: Linha única</a>
    * <a href="comentario_multipla_linha_documentacao">Comentários de documentação: Múltiplas linhas</a>
  * <a href="#leitura_e_link">📚 Leitura e links recomendado</a>
  * <a href="#licenca">🧾Licença</a>

***

<h2 id="comentarios_dart">🗨️ Comentários em Dart</h2>

Os comentários na linguagem dart possuem a mesma função que os utilizados em outras linguagens: documentar o código. Seu uso deve ser alinhado á uma boa nomenclatura de variáveis e métodos para promover uma leitura e interpretação clara do código. Atualmente, para comentários simples, temos dois meios de comentários, sendo eles o **_comentário de linha única_** e o **_comentário de mútiplas linhas_** ou **_comentário de bloco_**.


<h2 id="comentario_linha_unica">Comentários de linha única</h2>

Os comentários de linha única são majoritariamente utilizados para pequenos avisos ou indicações. Sua utilização é bastante simples, onde basta utilizar duas barras para indicar ao computador que este trecho de código é um comentário.

<h3 align="center">Comentários de linha única</h3>

~~~dart

// Vamos conquistar as esferas do dragão!
~~~

<p align="center">
    <a href="https://dartpad.dev/?id=5b59f356ac0fdb7965320d88e77f8d3d">
        <img src="https://i.imgur.com/PZN1KEk.png" height="24">
    </a>
</p>

<h2 id="comentario_multipla_linha">Comentários de múltiplas linhas</h2>

Já os comentários de múltiplas linhas ou comentários de bloco podem conter uma quantidade bem maior de texto, suportando quantas linhas o autor julgar necessário. Sua utilização é um pouco diferente do método de linha única, em que é necessário incluir um **/*** para indicar o início do comentário de bloco e um ***/** ao final do texto, para o seu termino ao compilador. 

<h3 align="center">Comentários de múltiplas linhas</h3>

~~~dart
/*
Levar pra luta a garra do vencedor
Correr e pegar as esferas do dragão!
São tantas maravilhas pra descobrir
A fantástica aventura começou
Neste mundo de emoção que você chegou!
*/
~~~

<p align="center">
    <a href="https://dartpad.dev/?id=de10956b3ddbf1f3718b31f03aae0f54">
        <img src="https://i.imgur.com/mxmUWy2.png" height="24">
    </a>
</p>

<p align="right">
    <a href="#sumario" style="font-size:1rem;font-weight: bold;">
        <img src="https://raw.githubusercontent.com/JosManoel/Dart-Study/main/images/icons/voltar_ao_topo.png" height="32">
    </a>
</p>

***

<h2 id="comentarios_documentação">💬 Comentários de documentação</h2>

O Dart possui ainda uma segunda forma de incluir comentários, mais utilizada durante a documentação de métodos e bibliotecas. Sua principal função é trazer informações que o programador considere necessário ao entendimento da função utilizada, aparecendo junto a um popup quando o mouse é posicionado sobre algum método. Assim como no comentário comum, os comentários de documentação também possuem dois meios de utilização: os **_comentários de linha única_** e os **_comentários de múltiplas linhas_**.


<h2 id="comentario_linha_unica_documentacao">Comentários de documentação: Linha única</h1>
Os comentários de documentação com uma única linha podem ser indicados utilizando três barras, sendo este o resultado:

<h3 align="center">Comentários de documentação com linha única</h3>

~~~dart
/// Musica: Vamos Conquistar As Esferas do Dragão!
~~~

<p align="center">
    <a href="https://dartpad.dev/?id=cc5f60918e36da2972700f4ca1d041f7">
        <img src="https://i.imgur.com/PZN1KEk.png" height="24">
    </a>
</p>

> Sua visualização só é suportadas em ferramentas de edição de código mais completas, como o VS Studio.

<h2 id="comentario_multipla_linha_documentacao">Comentários de documentação: Múltiplas linhas</h2>

Os comentários de documentação com múltiplas linhas funcionam de maneira bastante semelhante aos comentários de múltiplas linhas comuns, onde sua principal diferença está no uso de um segundo asterisco no primeiro indicador de abertura de comentário, ficando da seguinte forma:

<h3 align="center">Comentários de documentação com mútiplas linhas</h3>

~~~dart
/**
Anime: Dragon Ball (Clássico).
Autor: Akira Toriyama.
*/
~~~

<p align="center">
    <a href="https://dartpad.dev/?id=9c4db6afca3b0a69fd385bca0236ff1c">
        <img src="https://i.imgur.com/mxmUWy2.png" height="24">
    </a>
</p>

> Sua visualização só é suportadas em ferramentas de edição de código mais completas, como o VS Studio.

<p align="right">
    <a href="#sumario" style="font-size:1rem;font-weight: bold;">
        <img src="https://raw.githubusercontent.com/JosManoel/Dart-Study/main/images/icons/voltar_ao_topo.png" height="32">
    </a>
</p>

***

<h2 id="leitura_e_link">📚 Leitura e links recomendado</h2>

* [🎯 Introdução à programação com Dart](https://dev.to/cephalopodluke/introducao-a-programacao-com-dart-aji)
* [🎯 APRENDE DART: COMENTARIOS EN DART](https://dartgoogle.wordpress.com/2014/06/09/google-dart-comentarios-dart/)
* [🎯 Comentários de Documentação no Dart](https://medium.com/@leonardopaim/coment%C3%A1rios-de-documenta%C3%A7%C3%A3o-no-dart-d3deeeb1bc72#:~:text=O%20Dart%20possui%20uma%20forma,com%20muitas%20dicas%20de%20utiliza%C3%A7%C3%A3o.)

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
