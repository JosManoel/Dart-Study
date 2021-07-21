# Dart: Operadores e operações <a href = "https://dart.dev/"><img src="https://raw.githubusercontent.com/JosManoel/Dart-Study/main/images/icons/dart.png" width = "24"></img></a>


O Dart possui operadores semelhantes aos já bastante utilizados em outras linguagens, contanto com operadores aritméticos, operadores de incremento e operadores relacionais.

# Operadores aritméticos:

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


## Exemplo de utilização dos operadores aritméticos:

### Soma

* Você pode realizar a soma direto na atribução do valor da variável.

```
var soma = 90843 + 86170; // = 177013
print(soma);
// Saida: 177013
```

* Também é possível realizar a soma posteriormente:

```
var numero1 = 3000;
var numero2 = 2500;
print(numero1 + numero2);
// Saida: 5500
```
* Somando strings:

```
// Somando strings no print:

print("Aprendendo " + "dart " + "para " + "usar " + "no " + "Flutter");
// Saida: Aprendendo dart para usar no Flutter

// Somando strings de variaveis:
var titulo = "As aventuras de TIN-TIN";
var subtitulo = "O carangueijo das Pinças de ouro";

print(titulo + " Episodio: " + subtitulo);
// Saida: As aventuras de TIN-TIN Episodio: O carangueijo das Pinças de ouro
```
> Todos esses métodos de realizar operações com dados, com exceção da soma de strings, também são presentes nos outros operadores.

### Subtração

* Subtraindo valores:
```
var sub = 57 - 15; // = 42
print(sub);
// Saida: 42

var numero1 = 456;
var numero2 = 123;
print(numero1 - numero2);
// Saida: 333
```
### Multiplicação

* Multiplicação de valores:
```
var mult = 26 * 45; // = 1170
print(mult);
// Saida: 1170

var numero1 = 456;
var numero2 = 123;
print(numero1 - numero2);
// Saida: 333
```
### Divisão

* Divisão de valores:
```
var divi = 45 / 15; // = 3
print(divi);
// Saida: 3

var numero1 = 234;
var numero2 = 120;
print(numero1 / numero2);
// Saida: 1.95
```
* Obtendo apenas a parte inteira da divisão:

```
var numero1 = 234;
var numero2 = 120;
print(numero1 / numero2);
// Saida: 1
```

### Módulo 
* Retornando apenas o resto da divisão:
```
var numero1 = 5;
var numero2 = 2;
print(numero1 % numero2);
// Saida: 1
```
### Invertendo sinais

> A inversão de sinais é semelhante ao já utilizado em cálculos, onde basta colocar o sinal de subtração a frente da operação.

```
var inver = -(-2);
print(inver);
// Saida: 2
```
***
# Operadores de incremento
Os operadores de incremento são utilizados para diminuir ou incrementar uma variável em **1 unidade**. Normalmente são utilizados em laços como o for, que será abordado posteriormente. Os operadores de incremento são dividos em **prefixo** e **postfix**.

Exemplo:
```
// Incremento: ++
variavel++;
// adiciona +1 a variavel

// Decremento: --
variavel--;
// retira -1 da variavel
```

## Prefixo
Altera a variável antes de avaliar a expressão de condição.
```
++variavel; // Incremento
--variavel; // Decremento
```

## Postfix
Altera a variável após avaliar a expressão de condição.
```
variavel++; // Incremento
variavel--; // Decremento
```
***
# Operadores relacionais

Os operadores relacionais são destinados a comparações entre fatores, normalmente utilizados em condicionais, que serão abordados posteriormente. Os operadores relacionais retornam valores booleanos (**true**/**false**).

### Operadores relacionais:
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

Exemplo:

```
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
```
***
## 📚 Leitura e links recomendado:
* [📝 Dart - Documentação](https://dart.dev/guides)
* [🎯 Introdução à programação com Dart](https://dev.to/madebyluque/introducao-a-programacao-com-dart-aji)
* [🎯 Linguagem Dart: operadores](https://www.devmedia.com.br/linguagem-dart-operadores/40724)
* [🎯 Video: Realizando Operações Aritméticas](https://www.youtube.com/watch?v=mp7lNJH8Ws0&list=PLR5GUTqrcwXhVV-jNR38vfAZabkmGGKfO&index=3)
* [🎯 Video: Realizando Operações Lógicas](https://www.youtube.com/watch?v=1QQhZ61dg9k&list=PLR5GUTqrcwXhVV-jNR38vfAZabkmGGKfO&index=4)
***
## 🧾Licença:
Este projeto está sob a licença [Apache 2.0](https://github.com/JosManoel/Dart-Study/blob/main/LICENSE).
