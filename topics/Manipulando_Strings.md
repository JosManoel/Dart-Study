# Dart: Manipulando Strings <a href = "https://dart.dev/"><img src="https://raw.githubusercontent.com/JosManoel/Dart-Study/main/images/icons/dart.png" width = "24"></img></a>

As Strings são usadas principalmente para apresentar texto, funcionando basicamente como uma **lista de caracteres**. O Dart representa uma String como uma sequência de unidades de código **UTF-16**, onde cada caractere pode ser representado por uma ou mais unidades, como é comumente utilizado em **emojis**, que necessitam de pelo menos duas unidades de código.  

## Formato UTF-16
No formato UTF-16 os caracteres são codificados em duas mais palavras ( unidades de códigos ou **code units** ). Um fator importante sobre o formato UTF-16 é que os códigos em **UNICODE**, de **U+0000 a U+FFFF**, são representados pelo seu próprio valor, ocorrendo apenas a substituição do **U+** pelo **0x**.

| UTF-16 | UNICODE | Saída |
|--------|---------|-------|
| 0x007A | U+007A  |   z   |

Durante a programação utilizando a linguagem Dart o conhecimento completo do formato UTF-16 não se faz necessário. Entretanto, é preciso ter em mente que esse formato possui algumas peculiaridades em relação à representação de emojis que podem resultar em possíveis erros. O tratamento desses casos será abordado em um futuro tópico.
# Strings de linha única e multilinhas.

O Dart possui várias maneiras para a declaração de uma String, em que podem ser declaradas usando aspas pares simples ou duplas. Em casos de Strings com múltiplas linhas, a declaração deve ocorrer com o uso de aspas triplas.

### Exemplo de declaração das Strings

```
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
```

# Modificando e realizando operações

Em suma, as strings são imutáveis. No entanto, é possível realizar operações com uma string, resultando na criação de uma nova. Como exemplo disso temos a concatenação de strings, que resulta numa nova string que contém a informação de todas as outras.
### Exemplo de concatenação de Strings
```
var conc = "Kobayashi-san " + "Chi no " + "Maid Dragon";
```
> Também é possível concatenar strings sem utilizar o operador '+'

```
var conc = "Kobayashi-san " + "Chi no " + "Maid Dragon";
```
## Interpolando variáveis 
O processo de interpolação de variáveis acontece de maneira semelhante ao JavaScript, em que a variável é incluída entre chaves.

```
var episodios = 13;
print ("Numero de episodios da 1 temporada: ${episodios}");
```

## Contando caracteres 
No Dart os caracteres são contados a partir do **Code Units** e, para isso, são utilizadas diferentes funções, de acordo com cada necessidade. Em um primeiro cenário, podemos utilizar o **length** para descobrir quantos caracteres existem dentro de uma string, da mesma forma que ocorre com as **listas**. Isso acontece porque uma string nada mais é que uma lista de caracteres, que podem ser acessados individualmente através do índice.
### Exemplo de utilização do lenght
```
var frase = "Em todos esses anos nessa industria vital, essa é a 1 vez que isso me acontece";
  
print(frase.length);

// imprimindo um caractere pelo indice
print(frase[1]);

//Saída: m 
```

O Dart também permite recuperar o Code Unit de cada caractere, utilizando o **codeUnitAt**, que retorna o número de um caractere específico, ou o **codeUnits**, que retorna uma lista com todos os códigos.

```
// CodeUnits
var nome = "Jaden";
print(nome.codeUnits);
// Saída: [74, 97, 100, 101, 110]

// CodeUnitsAt
print(nome.codeUnitAt(1));
// Saída: 97

```
## 📚 Leitura e links recomendado:
* [📝 Dart - Documentação](https://dart.dev/guides)
* [🎯 String class](https://api.dart.dev/stable/2.13.4/dart-core/String-class.html)
* [🎯 Top 10 String utility methods you should know (Dart)](https://codeburst.io/top-10-string-utility-methods-you-should-know-dart-b51ef65b3cc2)
* [🎯 Dart string manipulation done right](https://medium.com/dartlang/dart-string-manipulation-done-right-5abd0668ba3e)
* [📝 Transformação entre as representações UTF-8 e UTF-16](http://www4.inf.puc-rio.br/~inf1018//2013.1/trabs/t1/trab1.html)

***
## 🧾Licença:
Este projeto está sob a licença [Apache 2.0](https://github.com/JosManoel/Dart-Study/blob/main/LICENSE).

