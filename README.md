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
  <a href="#topicos">🧮 Tópicos</a> &nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;
  <a href="#leitura">📚 Leitura e links recomendados</a> &nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;
  <a href="#licenca">🧾Licença</a>
</p>


***

<h2 id = "sobre-este-projeto">👨🏻‍💻 Sobre este projeto</h2>

Este repositório foi criado com o intuito de armazenar e organizar as anotações e exercícios realizados durante o aprendizado com a linguagem Dart. O material a seguir é de uso livre, sinta-se a vontade para utilizar estas anotações em seu desenvolvimento ou para contribuir com o conteúdo.

*  [Como posso contribuir?](https://github.com/JosManoel/Dart-Study/wiki)

***

<h2 id="o-que-e-dart">🎯 O que é Dart?</h2>

Dart é uma linguagem orientada à objetos fortemente tipada¹ que pode ser utilizada tanto do "lado do cliente" (front-end) como do lado do servidor(back-end). Ela foi criada em 2011 pelo Google originalmente para substituir o javascript, porém não obteve exito devida a evolução do JS e dos scripts para páginas web. Atualmente o Dart é considerado uma linguagem multi-paradigma, onde é comumente utilizada no desenvolvimento de aplicações em Flutter.

>1️⃣ Isto significa que as variáveis em Dart devem possuir um tipo que não será mudado ao longo do código. Este assunto será aprofundado no tópico sobre variáveis.

O Dart tem uma sintaxe baseada na linguagem C, deste modo, sua escrita se faz semelhante a linguagens populares, como o Java. No entanto, o Dart busca minimizar alguns "ruídos", priorizando um código mais limpo. Como exemplo, podemos vê este simples Hello World, que necessita de poucas linhas de código, quando comparada as linguagens citadas anteriormente.

~~~dart

void main() {
  print("Hello World!");
}
~~~

O Dart possui uma função principal denominada main, onde através dela, todo o código é iniciado. O Dart é uma linguagem case-sensitive, por isso, deve-se tomar cuidado ao escrever o código, para evitar possíveis erros.

A exemplo disso, temos o seguinte código, que ira gerar um erro, pois o Dart não reconhece uma função chamada **P**rint.

~~~dart

void main(){
    Print("Hello");
}
~~~
Sua versão correta seria:

~~~dart

void main(){
    print("Hello");
}
~~~

> Toda linha de código escrita em Dart é terminada em ; (ponto e virgula).

***

<h2 id="topicos">🧮 Tópicos</h2>

<h3>
    <img src="https://raw.githubusercontent.com/JosManoel/Dart-Study/main/images/icons/icone_basico.png" width = "28"> 
    1 - Módulo Básico
</h3>

1. [Utilizando os comentários](https://github.com/JosManoel/Dart-Study/blob/main/topics/1-1_Utilizando_os_comentarios.md) ✔️
2. [Declarando variáveis](https://github.com/JosManoel/Dart-Study/blob/main/topics/1-2_Declarando_variaveis.md) ✔️ 
3. [Manipulando Strings](https://github.com/JosManoel/Dart-Study/blob/main/topics/1-3_Manipulando_Strings.md) ✔️
4. [Operadores e operações](https://github.com/JosManoel/Dart-Study/blob/main/topics/1-4_Operadores_e_operacoes.md) ✔️
5. [Estruturas condicionais](https://github.com/JosManoel/Dart-Study/blob/main/topics/1-5_Estruturas_condicionais.md) ✔️
6. [Estruturas de repetição](https://github.com/JosManoel/Dart-Study/blob/main/topics/1-6_Estruturas_de_repeticao.md) ✔️

<h3>
    <img src="https://raw.githubusercontent.com/JosManoel/Dart-Study/main/images/icons/icone_intermediario.png" width = "28"> 
    2 - Módulo Intermediário
</h3>

1. [Criando funções](https://github.com/JosManoel/Dart-Study/blob/main/topics/2-1_Criando_funcoes.md)  ✔️
2. [Utilizando bibliotecas](https://github.com/JosManoel/Dart-Study/blob/main/topics/2-2_Utilizando_bibliotecas.md)  ✔️
3. [Utilizando classes](https://github.com/JosManoel/Dart-Study/blob/main/topics/2-3_Utilizando_classes.md)  🛠
4.
<h3>
    <img src="https://raw.githubusercontent.com/JosManoel/Dart-Study/main/images/icons/icone_avancado.png" width = "28"> 
    3 - Módulo Avançado
</h3>

1.
2.
3.

> ⚠️ Boa parte das variáveis utilizadas neste repositório possuem um tom descontraído, trazendo referencias a obras da cultura pop. O uso de variáveis como estas em outros projetos não é recomendado. ⚠️

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
