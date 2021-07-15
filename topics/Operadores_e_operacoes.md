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
## 📚 Leitura e links recomendado:
* [📝 Dart - Documentação](https://dart.dev/guides)
* [🎯 Introdução à programação com Dart](https://dev.to/madebyluque/introducao-a-programacao-com-dart-aji)
* [🎯 Linguagem Dart: operadores](https://www.devmedia.com.br/linguagem-dart-operadores/40724)

***
## 🧾Licença:
Este projeto está sob a licença [Apache 2.0](https://github.com/JosManoel/Dart-Study/blob/main/LICENSE).
