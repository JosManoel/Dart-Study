<img src="https://i.imgur.com/tTUsTGq.png"> 

<p>

**Autor:**
  <a href="https://github.com/JosManoel">Manoel Freitas</a>
</p>

Vimos anteriormente no tratamento de exceções que a execução de um código normalmente segue uma rotina linear, em que cada ação é executada em sequência, caracterizando um fluxo síncrono de atividades. Além do fluxo síncrono, o desenvolvimento de uma aplicação também pode possuir elementos assíncronos que não agem linearmente, conforme veremos nesse artigo.

***
<h2 id="sumario">🧮 Sumário</h2>

  * <a href="#intro">Fluxo de execução de um software</a>
    * <a href="#sincrono">Execução síncrona</a>
    * <a href="#assincrono">Execução assíncrona</a>
    * <a href="#concorrencia">Concorrência e paralelismo</a>
  * <a href="#dart_assincrono">Dart - programação assíncrona</a>
    * <a href="#isolates">Isolates</a>
    * <a href="#event-loop">Loop de eventos</a>
  * <a href="#funcoes">Criando funções assíncronas</a>
    * <a href="#future">Future</a>
    * <a href="#stream">Stream</a>
    * <a href="#excecoes">Funções assíncronas e exceções</a>
  * <a href="#leitura_e_link">📚 Leitura e links recomendados</a>
  * <a href="#licenca">🧾Licença</a>

***

<h2 id="intro">Fluxo de execução de um software</h2>

Quando trabalhamos com o tratamento de exceções, observamos que todo software possui uma determinada ordem de execução de suas instruções, sendo normalmente sequenciais. Nestes casos temos o que é chamado de programação síncrona, onde cada instrução é processada na ordem que foi escrita no programa através do **loop de eventos**.

Entretanto, conforme o desenvolvimento de software adentrou a computação em nuvem e o tratamento de grandes volumes de dados, surgiu a necessidade de utilizar outros processos de execução como a programação **assíncrona**.

<p align="right">
    <a href="#sumario">
        <img src="https://raw.githubusercontent.com/JosManoel/Dart-Study/main/images/icons/voltar_ao_topo.png" height="32">
    </a>
</p>


<h2 id="sincrono">Execução síncrona</h2>

Na **programação síncrona** cada entrada no **loop de eventos** é individual, com as instruções sendo processadas e executadas conforme a "ordem de chegada". Apesar de bastante funcional, esse método pode se mostrar bastante lento na leitura e tratamento de grandes volumes de dados ou na requisição de informações de fontes externas, visto que o software permanece "bloqueado" até que a execução de um determinado trecho seja encerrada e inicie outra.

<h3 align="center">Programação síncrona - Fluxograma de execução</h3>

<p align="center">
    <img src="https://i.imgur.com/HMMaGdB.png" width="600"> 
</p>

> Na prática, a programação síncrona possui uma sequência linear de execução.

<p align="right">
    <a href="#sumario">
        <img src="https://raw.githubusercontent.com/JosManoel/Dart-Study/main/images/icons/voltar_ao_topo.png" height="32">
    </a>
</p>

<h2 id="assincrono">Execução assíncrona</h2>

Já na **programação assíncrona** temos a execução de determinados processos em segundo plano através do **loop de eventos**. Os métodos de **execução assíncrona** costumam ser utilizados em ambientes onde lidamos com grandes quantidades de dados ou ferramentas que demandem o uso da rede, como a busca de dados em API's e a leitura e gravação de dados. 

Nessa modalidade ainda temos uma entrada linear de processos, apesar de permitir a inserção de outra instrução enquanto a anterior ainda está sendo executada. Dessa forma, podemos ter a execução de diversas rotinas em segundo plano enquanto novas entradas são computadas, apresentando o resultado do processo conforme é finalizado e não em "ordem de chegada".

<h3 align="center">Programação assíncrona - Fluxograma de execução</h3>

<p align="center">
    <img src="https://i.imgur.com/qdYIzo9.png" width="600"> 
</p>

> Note que, apesar do segundo objeto ser executado por último, o seu processo é finalizado mais rapidamente, enquanto a primeira entrada ainda está sendo computada.

<p align="right">
    <a href="#sumario">
        <img src="https://raw.githubusercontent.com/JosManoel/Dart-Study/main/images/icons/voltar_ao_topo.png" height="32">
    </a>
</p>


***

<h2 id="concorrencia">Concorrência e paralelismo</h2>

A programação assíncrona não está isenta dos problemas de administração de recursos. Com o intuito de facilitar a execução simultânea de diversas instruções surgiram alguns métodos para gerenciamento de processos, como o **paralelismo** e a **programação concorrente**. 

Para determinar as características da **concorrência** e do **paralelismo** é comum que utilizem a definição descrita por Rob Pike, um dos criadores da linguagem Go. Segundo ele, quando tratamos de **concorrência** estaríamos gerenciando a execução de vários processos enquanto que no **paralelismo** o objetivo seria processar diversos itens em simultâneo. Dessa forma, podemos assumir a **programação concorrente** como um elemento ao nível de software e o **paralelismo** como um conceito ao nível de hardware.

De certo modo, podemos observar nitidamente o **paralelismo** ao executar duas tarefas diferentes ao mesmo tempo em núcleos diferentes de um processador. Já a **concorrência** é observada em situações em que um programa possui diversas tarefas diferentes que podem ser executadas em ordem diferentes. Outro exemplo comum para a programação concorrente é de um software que faz o download de dois elementos e os combina em um só. Nesse caso, não importa a ordem que os objetos serão baixados, desde que só sejam combinados quando o download dos dois estiverem completos.

Nas versões mais recentes do Dart não temos o uso explicito do **paralelismo** com funções assíncronas, uma vez que todos os eventos são executados seguindo uma ordem regular de requisições do loop de eventos, conforme perceberemos no decorrer do artigo. 

<p align="right">
    <a href="#sumario">
        <img src="https://raw.githubusercontent.com/JosManoel/Dart-Study/main/images/icons/voltar_ao_topo.png" height="32">
    </a>
</p>


***

<h2 id="dart_assincrono">Dart - programação assíncrona</h2>

O Dart é uma linguagem que permite a adição de recursos para execução assíncrona de tarefas. Dessa forma, podemos utilizá-lo tanto para a programação síncrona como assíncrona, além dos modelos de paralelismo e concorrência, que serão abordados adiante.

Para realizar a execução de processo assíncronos, o Dart utiliza uma combinação entre partes de **memoria reservada** do dispositivo e **threads** de processamento associadas e isoladas de modo a formar um **isolate**, uma pequena parcela da máquina destinada à execução de uma rotina específica.

<p align="right">
    <a href="#sumario">
        <img src="https://raw.githubusercontent.com/JosManoel/Dart-Study/main/images/icons/voltar_ao_topo.png" height="32">
    </a>
</p>


<h2 id="isolates">Isolates</h2>

Um **Isolate** funciona de maneira semelhante ao conceito de Web Workers no JavaScript, que utiliza **threads** de processamento separadas para executar scripts em segundo plano sem interferir na interface do usuário. De maneira resumida, uma **thread** pode ser definida como uma linha isolada de processamento destinada à execução de uma única tarefa, ocorrendo ao nível de núcleo do processador ( **Kernel-Level Thread** ), ou implementada por bibliotecas de uma determinada linguagem ( **User-Level Thread** ), que é o caso do Dart. 

Além disso, para a construção de um isolate também é reservado uma certa quantidade de memória, que será destinada à leitura e escrita de dados. Dessa forma, ao trabalhar com conjuntos isolados de **threads**, com um **loop de eventos** e memoria dedicados, o Dart previne a ocorrência de disputa por acesso à memória e conflitos de mutabilidade de dados, evitando alguns dos problemas clássicos dos métodos de execução assíncrona.

O Dart por padrão já possui uma **isolate** dedicada para o método **main()**, responsável por executar todo o código escrito e funções chamadas dentro dele em seu **loop de eventos**.

<h3 align="center">Isolates</h3>

<p align="center">
    <img src="https://i.imgur.com/9u8hnHI.png" width="600"> 
</p>

Entretanto, apesar apresentar funcionalidades bastante úteis, ao trabalhar com **isolates** o Dart restringe a comunicação entre os processos à utilização de uma API de troca de mensagens, além de requirir que um ambiente inteiro seja inicializado sempre que é necessário desenvolver alguma funcionalidade assíncrona, podendo possuir um consumo elevado de recursos em casos onde estamos trabalhando com grandes volumes de dados ou processos complexos. 

<p align="right">
    <a href="#sumario">
        <img src="https://raw.githubusercontent.com/JosManoel/Dart-Study/main/images/icons/voltar_ao_topo.png" height="32">
    </a>
</p>

<h2 id="event-loop">Loop de eventos</h2>

Como mensionado anteriormente, o **loop de eventos** é responsável por gerenciar a execução do código no **isolate**. Dentro de um **event-loop** a execução é exclusivamente linear e se estenderá até que todas as instruções sejam executadas. 

No processo de um **event-loop** são criadas duas estruturas denominadas **Microtask-queue** e **Event-queue** (ou **task-queue**), caracterizadas como listas do tipo [FIFO](https://pt.wikipedia.org/wiki/FIFO), onde o primeiro processo a entrar é o primeiro a ser executado. Naturalmente, a **Event-queue** é respossável pela maioria dos eventos recebidos, incluindo callbacks e mensagens de outros **isolates**, disparando uma ação de evento conforme são enviados. Já a **Microtask-queue** é destinada exclusivamente à eventos internos, possuindo uma prioridade de execução mais alta. Normalmente a **Microtask-queue** permanece vazia e é utilizada para executar recursos antes do próximo item da **Event-list**.

<p align="right">
    <a href="#sumario">
        <img src="https://raw.githubusercontent.com/JosManoel/Dart-Study/main/images/icons/voltar_ao_topo.png" height="32">
    </a>
</p>

***

<h2 id="funcoes">Criando funções assíncronas</h2>

No Dart os métodos assíncronos são implementados pela biblioteca **dart:async**, que pode retornar tanto um objeto do tipo [**Future**](https://dart.dev/guides/libraries/library-tour#future), como também um objeto do tipo [**Stream**](https://dart.dev/guides/libraries/library-tour#stream). Apesar de ambos possuírem funcionalidades semelhantes, temos algumas diferenças quanto a sua implementação, sendo o **Future** utilizado em situações onde é necessário informar que um determinado objeto retornará um valor no futuro. Já o **Stream** é normalmente empregado quando trabalhamos com programação reativa, que será abordada posteriormente em outro tópico.

Em ambos os casos, para a utilização da programação assíncrona, o Dart dispõe de algumas palavras-chave que indicam como determinados trechos de código devem ser tratados, sendo elas:

 * **Async** - Utilizada para determinar quando um método será assíncrono, informando que a execução do programa deve continuar enquanto o processo indicado não é finalizado.

 * **Await** - Empregada em casos onde a aplicação deve esperar o retorno de uma função assíncrona, bastante útil em casos em que uma determinada função depende do resultado de outra.

 * **Then** - O **then** é utilizado em situações onde desejamos executar uma ação após o termino da execução de alguma future.

> Apesar dos métodos assincronos serem implementados pela biblioteca **dart:async**, desde a versão 2.1 do Dart não é mais necessário importa-lá diretamente no código, visto que a biblioteca **dart:core** já exporta os elementos necessários. 

<p align="right">
    <a href="#sumario">
        <img src="https://raw.githubusercontent.com/JosManoel/Dart-Study/main/images/icons/voltar_ao_topo.png" height="32">
    </a>
</p>

<h2 id="future">Future</h2>

Assim como mencionado anteriormente, o **Future** é utilizado quando desejamos criar uma função assíncrona. Deste modo, ao criarmos um objeto do tipo **Future** devemos indicar na sua implementação, assim como a palavra-chave **async**, para indicar que este é um método assíncrono.

> Funções identificadas como **async** sempre retornarão objetos do tipo **Future**.

<h3 align="center">Funções assíncronas - sintaxe</h3>

~~~dart

Future<tipo_retorno> nome_funcao() async {
    //instrucoes
}

void main(){
    await nome_funcao();
}

~~~

> Caso seja necessário esperar o retorno de uma função assíncrona, devemos utilizar o **await** antes de seu chamado.

No Dart também temos uma segunda maneira de criar uma função assíncrona utilizando diretamente a [**API Future**](https://dart.dev/guides/libraries/library-tour#future). Nesta segunda sintaxe não temos a utilização da palavra-chave **Future** diretamente na função, ainda que todos os objetos sejam desse tipo. 

<h3 align="center">Funções assíncronas - API Future</h3>

~~~dart

void runUsingFuture() {
  // ...
  findEntryPoint().then((entryPoint) {
    return runExecutable(entryPoint, args);
  }).then(flushThenExit);
}

~~~

No exemplo utilizado pela documentação da API tempos o uso do método **then** para executar três funções assíncronas em sequência. Observe que, dependendo da complexidade da instrução, essa sintaxe pode se tornar de difícil assimilação, embora ainda esteja realizando ações simples. Esta mesma função poderia ser reescrita utilizando os métodos **async** e **await** da seguinte forma:

<h3 align="center">Funções assíncronas - Async/Await</h3>

~~~dart

Future<void> runUsingAsyncAwait() async {
  // ...
  var entryPoint = await findEntryPoint();
  var exitCode = await runExecutable(entryPoint, args);
  await flushThenExit(exitCode);
}

~~~


<h3 align="center">Future - Exemplo prático</h3>

~~~dart
class Mugiwara {
  late String name;
  late List<String> skills;
  
  Mugiwara(this.name, this.skills);
  void set setSkill(String skill) => skills.add(skill);
  
  void getSkills() => print("$name - Habilidades: $skills");
}

Future<void> timeSkip(Mugiwara mugiwara, String newSkill) async{  
  await Future.delayed(Duration(milliseconds: 4000));
  
  mugiwara.setSkill = newSkill;
}

void main() {
  Mugiwara franky = Mugiwara("Franky", ["Franky Centauros"]);
  
  timeSkip(franky, "Franky Shogun").then((value){
    print("${franky.name} saiu do TimeSkip!");
    franky.getSkills();
  });
  
  franky.getSkills();
  print("${franky.name} entrou em TimeSkip...");
}
  
~~~

<p align="center">
    <a href="https://dartpad.dev/?id=a1edd3b02c29d31aa68841b7a9f891bc">
        <img src="https://i.imgur.com/C09W0z3.png" height="24">
    </a>
</p>

> No exemplo acima temos o uso do método **delayed**, que cria um pequeno delay conforme a duração informada. Além disso, temos o uso do **then** para executar determinadas instruções após a conclusão do método timeSkip. Note que, apesar da mensagem de entrada do timeSkip está após a chamada do método, ela é mostrada primeiro na saída do console, uma vez que a função assíncrona ainda está em execução.

<p align="right">
    <a href="#sumario">
        <img src="https://raw.githubusercontent.com/JosManoel/Dart-Study/main/images/icons/voltar_ao_topo.png" height="32">
    </a>
</p>


<h2 id="excecoes">Funções assíncronas e exceções</h2>

Durante o desenvolvimento de aplicações reais é comum que as funções assíncronas sejam utilizadas para requisições em bancos de dados ou para lidar com pesquisas web. Ainda que desempenhe esta função adequadamente, o retorno desses métodos ainda está sujeito a possíveis erros, podendo resultar em quebras no sistema. Para evitar situações como essa a documentação do Dart aconselha a utilização do tratamento de exceções com o já conhecido [**Try... Catch**](https://github.com/JosManoel/Dart-Study/blob/main/topics/2-3_Tratando_excecoes.md).

A sintaxe de utilização a mesma utilizada para instruções convencionais, com o bloco **Catch** sendo o responsável por realizar o tratamento do erro. 


<h3 align="center">Tratamento de exceções com funções assíncronas - sintaxe</h3>

~~~dart

try {
    var assinc_resultado = await funcaoAssincrona();

} catch (e) {
    // Tratamento de erros
}

~~~

<p align="right">
    <a href="#sumario">
        <img src="https://raw.githubusercontent.com/JosManoel/Dart-Study/main/images/icons/voltar_ao_topo.png" height="32">
    </a>
</p>

***


<h2 id="leitura_e_link">📚 Leitura e links recomendados</h2>


* [📝 Dart - Documentação](https://dart.dev/guides/language/language-tour#generics)
* [🎯 Concorrência, Paralelismo, Processos, Threads, programação síncrona e assíncrona](https://www.treinaweb.com.br/blog/concorrencia-paralelismo-processos-threads-programacao-sincrona-e-assincrona/)
* [🎯 FIFO](https://pt.wikipedia.org/wiki/FIFO)
* [🎯 Thread](https://pt.wikipedia.org/wiki/Thread_(computa%C3%A7%C3%A3o))
* [🎯 Fundamentos de Dart/Flutter e sua natureza assíncrona: Isolates](https://medium.com/evoluum/fundamentos-de-dart-flutter-e-sua-natureza-ass%C3%ADncrona-parte-1-isolates-62ad32da28f9)
* [🎯 Fundamentos de Dart/Flutter e sua natureza assíncrona: Event-loop](https://medium.com/evoluum/fundamentos-de-dart-flutter-e-sua-natureza-ass%C3%ADncrona-parte-2-event-loop-b3a55d016790)
* [🎯 Como o Flutter é executado no Dart](https://medium.com/flutterando/como-o-flutter-%C3%A9-executado-no-dart-parte-3-6842322aa539)
* [🎯 Dart:Async - Future](https://dart.dev/guides/libraries/library-tour#future)
* [🎯 Como funciona o async-await e Future no Flutter](https://www.treinaweb.com.br/blog/como-funciona-o-async-await-e-future-no-flutter)
* [🎯 Flutter Descomplica — Funções Assíncronas](https://matheustech.medium.com/flutter-descomplica-funcoes-assincronas-ab5380d276dc)
* [🎯 Asynchronous programming: futures, async, await](https://dart.dev/codelabs/async-await)
* [🎯 Concurrency in Dart](https://dart.dev/guides/language/concurrency)
* [🎯 Multithreading in Flutter using Dart isolates](https://blog.logrocket.com/multithreading-flutter-using-dart-isolates/)
* [🎯 Video: Programação Assíncrona no Dart e Flutter](https://www.youtube.com/watch?v=G-SNZJ5Qpr0)
* [🎯 Video: Programação assíncrona vs Programação paralela](https://www.youtube.com/watch?v=zLfXPSeCkB8)
* [🎯 Video: Definição de thread, benefícios, exemplos e estados](https://www.youtube.com/watch?v=aRFKL7nSpts)


<p align="right">
    <a href="#sumario">
        <img src="https://raw.githubusercontent.com/JosManoel/Dart-Study/main/images/icons/voltar_ao_topo.png" height="32">
    </a>
</p>

***

<h2 id="licenca">🧾Licença</h2>

Este projeto está sob a licença [Apache 2.0](https://github.com/JosManoel/Dart-Study/blob/main/LICENSE).

<p align="right">
    <a href="#sumario">
        <img src="https://raw.githubusercontent.com/JosManoel/Dart-Study/main/images/icons/voltar_ao_topo.png" height="32">
    </a>
</p>
