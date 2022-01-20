<h1 align="center">
  <div>
    <img src="https://raw.githubusercontent.com/JosManoel/Dart-Study/main/images/icons/dart.png" width = "26"> 
    Dart Study: Exercícios e Anotações
  </div>

  <p align="center">
    <img src="https://img.shields.io/github/commit-activity/m/JosManoel/Dart-Study">
    <img src="https://img.shields.io/github/last-commit/JosManoel/Dart-Study">
    <img src="https://img.shields.io/github/contributors/JosManoel/Dart-Study">
    <img src="https://img.shields.io/github/license/JosManoel/Dart-Study">
  </p>
</h1>

<p align="center">
  <a href="#sobre-este-projeto">👨🏻‍💻 Sobre este projeto </a> &nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;
  <a href="#o-que-e-dart">🎯 O que é Dart?</a> &nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;
  <a href="#comentarios">🏷️ Comentários no Dart </a> &nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;
  <a href="#topicos">🧮 Tópicos</a> &nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;
  <a href="#leitura">📚 Leitura e links recomendados</a> &nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;
  <a href="#licenca">🧾Licença</a>
</p>



***

<h2 id = "sobre-este-projeto">👨🏻‍💻 Sobre este projeto</h2>

Este repositório é foi criado com o intuito de armazenar e organizar as anotações e exercícios realizados durante o aprendizado com a linguagem Dart. O material a seguir é de uso livre, sinta-se a vontade para utilizar estas anotações em seu desenvolvimento.

> Para o desenvolvimento e aprendizado desta linguagem foi utilizado o VS Code, no entanto, também é possível utilizar ferramentas online, como o [DartPad](https://dartpad.dev/).

***

<h2 id="o-que-e-dart">🎯 O que é Dart?</h2>

Dart é uma linguagem orientada à objetos fortemente tipada¹ que pode ser utilizada tanto do "lado do cliente" (front-end) como do lado do servidor(back-end). Ela foi criada em 2011 pelo Google originalmente para substituir o javascript, porém não obteve exito devida a evolução do JS e dos scripts para páginas web. Atualmente o Dart é considerado uma linguagem multi-paradigma, onde é comumente utilizada no desenvolvimento de aplicações em Flutter.

>1️⃣ Isto significa que as variáveis em Dart devem possuir um tipo que não será mudado ao longo do código. Este assunto será aprofundado no tópico sobre variáveis.

O Dart tem uma sintaxe baseada na linguagem C, deste modo, sua escrita se faz semelhante a linguagens populares, como o Java. No entanto, o Dart busca minimizar alguns "ruídos", priorizando um código mais limpo. Como exemplo, podemos vê este simples Hello World, que necessita de poucas linhas de código, quando comparada as linguagens citadas anteriormente.

```
void main() {
  print("Hello World!");
}
```

O Dart possui uma função principal denominada main, onde através dela, todo o código é iniciado. O Dart é uma linguagem case-sensitive, por isso, deve-se tomar cuidado ao escrever o código, para evitar possíveis erros.

A exemplo disso, temos o seguinte código, que ira gerar um erro, pois o Dart não reconhece uma função chamada **P**rint.
```
void main(){
    Print("Hello");
}
```
Sua versão correta seria:

```
void main(){
    print("Hello");
}
```

> Toda linha de código escrita em Dart é terminada em ; (ponto e virgula).

***

<h2 id="comentarios">🏷️ Comentários no Dart</h2>

Os comentários possuem uma importante função no código. Através dele é possível documentar trechos do código para auxiliar a compreensão do código. Aliás, dentre os 3 tipos de comentários suportados pelo Dart, existe um específico para documentação.
### Comentando o código:

* Comentários de uma única linha:
```
// Vamos conquistar as esferas do dragão!
```

* Comentários de multíplas linhas:
```
/*
Levar pra luta a garra do vencedor
Correr e pegar as esferas do dragão!
São tantas maravilhas pra descobrir
A fantástica aventura começou
Neste mundo de emoção que você chegou!
*/
```

* Comentário de documentação:

> Os comentários de documentação podem ser de unica linha:

```
/// Musica: Vamos Conquistar As Esferas do Dragão!
```

> Ou de multiplas linhas:
```
/**
Anime: Dragon Ball (Clássico).
Autor: Akira Toriyama.
**/
```

> ⚠️ Atenção: Boa parte das variáveis utilizadas neste repositório possuem um tom descontraído, trazendo referencias a obras da cultura pop. O uso de variáveis como estas em outros projetos não é recomendado. ⚠️
>
***

<h2 id="topicos">🧮 Tópicos</h2>

* [Declarando variáveis](https://github.com/JosManoel/Dart-Study/blob/main/topics/Variaveis.md) ✔️ 
* [Operadores e operações](https://github.com/JosManoel/Dart-Study/blob/main/topics/Operadores_e_operacoes.md) ✔️
* [Controle de fluxo - Estruturas condicionais](https://github.com/JosManoel/Dart-Study/blob/main/topics/Controle_de_fluxo.md) ✔️
* [Estruturas de repetição](https://github.com/JosManoel/Dart-Study/blob/main/topics/Estruturas_de_repeticao.md) ✔️
* [Manipulando Strings](https://github.com/JosManoel/Dart-Study/blob/main/topics/Manipulando_Strings.md) 🛠

***

<h2 id="leitura">📚 Leitura e links recomendados</h2>

* [📝 Dart - Documentação](https://dart.dev/guides)
* [📺 Programação em Dart: Daniel Ciolfi](https://www.youtube.com/playlist?list=PLR5GUTqrcwXhVV-jNR38vfAZabkmGGKfO)
* [🎯O que é Dart?](https://www.treinaweb.com.br/blog/o-que-e-dart)
* [🎯 DartPad](https://dartpad.dev/)
* [🎯 Introdução à programação com Dart](https://dev.to/madebyluque/introducao-a-programacao-com-dart-aji)

***

<h2 id="licenca">🧾Licença</h2>

Este projeto está sob a licença [Apache 2.0](https://github.com/JosManoel/Dart-Study/blob/main/LICENSE).

*** 

<div align = "center">

  👋 Feito por [JosManoel](https://github.com/JosManoel) com ☕ , 🎧 e 💻.

</div>
