# Dart: Controle de fluxo - Estruturas condicionais <a href = "https://dart.dev/"><img src="https://raw.githubusercontent.com/JosManoel/Dart-Study/main/images/icons/dart.png" width = "24"></img></a>

As estruturas condicionais permitem executar determinados trechos do código caso alguma condição seja obedecida. Através destes operadores é possível manipular o fluxo natural de execução do código, otimizando-o e reduzindo o número de linhas necessárias para construção de uma função.

# If... else:
Os operadores **if/else** em dart possuem a mesma função e sintaxe como encontradas em outras linguagens. Sua função, em resumo, é executar um trecho do código caso a operação condicional retorne um valor true. O **if** pode ser utilizado sem a presença do **else**, porém o seu uso é recomendado para evitar possíveis erros de exceção.

### Exemplo da sintaxe do if/else
```
if(condicao_que_vai_ser_testada){
    //codigo que sera executado caso a condicao retorne true
}else{
    //codigo que sera executado caso a condicao retorne false
}
```

### Exemplo de utilização do if/else
```
var pokebola = true; 

if (pokebola == true){
    print("Capturar pokemon");
} else{
    print("Não capturar pokemon");
}
```

> Você também pode adicionar outras condições através do uso de operadores lógicos.

### Exemplo de utilização de dois fatores condicionais
```
var pokebola = true; 
var pokebola_vazia = true; 

// Caso 1: Operador logico AND (&&)

// caso a pokebola exista E ela esteja vazia, o pokemon sera capturado.
if (pokebola == true && pokebola_vazia == true){
    print("Capturar pokemon");
} else{
    print("Não capturar pokemon");
}


// Caso 2: Operador logico OR (&&)

// caso exista alguma pokebola, seja ela vazia OU nao, o treinar tera pokebolas.
if(pokebola == true || pokebola_vazia == true){
    print("Tenho pokebolas");
} else{
    print("Não tenho pokebolas");
}
```

### Concatenando if/else

O if/else também permite concatenar vários **else/if** entre o if e o else:

```
var estrelas = 0;
var delito = true;

if(delito == true){
    estrelas = 2;
}else if(estrelas > 0){
    print("Voce e procurado, CJ");
    print("Estrelas: " + estrelas.toString());
}else{
    print("Tudo limpo, CJ");
}
```
> Atente-se a necessidade do seu código, se esta estrutura for necessária, talvez seja melhor utilizar um switch/case.

> O ".toString()", utilizado no código acima é uma função que converte uma variável para uma String. Esta função será abordada melhor num futuro tópico.
***

# Operador Ternário 
O operador ternário é uma forma compacta de realizar o if/else, ideal para pequenas condicionais que podem ser escritas em apenas uma linha. 

### Estruturua de um operador ternário

|Variavel| Condição | Operador | Retorno caso a variável seja _true_ | Operador | Retorno caso a variável seja _false_| Resultado |
|-|-|-|-|-|-|-|
|Cavaleiro =  | true |  ?  |"Espada"| : |"Cajado"| Cavaleiro = "Espada"|
|Mago = | false| ?| "Espada"| : | "Cajado"| Mago = "Cajado"|

### Exemplo de utilização do operador ternário:
```
bool divida = false;
String conta;

conta = divida ? "saldo devedor" :"possui credito";
print(conta);

/* Caso a divida seja true, sera retornado um saldo devedor, caso contrario, sera retornado que a conta possui credito */
```
> Atente-se: O valor booleano da condição deve ser declarado (se é true ou false), caso contrário, será atribuído um valor null, causando um erro no código.

### Outra maneira de declarar um operador ternário
O operador possui uma forma ainda mais contraída, que atribui um valor padrão caso uma valor que está sendo recebido seja nulo:

|Variável| Valor repassado | Operador | Valor caso o a variável repassada seja nula|
|-|-|-|-|
|guilda = |"Almas da Ofensa" | ?? | "Sem guilda"

### Exemplo de utilização da segunda forma:
```
String nome = "Ataru";
String usuario = nome ?? "Não informado";

print(usuario);

/* Caso o nome tenha um valor diferente de null, ele sera atribuido ao usuario. Caso contrario, sera colocado como Nao informado */
```

## 📚 Leitura e links recomendado:
* [📝 Dart - Documentação](https://dart.dev/guides)
* [🎯 Introdução à programação com Dart](https://dev.to/madebyluque/introducao-a-programacao-com-dart-aji)
* [🎯 Linguagem Dart: Controle de Fluxo](https://www.devmedia.com.br/linguagem-dart-controle-de-fluxo/40758)
* [🎯 Estruturas condicionais e de repetição no Dart](https://www.treinaweb.com.br/blog/estruturas-condicionais-e-de-repeticao-no-dart)
* [🎯 toString method](https://api.flutter.dev/flutter/dart-core/num/toString.html)
* [🎯 Dart Intermediário: Condicionais](https://www.flutterbrasil.com/21-dart-intermediario-condicionais)
* [🎯 Video: Tomando Decisões (Condicionais)](https://www.youtube.com/watch?v=_FMjnxwxGzA&list=PLR5GUTqrcwXhVV-jNR38vfAZabkmGGKfO&index=5)
***
## 🧾Licença:
Este projeto está sob a licença [Apache 2.0](https://api.flutter.dev/flutter/dart-core/num/toString.html).
