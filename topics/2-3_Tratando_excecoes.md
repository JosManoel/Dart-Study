<img src="https://i.imgur.com/nhTNC7J.png"> 

<p>

**Autor:**
  <a href="https://github.com/JosManoel">Manoel Freitas</a>
</p>

Durante o desenvolvimento de aplicações não serão raras às vezes em que será necessário tratar algum evento indesejado que ocorreu durante a execução do software, seja por bugs no desenvolvimento ou entradas incorretas do usuário.

Para estes casos, na programação, essas ocorrências são solucionadas pelos mecanismos de tratamento de exceções, responsáveis por direcionar o programa para uma **rotina de tratamento**, quando o fluxo normal é interrompido. 

***
<h2 id="sumario">🧮 Sumário</h2>
  
  * <a href="#O_que_e_uma_excecao">O que é uma exceção?</a>
      * <a href="#Checked">Exceções checadas (Checked Exceptions)</a>
      * <a href="#Unchecked">Exceções não checadas (Unchecked Exceptions)</a>
  * <a href="#Tratando_excecoes">Tratando exceções</a>
      * <a href="#Catch">Try... Catch</a>
      * <a href="#On">On</a>
      * <a href="#Finally">Finally</a>
  * <a href="#Throw">Throw</a>
  * <a href="#Rethrow">Rethrow</a>
  * <a href="#Personalizadas">Exceções personalizadas</a>
  * <a href="#Dart_core-exception">Dart Core: Exceptions</a>
  * <a href="#Dart_core-error">Dart Core: Error</a>
  * <a href="#leitura_e_link">📚 Leitura e links recomendado</a>
  * <a href="#licenca">🧾Licença</a>

***


<h2 id="O_que_e_uma_excecao">O que é uma exceção?</h2>

No desenvolvimento de software, uma **exceção** ocorre quando um evento indesejado interrompe o fluxo de execução convencional do código, seja por algum erro de programação ou alguma entrada inválida do usuário. Isso pode acontecer ao informar um valor numérico, quando era esperando uma string, ou quando estava esperando algum valor retornado como nulo.


<h3 align="center">Fluxo de execução de um software</h3>

<p align="center">
    <img src="https://i.imgur.com/QjQMGVp.png" height="320"> 
</p>

> Neste exemplo podemos observar a execução de um programa que recebeu uma exceção na 2° instrução, levando a um tratamento e a sua finalização. Este fluxograma representa uma quebra clara no fluxo de execução de um software, que acontece sempre que uma exceção ocorre.

As exceções ainda podem ser classificadas em dois tipos: as **exceções checadas (checked)** e as **exceções não checadas (unchecked)**. 

<h3 id="Checked">Exceções checadas (Checked Exceptions)</h3>

As exceções chegadas, de maneira geral, são utilizadas para sinalizar condições inválidas em áreas que necessitam obrigatoriamente de uma resolução imediata. Um bom exemplo disso pode ser visto em softwares de leitura em pdf, que retornará uma mensagem de erro com a sinalização de "**Arquivo inválido**", quando um formato de documento diferente do pdf for submetido. 

Essa é uma das principais características de uma **checked exception**: a exceção deve obrigatoriamente ser tratada, seja com um bloco **try-catch** ou outros métodos que a linguagem utilizada disponibilizar. 

<h3 id="Unchecked">Exceções não checadas (Unchecked Exceptions)</h3>

As exceções não checadas funcionam de maneira contrária as exceções checadas, já que não existe a necessidade de tratá-las, apesar do erro ou bug continuar em execução até que sejam verificadas por algum método desenvolvido pelo programador, ou até que o programa seja encerrado inesperadamente.

> Este é o tipo mais comum, presente na maioria das linguagens de programação, incluindo o Dart.

Apesar de existência dessas essas duas definições, nem todas as linguagens de programação compartilham das duas exceções, como o Ruby, C# e Dart, que não possuem as **checked exceptions**, ao contrário do Java, que utiliza ambas.

Para lidar esses erros, diversas linguagens de programação desenvolveram seus próprios métodos de tratamento, incluindo estruturas condicionais e bibliotecas específicas, como a classe exceptions, da biblioteca dart:core, que será abordada a seguir.

<p align="right">
    <a href="#sumario">
        <img src="https://raw.githubusercontent.com/JosManoel/Dart-Study/main/images/icons/voltar_ao_topo.png" height="32">
    </a>
</p>

***

<h2 id="Tratando_excecoes">Tratando exceções</h2>

O Dart possui diversas maneiras de lidar com exceções, incluindo não lidar com elas. Diferentemente de outras linguagens como o Java, todas as exceções do Dart são exceções do tipo **unchecked**, o que significa que não é necessário tratá-las.

> Quando um exceção não é tratada no Dart a chamada que gerou a exceção será suspensa e posteriormente encerrada em conjunto com o programa, caso seja necessário. 

> O Dart ainda possui duas classes de exceções, sendo elas a **Exception** e a **Error**, que fazem parte da biblioteca dart:core e serão abordadas posteriormente. 

No Dart as exceções basicamente podem ser tratadas utilizando os métodos **Try... Catch**, **Finally** e **Throw**.


<h2 id="Catch">Try... Catch</h2>

O conjunto de blocos **Try... Catch** é bastante utilizado por diversas linguagens de programação, como o Java e JavaScript. No Dart, seu funcionamento ocorre de maneira semelhante as outras ferramentas de desenvolvimento, seguindo a seguinte sintaxe:

*  **Try:** Bloco responsável por "conter" o trecho de código que será analisado. Sua função é verificar se o código que está dentro do seu bloco, quando executado, retorna algum erro, _desviando o fluxo de execução_ do programa para um segundo bloco de tratamento, seja ele um **Catch** ou um **On**.

* **Catch** Bloco responsável por executar o tratamento do erro relatado pelo bloco **Try**. Sua função é executar uma série de comportamentos definidos pelo desenvolvedor para o código de erro especificado.

<h3 align="center">Sintaxe de utilização do Try... Catch</h3>

~~~dart

try{
    //Bloco que receberá o código que será analisado pelo try.
}

catch(parametro_de_erro){
    //Bloco responsável por executar o tratamento definido pelo desenvolvedor.
}
~~~

<h3 align="center">Try... Catch - Exemplo prático</h3>

~~~dart
main() { 
   int saitama_forca = 10; 
   int saitama_cabelo = 0; 
   int saitama_poder;  
   
   try {  
     saitama_poder = saitama_forca ~/ saitama_cabelo;
     print("Nível de poder do Saitama: ${saitama_poder}");
   }  
   catch(e) { 
      print(e); 
   } 
} 
~~~

<p align="center">
    <a href="https://dartpad.dev/?id=2617993072e628d81cd3e0cbe6d41f6a">
        <img src="https://i.imgur.com/Z8T7RJU.png" height="24">
    </a>
</p>

> Experimente aumentar o valor da variável "saitama_cabelo".

Note que, ao executar este código, uma mensagem de erro será exibida ao invés do resultado esperado na variável "saitama_poder". Isso acontece devido ao erro retornado pela divisão por zero, desviando o fluxo comum de execução do código para o bloco **Catch**.

Perceba que o erro exibido pelo bloco **Catch** é proveniente do parâmetro **_e_**, um parâmetro de erro retornado pelo bloco **Try** e que pode possuir qualquer nome, apesar de ser convencionalmente atribuído apenas como "e" para erros genéricos.

O erro retornado simboliza uma exceção por _"Unsupported operation"_, um erro do tipo _"Error class"_, uma classe de exceções suportada pelo Dart e que será abordada posteriormente. 

<p align="right">
    <a href="#sumario">
        <img src="https://raw.githubusercontent.com/JosManoel/Dart-Study/main/images/icons/voltar_ao_topo.png" height="32">
    </a>
</p>

<h2 id="On">On</h2>

O bloco **On** possui um funcionamento semelhante ao bloco **Catch**, porém é destinado ao uso em situações em que já se sabe qual será a categoria de erro retornado. Através dele é possível realizar o tratamento de exceções específicas, definidas pelas bibliotecas do dart, seja ela do tipo **Exception** ou **Error**, que serão abordadas posteriormente.

Podemos tomar como exemplo o código anterior, já que já sabemos que o erro retornado é um erro do tipo _"Unsupported operation"_, da [UnsupportedError class](https://api.dart.dev/stable/2.16.2/dart-core/UnsupportedError-class.html). Portanto, podemos reescrever o código como:

<h3 align="center">Try... On - Exemplo prático</h3>

~~~dart
main() { 
   int saitama_forca = 10; 
   int saitama_cabelo = 0; 
   int saitama_poder;  
   
   try {  
     saitama_poder = saitama_forca ~/ saitama_cabelo;
     print("Nível de poder do Saitama: ${saitama_poder}");
   }  
   on UnsupportedError { 
      print("UnsupportedError: operação inválida"); 
   } 
} 
~~~

<p align="center">
    <a href="https://dartpad.dev/?id=ad550a6fe89ceddce2e1d2cf4d054fc2">
        <img src="https://i.imgur.com/X8nLz0A.png" height="24">
    </a>
</p>

> Os tipos de erros suportados pelo bloco de tratamento On será abordado posteriormente, nos tópicos sobre Dart Core Exceptions e Errors.

Note que neste caso não possuímos o parâmetro de erro, já que o bloco **On** não possui suporte a parâmetros.

O bloco **On** ainda pode ser combinado com o **Catch**, normalmente utilizado quando queremos capturar tanto erros conhecidos como erros desconhecidos. Encadear blocos **On** e **Catch** pode ser bastante útil para criar tratamentos de exceções robustos em aplicações.

<h3 align="center">Sintaxe de utilização do Try... On/Catch</h3>

~~~dart

try{
    //Bloco que receberá o código que será analisado pelo try.
}

on Excecao_conhecida{
    //Bloco responsável por executar o tratamento definido pelo desenvolvedor
    //para situações préviamente conhecidas.

}
catch(parametro_de_erro){
    //Bloco responsável por executar o tratamento definido pelo desenvolvedor.
}
~~~

<h3 align="center">Try... On/Catch - Exemplo prático</h3>

~~~dart
main() { 
   main() { 
  // Alterne a variável "saitama_cabelo" entre "0" e "null"
   var saitama_forca = 10; 
   var saitama_cabelo = 0; 
   var saitama_poder;  
   
   try {  
     saitama_poder = saitama_forca ~/ saitama_cabelo;
     print("Nível de poder do Saitama: ${saitama_poder}");
   }  
   on UnsupportedError{ 
      print("Erro capturado pelo bloco On"); 
      print("UnsupportedError: operação inválida"); 
   }
   catch(e) { 
      print("Erro capturado pelo bloco Catch"); 
      print(e); 
   } 
}   
~~~

<p align="center">
    <a href="https://dartpad.dev/?id=6c5a7d24c33404556d63031e22476b15">
        <img src="https://i.imgur.com/RSX2Sun.png" height="24">
    </a>
</p>


<p align="right">
    <a href="#sumario">
        <img src="https://raw.githubusercontent.com/JosManoel/Dart-Study/main/images/icons/voltar_ao_topo.png" height="32">
    </a>
</p>

<h2 id="Finally">Finally</h2>

O bloco **Finally** funciona como um complemento ao tratamento de exceções. Sua função é excecutar uma série de funções definidas pelo desenvolvedor independente do erro reportado pelo bloco **Try**, mesmo que ele não retorne nenhuma exceção. Qualquer código escrito dentro deste bloco será executado, independente do retorno ou não de algum erro.

O **Finally** pode ser bastante útil em situações onde desejamos definir um comportamento padrão para a finalização de um programa. Por exemplo, podemos ter uma situação onde criamos um sistema de login, que sempre pergunta ao usuário se ele deseja realmente sair da página, independente do login ter retornado algum erro ou não.

<h3 align="center">Sintaxe de utilização do Try... On/Catch - Finally</h3>

~~~dart

try{
    //Bloco que receberá o código que será analisado pelo try.
}

on Excecao_conhecida{
    //Bloco responsável por executar o tratamento definido pelo desenvolvedor
    //para situações préviamente conhecidas.

}
catch(parametro_de_erro){
    //Bloco responsável por executar o tratamento definido pelo desenvolvedor.
}
finally {
    //Instruções que serão executadas independente do erro retornado.
}
~~~

<h3 align="center">Try... On/Catch - Exemplo prático</h3>

~~~dart
main() { 
   var saitama_forca = 10; 
   var saitama_cabelo = 0; 
   var saitama_poder;  
   
   try {  
     saitama_poder = saitama_forca ~/ saitama_cabelo;
     print("Nível de poder do Saitama: ${saitama_poder}");
   }  
   on UnsupportedError{ 
      print("Erro capturado pelo bloco On"); 
      print("UnsupportedError: operação inválida"); 
   }
   catch(e) { 
      print("Erro capturado pelo bloco Catch"); 
      print(e); 
   }
   finally {
     print("Cálculo de poder do Saitama encerrado");
   }
}   
~~~

<p align="center">
    <a href="https://dartpad.dev/?id=cb76459c8417f12c2732d249ae009bc2">
        <img src="https://i.imgur.com/xROnijT.png" height="24">
    </a>
</p>

<p align="right">
    <a href="#sumario">
        <img src="https://raw.githubusercontent.com/JosManoel/Dart-Study/main/images/icons/voltar_ao_topo.png" height="32">
    </a>
</p>

***
<h2 id="Throw">Throw</h2>

O método throw possui uma funcionalidade bastante peculiar: gerar explicitamente uma exceção. Através do **Throw** é possível criar chamadas para exceções que serão tratadas posteriormente, mesmo que não exista propriamente um erro no código analisado. Seu funcionamento é simples, bastando chamar o **Throw** com alguma das classes de exceções desejadas. O Throw ainda pode ser combinado a outros elementos, como as funções, para criar as **Exceções personalizadas**, que serão abordadas a seguir.

<h3 align="center">Sintaxe de utilização do Throw</h3>

~~~dart
throw Classe_de_Excecao(parametros_quando_necessario);
~~~

> Alguns tutoriais podem trazer a sintaxe do throw em conjunto com o "new" (throw new), no entanto, segundo a documentação atual do dart, o uso do "new" para criar novas instâncias não é mais necessário.

O **Throw** pode ser utilizado para diversos tipos de exceções, como o **FormatException** e o **UnsupportedError**, bem como todos os seus parâmetros definidos pela documentação. Para vê lista completa acesse [este link](https://api.dart.dev/stable/2.17.0/dart-core/dart-core-library.html#exceptions).

<h3 align="center">Throw - Exemplo prático</h3>

~~~dart
main() { 
   var saitama_forca = 10; 
   var saitama_cabelo = 0; 
   var saitama_poder;  
   
   try {  
     if(saitama_cabelo > 0){
        throw FormatException("Saitama deve ser careca");  
     }
     
     saitama_poder = saitama_forca ~/ saitama_cabelo;
     print("Nível de poder do Saitama: ${saitama_poder}");
   }  
   on UnsupportedError{ 
      print("Erro capturado pelo bloco On"); 
      print("UnsupportedError: operação inválida"); 
   }
   catch(e) { 
      print("Erro capturado pelo bloco Catch"); 
      print(e); 
   }
   finally {
     print("Cálculo de poder do Saitama encerrado");
   }
}   
~~~

> Experimente aumentar o valor da variável "saitama_cabelo". 

<p align="center">
    <a href="https://dartpad.dev/?id=d5417800ca5c115e617a4875a33117ad">
        <img src="https://i.imgur.com/sbTnZQn.png" height="24">
    </a>
</p>

Note que quando a variável _"saitama_cabelo"_ possui um valor maior que zero, é lançado um FormatException com a mensagem _"Saitama deve ser careca"_, que é capturada e exibida pelo bloco **Catch**.

<p align="right">
    <a href="#sumario">
        <img src="https://raw.githubusercontent.com/JosManoel/Dart-Study/main/images/icons/voltar_ao_topo.png" height="32">
    </a>
</p>

***

<h2 id="Rethrow">Rethrow</h2>

No Dart, além de capturar as exceções, também é possível relançá-las para poderem ser tratadas em outros níveis mais complexos. Essa tarefa originalmente poderia ser feita através do **Throw**, no entanto, para melhorar a sintaxe e tornar o código mais legível, o Dart adicionou um recurso denominado **Rethrow**, responsável por relançar uma exceção capturada para um nível mais alto.

O **Rethrow** possui uma sintaxe ainda mais simples, bastando chamá-lo ao fim do bloco de tratamento.

<h3 align="center">Sintaxe de utilização do Rethrow</h3>

~~~dart
//Bloco de tratamento de excecao 
//... 
rethrow;
//...
~~~

<h3 align="center">Rethrow - Exemplo prático</h3>

~~~dart
main() { 
   var saitama_forca = 10; 
   var saitama_cabelo = 0; 
   var saitama_poder;  
   
   try {  
     if(saitama_cabelo > 0){
        throw FormatException("Saitama deve ser careca");  
     }
     
     saitama_poder = saitama_forca ~/ saitama_cabelo;
     print("Nível de poder do Saitama: ${saitama_poder}");
   }  
   on UnsupportedError{ 
      print("Erro capturado pelo bloco On"); 
      print("UnsupportedError: operação inválida"); 
      rethrow;
   }
   catch(e) { 
      print("Erro capturado pelo bloco Catch"); 
      print(e);
   }
   finally {
     print("Cálculo de poder do Saitama encerrado");
   }
}    
~~~

> Note que agora o console também retorna um "Uncaught Error", resultado do tratamento do "UnsupportedError" em um nível mais alto. 

<p align="center">
    <a href="https://dartpad.dev/?id=731be0b9bac48f1ed677b04929566fca">
        <img src="https://i.imgur.com/7QUft2k.png" height="24">
    </a>
</p>


<p align="right">
    <a href="#sumario">
        <img src="https://raw.githubusercontent.com/JosManoel/Dart-Study/main/images/icons/voltar_ao_topo.png" height="32">
    </a>
</p>

***
<h2 id="#Personalizadas">Exceções personalizadas</h2>

O Dart permite ainda a criação de exceções personalizadas para suas aplicações. Do mesmo modo que as outras exceções são subtipos da classe interna "_Exception_", no Dart, as exceções personalizadas também são extensões desta classe. Apesar de trazer novos elementos, sua sintaxe ainda continua bastante simples, possuindo a seguinte estrutura:


<h3 align="center">Exceções personalizadas - Sintaxe</h3>

~~~dart
class Nome_da_excecao_personalizada implements Exception {
    //instruções para o tratamento de exceções
}
~~~

Note que agora utilizamos fortemente o conceito de classes, com termos como "_class_" e "_implements_". Apesar deste tema ainda não ter sido abordado, seu completo entendimento não será necessário neste momento. Por enquanto, iremos utilizá-los apenas como "membros da sintaxe". Posteriormente entraremos a fundo e suas definições no tópico sobre classes.

As exceções personalizadas possuem certas peculiaridades quanto a sua utilização quando comparada as demais. Por exemplo, para que uma exceção personalizada retorne uma mensagem de erro, será necessário antes criar uma função que será responsável por efetuar o retorno da mensagem, quando chamada. A criação desta função pode ser efetuada de diversas formas, mas a sintaxe mais utilizada para executá-la é a [Big Arrow Function](https://github.com/JosManoel/Dart-Study/blob/main/topics/2-1_Criando_funcoes.md#BigArrowF), por ser mais compacta. Para que seja exibida a mensagem de erro, será necessário chamar a classe da exceção personalizada com sua função, conforme a seguinte sintaxe:

<h3 align="center">Exceções personalizadas - Mensagem de erro</h3>

~~~dart
class Nome_da_excecao_personalizada implements Exception {
    String mensagem_de_erro()=> "Texto de erro";
}

//...

//Printando a mensagem na tela.
print(Nome_da_excecao_personalizada.mensagem_de_erro());
~~~

Para o uso de exceções customizadas também é recomendado que se utilize outras funções para lançar o erro com o uso do **throw**. Deste modo, é possível manter o tratamento de erro separado do lançamento de exceções, mantendo o código legível.

<h3 align="center">Exceções personalizadas - Exemplo prático</h3>

~~~dart
// Exceção customizada
class carecaException implements Exception{
  String erroMsg()=> "Saitama deve ser careca";
}

main() { 
   var saitama_forca = 10; 
   var saitama_cabelo = 1; 
   var saitama_poder;  
   
   try {  
     carecaChecker(saitama_cabelo);
     
     saitama_poder = saitama_forca ~/ saitama_cabelo;
     print("Nível de poder do Saitama: ${saitama_poder}");
   }  
   on carecaException{ 
     carecaException e = carecaException();
     print(e.erroMsg());
   }

   finally {
     print("Cálculo de poder do Saitama encerrado");
   }
}   

// Função de verificação
void carecaChecker(cabelo){
  if(cabelo > 0){
    throw carecaException();  
  }
}
~~~

<p align="center">
    <a href="https://dartpad.dev/?id=30aa169e8ccfcd22adb8ec865e6805d9">
        <img src="https://i.imgur.com/PBpepuR.png" height="24">
    </a>
</p>

<p align="right">
    <a href="#sumario">
        <img src="https://raw.githubusercontent.com/JosManoel/Dart-Study/main/images/icons/voltar_ao_topo.png" height="32">
    </a>
</p>


***
<h2 id="Dart_core-exception">Dart Core: Exceptions</h2>

O Dart possui uma clara definição quanto a diferença entre **Exception** e **Error**, utilizando duas bibliotecas distintas para implementar cada um desses elementos. A primeira delas, a **Exception Class** é definida como uma "interface" para todas as exceções da **Dart:core Library**, destinada à transmissão e capturas de falhas em tempo de execução. 

Por definição, a **Exception Class** deve ser utilizada sempre que queremos tratar um erro esperado, como os exemplos desenvolvidos neste artigo. A **Exception Class** implementa 7 tipos de exceções, sendo elas:

* [DeferredLoadException](https://api.dart.dev/stable/2.16.2/dart-async/DeferredLoadException-class.html)
* [FormatException](https://api.dart.dev/stable/2.16.2/dart-core/FormatException-class.html)
* [IOException](https://api.dart.dev/stable/2.16.2/dart-io/IOException-class.html)
* [IsolateSpawnException](https://api.dart.dev/stable/2.16.2/dart-isolate/IsolateSpawnException-class.html)
* [NullRejectionException](https://api.dart.dev/stable/2.16.2/dart-js_util/NullRejectionException-class.html)
* [OSError](https://api.dart.dev/stable/2.16.2/dart-io/OSError-class.html)
* [TimeoutException](https://api.dart.dev/stable/2.16.2/dart-async/TimeoutException-class.html)

A documentação completa da **Exception Class** pode ser encontrada [neste link](https://api.dart.dev/stable/2.16.2/dart-core/Exception-class.html).

<p align="right">
    <a href="#sumario">
        <img src="https://raw.githubusercontent.com/JosManoel/Dart-Study/main/images/icons/voltar_ao_topo.png" height="32">
    </a>
</p>

***

<h2 id="Dart_core-error">Dart Core: Error</h2>

Ao contrário da **Exception**, a **Error Class** trata de erros do software e não devem ser capturados, mas sim endereçados ao desenvolvedor, para que possam ser corrigidos fora do tempo de execução. Apesar de também ser possível capturá-los com o tratamento de exceções, como feito com o _UnsupportedError_ em alguns dos exemplos, a sua utilização para estes fins é fortemente desencorajada, sendo mais usual e seguro o encerramento por completo da aplicação.

De modo geral, um **Error** pode ser definido como uma falha no programa que o desenvolvedor deveria ter evitado, como chamar uma função com argumentos inválidos ou um momento que não era permitido. 

A variedade de erros implementados pela **Error Class** é bem mais amplo que as 7 principais exceções da **Exception Class** e podem ser acessados a partir de sua [documentação](https://api.dart.dev/stable/2.16.2/dart-core/Error-class.html).

<p align="right">
    <a href="#sumario">
        <img src="https://raw.githubusercontent.com/JosManoel/Dart-Study/main/images/icons/voltar_ao_topo.png" height="32">
    </a>
</p>




***
<h2 id="#leitura_e_link"> 📚 Leitura e links recomendados </h2>

* [📝 Dart - Documentação](https://dart.dev/guides)
* [🎯 Language Tuor: Exceptions](https://dart.dev/guides/language/language-tour#exceptions)
* [🎯 Library Tuor: Exceptions](https://dart.dev/guides/libraries/library-tour#exceptions)
* [🎯 Dart:core library - Exception class](https://api.dart.dev/stable/2.16.2/dart-core/Exception-class.html)
* [🎯 Dart:core library - Error class](https://api.dart.dev/stable/2.16.2/dart-core/Error-class.html)
* [🎯 Dart – Types of Exceptions](https://www.geeksforgeeks.org/dart-types-of-exceptions/)
* [🎯 Dart Programming - Exceptions](https://www.tutorialspoint.com/dart_programming/dart_programming_exceptions.htm)
* [🎯 Do use retrow to rethrow a caught exception](https://dart.dev/guides/language/effective-dart/usage#do-use-rethrow-to-rethrow-a-caught-exception)
* [🎯 use_rethrow_when_possible](https://dart-lang.github.io/linter/lints/use_rethrow_when_possible.html)
* [🎯 Dart - Creating Custom Exception Class](https://www.woolha.com/tutorials/dart-creating-custom-exception-class)
* [🎯 avoid_catching_errors](https://dart-lang.github.io/linter/lints/avoid_catching_errors.html)

<p align="right">
    <a href="#sumario" style="font-size:1rem;font-weight: bold;">
        <img src="https://raw.githubusercontent.com/JosManoel/Dart-Study/main/images/icons/voltar_ao_topo.png" height="32">
    </a>
</p>

***
<h2 id="#licenca"> 🧾Licença </h2>

Este projeto está sob a licença [Apache 2.0](https://github.com/JosManoel/Dart-Study/blob/main/LICENSE).

<p align="right">
    <a href="#sumario" style="font-size:1rem;font-weight: bold;">
        <img src="https://raw.githubusercontent.com/JosManoel/Dart-Study/main/images/icons/voltar_ao_topo.png" height="32">
    </a>
</p>
