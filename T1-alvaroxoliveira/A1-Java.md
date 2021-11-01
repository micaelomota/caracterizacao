<!-- Caracterização da Linguagem L1 - Java - Álvaro Souza Oliveira -->

# Linguagem 1 - Java

## Modelo de tradução

<body style="text-align: justify">
    <p>
    Java é uma linguagem multi-paradigma e também de multi-plataforma, que tem sua compilação em duas etapas, as quais envolvem primeiro por meio de um compilador idependente do Sistema Operacional e na segunda compilação, tudo ocorre por meio da usa tão poderosa Máquina Virtual Java ou Java Virtual Machine, ou, para os íntimos, JVM, que é preparada justamente para cada tipo de Sistema Operacional que suporta seu código, que, conhecidamente é uma lista muito vasta.
    </p>
    <p>
    Em Java, os programas não são compilados diretamente em arquivos executáveis, em vez disso, são compilados em <b>bytecode</b>, que a JVM (Java Virtual Machine) executa em tempo de execução. Cada vez que um programa for executado, o bytecode é convertido usando o compilador Just-In-Time (JIT). Isso resulta em um código de máquina que é alimentado na memória e assim, é executado.
    </p>
    </p>
    <p>
    Um código escrito na linguagem Java precisa ser compilado em duas etapas:
        <ol>
            <li>Primeiramente, precisam ser compilados para o bytecode</li>
            <li>Em segundo, quando o bytecode é executado, através do JIT ele é convertido para Machine-code (Código de Máquina)</li>
        </ol>
    </p>
    <p>
    Em intermédio entre a primeira e a segunda compilações, ao converter o código-fonte em bytecode, o compilador segue as seguintes etapas de forma cronológica:
        <ul>
            <li><b>Etapa de Análise</b>: Lê os arquivos de origem <code>.java</code> e faz o mapeamento da sequência de tokens resultante em nós de uma AST <b>Árvore Sintática Abstrata (Abstract Sintax Tree).</b></li>
            <li><b>Enter</b>: Insere elementos para as suas definições na tabela de símbolos.</li>
            <li><b>Anotações de Processos</b>: Processa as anotações encontradas nas unitdades de compilação especificadas.</li>
            <li><b>Atribuição</b>: Atribui as árvores de sintaxe. Esta etapa inclui resolução de nome, verificação de tipo e dobra constante</li>
            <li><b>Fluxo/Flow</b>: Executa a análise de fluxo da etapa anterior, incluindo as verificações de atribuições e também os acessos.</li>
            <li><b>Desugar</b> Reescreve as AST e traduz o que se chama de <i>Sintatic Sugar</i>.</li>
            <li><b>Geração</b>: Gera os arquivos do tipo <code>.Class</code></li>    
        </ul>
    </p>
</body>

### Execução
<body style="text-align: justify">
    <p>
        Os arquivos de clase gerados, como falados anteriormente independem do tipo de Máquina (Hardware) ou mesmo do tipo de Sistema Operacional, o que torna Java uma linguagem muito versátil permitindo que um código escrito na linguagem seja executado em praticamente qualquer sistema. 
    </p>
    <p>
        Para executar, é passado para a JVM o arquivo de classe principal, aquele que contém o método main do programa, e em seguida, se passa por três etapas principais, antes que seja executado o código de máquina final. A seguir, listamos estas etapas:
        <ul>
            <li><b>Class Loader</b>: A classe principal é carregada na memória passando o seu arquivo <code>.class</code> e chamando a JVM, e assim, todas as outras classes referencidas também são carregadas. Existem dois carregadores de classes principais que são os primordiais e os não primordiais. Os primordiais está integrado na JVM e é o padrão utilizado normalmente. O não-primordial é um carregador definido pelo programador, que tem a finalidade de fazer o mesmo processo mas de forma personalizada</li>
            <li><b>Verificador de Bytecode</b>: Após o bytecode ser carregado pelo carregador de classe, da etapa anterior, se deve ser inspecionado pelo verificador de bytecode para varredura e verificação das instruções e evitar que haja ações prejudiciais. </li>
            <li><b>Compilador Just-In-Time(JIT)</b>: Basicamente, seu trabalho é converter o bytecode que foi gerado e verificado em código de máquina. Assim o hardware pode executar código nativo e por conta do JIT, se ganha bastante performance em termos de velocidade de execução.</li>
        </ul>
    </p>
</body>

## Nomes, variáveis e vinculação

### Nomes

<body style="text-align: justify">
    <p>
      Em questão de nomes, no Java temos uma certa convenção para escrita de código. Essas convenções são bastante importantes do ponto de vista de organização, para que o código se mantenha legível e de fácil e rápida manutenção, afinal, em um projeto grande, não só um, como vários programadores irão participar, como dezenas e até mesmo centenas. Assim, para que nenhum programador tenha que adivinhar o que é uma classe ou até mesmo uma constante, em linguagens de programação, por muita influência de suas comunidades e outros fatores, essas convenções são adotadas para manter o código em um padrão para que todos entendam o código e possam também colocar a mão na massa, e no Java não poderia ser diferente.
    </p>
    <p>
      Em java, algumas convenções importantes são adotadas. Elas são listadas a seguir:
      <li><b>Pacotes/Packages</b>: Os nomes dos pacotes devem estar em letra minúscula. Em projetos pequenos, normalmente têm nomes simples, mas em projetos de grandes empresas, normalmente têm nomes mais complexos e subdividos com "." de acordo com o domínio da empresa. Um exemplo pode ser visto a seguir.</li>
      <div align=center><code> package br.minha.empresa; </code></div>
      <li><b>Classes/Class</b>: Classes são nomeadas começando sempre com palavras (normalmente substantivos, pois normalgeralmente representam objetos do mundo real) iniciando com letras maiúsculas a primeira letra de cada palavra. Tentar manter sempre nomes inteiros das palavras e também com boa descrição.</li>
      <div align=center><code> Class Bola {} </code></div>
      <li><b>Interfaces</b>: São nomeadas da mesma forma que se nomeiam as classes</li>
      <div align=center><code> interface iBola </code></div>
      <li><b>Métodos</b>: Devem ser verbos, com a primeira palavra iniciada e mantida com letras minúsculas e com as palavras internas iniciadas com letras maiúsculas.</li>
      <div align=center><code> public void chutarBola(); </code></div>
      <li><b>Variáveis</b>: Como os métodos, devem ser escritas em letras minúsculas e com exceção da primeira palavra, as internas devem começar com letras maiúsculas</li>
      <div align=center><code> int tamanhoDaBola</code></div>
      <li><b>Constantes</b>: As constantes devem ser palavras em upper case, ou seja, toda em maiúsculas, com divisão de palavra com o caractere underline "_"</li>
      <div align=center><code> final static int MAX_TAMANHO_BOLA = 4; </code></div>
    </p>
</body>

### Variáveis

<body style="text-align: justify">
    <p>
      Na linguagem Java, usamos três tipos de variáveis:
    </p>
    <p>
      <ol>
        <li><b>Variáveis de Classe</b>: São variáveis que pertencem a classe, assim todos os objetos tem acesso a elas, contendo o mesmo valor. São declaradas com o uso da palavra reservada <code>static</code>.</li>
        <li><b>Variáveis de instância</b>: São normalmente às mais usadas, pois estão declaradas dentro das classes, normalmente encapsuladas, tendo seus valores acessados por meio de getters e setters.</li>
        <li><b>Variáveis Locais</b>: São variáveis que estão presente dentro de blocos ou subprogramas, normalmente dentro dos métodos e não visíveis para escopos mais gerais, apenas para o escopo do próbrio subprograma em que foram declaradas.</li>
      </ol>
    </p>
</body>

### Vinculação (Binding)

<body style="text-align: justify">
    <p>
      Temos dois tipos de vinculação na linguagem Java:
      <div align=center>Vinculação Estática x Vinculação Dinâmica</div>
    </p>
    <p>
      <ul>
        <li><b>Vinculação Estática</b>: Temos esse tipo de vinculação quando a variável é determinada pelo compilador antes do programa ser executado, ou seja, em tempo de compilação. Temos este tipo de vinculação quando há algum método <code>private</code>, <code>static</code> ou <code>final</code>.</li>
        <li><b>Vinculação Dinâmica</b>: Temos esse tipo de vinculação quando a variável é determinada em tempo de execução. Ocorre em situações de código mais livre de encapsulamento, tornando o código mais versátil.</li>
      </ul>
    </p>
</body>

## Escopo, tempo de vida e ambientes de referência.

### Escopo e tempo de vida

<body style="text-align: justify">
    <p>
      Cada tipo de variável tem seu tipo de escopo e tempo de vida específico:
    </p>
    <p>
      <ol>
        <li><b>Variáveis de Classe</b>: Declarada dentro de uma classe, fora de todos os blocos, conhecida também como variável estática. Seu tempo de vida vai do inicio do programa até o final da sua execução.</li>
        <li><b>Variáveis de instância</b>: Seu escopo é definido dentro de uma classe, mas declarada fora de todos os blocos e subprogramas, conhecida como instância. Seu tempo de vida vai desde quando foi declarada até que o objeto instanciado seja removido da memória.</li>
        <li><b>Variáveis Locais</b>: Seu escopo é definido dentro de um bloco ou subprograma. Seu tempo de vida finaliza quando o bloco ou subprograma seja finalizado. Exemplo é quando um método execute todas as suas instruções.</li>
      </ol>
    </p>
</body>

### Ambientes de Referência

<body style="text-align: justify">
    <p>
      A linguagem Java é dita de escopo estático e apesar de ter recursos os quais podemos fazer vinculações dinâmicas, suas variáveis são referenciadas dentro de um ambiente estático.
    </p>
</body>

## Estruturas de controle a nível de Instrução

<body style="text-align: justify">
    <p>
      O compilador Java executa o código de cima para baixo. As instruções no código são executadas de acordo com a ordem em que aparecem. No entanto, o Java fornece instruções que podem ser usadas para fazer o controle o fluxo em códigos escritos na linguagem. Essas são chamadas de instruções de fluxo de controle. É um dos recursos fundamentais do Java e também de outras linguagens de programação, que fornece um bom fluxo de programa.
    </p>
    <p>
      O java Fornece três tipos de instruções de fluxo de controle, as quais são:
    </p>
    <ol>
      <li>
        Declarações de tomada de decisão.
        <ul>
          <li>
            Declarações do tipo <code>if/else if/else</code>.
          </li>
          <li>
            Declarações do tipo <code>switch/case</code>.
          </li>
        </ul>
      </li>
      <li>
        Instruções de repetição:
        <ul>
          <li>
            Repetições do tipo <code>for</code>. 
          </li>
          <li>
            Repetições do tipo <code>for-each</code>. 
          </li>
          <li>
            Repetições do tipo <code>while</code>. 
          </li>
          <li>
            Repetições do tipo <code>do-while</code>. 
          </li>
        </ul>
      </li>
      <li>
        Declarações de salto (jump).
        <ul>
          <li>
            Declarações do tipo <code>break</code>;
          </li>
          <li>
            Declarações do tipo <code>continue</code>.
          </li>
        </ul>
      </li>
    </ol>
    <p>
      Em Java uma instrução do tipo if é chamada de condicional, ou seja, seu uso é para avaliar expressões lógicas. Essa expressão lógica retorna verdadeiro ou falso e com isso há o desvio de fluxo dependendo do resultado da expressão. Existem quatro tipos dessas expressões:
      <ol>
        <li>
          Declaração <code>if</code> simples, na qual o <code>if</code> recebe uma expressão entre parenteses e caso a expressão seja verdadeira ele executa um bloco de código que é declarado logo após os parênteses.
        </li>
        <li>
          Declaração <code>if/else</code>, na qual existe um <code>else</code> logo após o <code>if</code> que executará um bloco de código caso a expressão que o <code>if</code> testou seja falsa.
        </li>
        <li>
          Declaração <code>if/else-if</code>, na qual existem várias condições aninhadas, as quais existe primeiramente um <code>if</code> e logo após condições <code>else if</code> também recebendo outras expressões entre parênteses e executando blocos de código para cada uma dessas outras expressões booleanas e podendo serem terminadas com <code>else</code> caso todas as outras expressões anteriores forem falsas.
        </li>
        <li>
          Declaração <code>if</code> aninhada é basicamente um conjunto de expressões <code>if</code>, na qual existe um <code>if</code> que contem dentro do seu bloco de código outros <code>if</code> ou <code>if-else</code> aninhados.
        </li>
      </ol>
    </p>
    <p>
      Em Java as instruções do tipo switch são super parecidas com às instruções do tipo if-else-if. Essas instruções contém vários blocos de código chamados cases, e um único case é executado com base na variável que está sendo alternada. A instrução switch tem uma certa vantagem em ser usada ao invés dos if's aninhados por conta da legibilidade que entrega.
    </p>
    <p>
      Pontos que devem ser levados em consideração ao usar switch:
    </p>
    <ul>
      <li>
        As condições de case podem ser de tipos primitivos ou enumaration e também, a partir do Java 7 podem ser usadas as Strings.
      </li>
      <li>
        Cases não podem ser duplicados.
      </li>
      <li>
        A instrução default é chamada quando nenhum dos casos corresponde à condição, semelhanto ao else e também é opcional.
      </li>
      <li>
        A instrução break finaliza um bloco de código quando a condição é satisfeita. Também é opcional e o próximo caso é executado.
      </li>
      <li>
        Obviamente ao usar esse tipo de estrutura, a condição case deve ser do mesmo tipo que a váriável usada na expressão switch.
      </li>
    </ul>
    <p>
      Falando agora sobre loop, no Java precisamos também considerar casos onde precisamos executar certos blocos de código mais de uma vez, então usamos estruturas de controle que chamamos de estruturas de repetição. Para executar esses loops, precisamos também de certas condições, para que haja uma entrada nessas repetições e também para que haja uma parada, pois um loop infinito nunca é um caso desejado para os programadores.
    </p>
    <p>
      Em java temos três tipos de loops que são executados de forma bastante semelhante, apesar da sintaxe de cada um se diferenciar um do outro. Essas formas são:
    </p>
    <ul>
      <li>
        O loop for.
      </li>
      <li>
        O loop for-each.
      </li>
      <li>
        O loop while.
      </li>
      <li>
        O loop do-while.
      </li>
    </ul>
    <p>
      O loop for é utilizado quando se há um loop controlado de certa forma que conhecemos o ponto de entrada no loop e o ponto de parada, ou seja, conhecemos quando vamos entrar e quando vamos sair do código. Este loop tem a sintaxe do tipo:
      <code>for(condicaoDeInicio; condicaoDeParada; controleIncrementoOuDecremento) {// bloco de código associado.}</code>
    </p>
    <p>
      O loop for-each é utilizado quando se deeja um loop iterável para atravessar estruturas de dados mais complexas como arrays ou collections. Neste tipo de loop não há necessidade de haver uma variável iteirável para ser um contador de loop para ser atualizada. O for-each então chega na estrura e executa seu bloco de código para cada um dos elementos dessas estruturas e fornece com isso uma segurança de que não irá dar erro por conta de alguma variável tentando ser acessada mas que na verdade não existe.
      <code>for(TipoDaEsrutura elemento: nomeDaEsrutura){// bloco de código associado.}</code>
    </p>
    <p>
      No loop While, as instruções são repetidas várias vezes, sem haver um controle tão rigoroso com nos loops anteriores. Esses loops são ideais quando não se sabe exatamente quantas iterações deverão ter para satisfazer as condições. Este loop ele carrega também uma expressão booleana que quando não satisfeita o loop para. Então também caso não seja tão rigorosamente controlado poderá gerar erros. A sintaxe é a seguinte:
      <code>while(condicao){// bloco de código associado.}</code>
    </p>
    <p>
      No loop do-While, é semelhante filosoficamente com o anterior, porem o bloco de código é executado pelo menos uma vez para depois verificar a condição. Ou seja, é para ser executado quando a quantidade de execuções não é definida e precisamos executar o bloco de código pelo menos uma vez. A sintaxe é a seguinte:
      <code>do{// bloco de código associado.} while(condicao);</code>
    </p>
    <p>
      Por fim, temos as declarações de Jump (saltos) que são usadas para transferir controle do programa para instruções específicas. Essas instruções basicamente transferem o controle e fluxo para outras partes do programa e existem duas delas bem conhecidas na linguagem Java que são:
    </p>
    <ul>
      <li>
        O salto break.
      </li>
      <li>
        O salto continue.
      </li>
    </ul>
    <p>
      O break basicamente serve para parar a execução de um fluxo atual e transferir o controle para uma próxima instrução que está fora daquele contexto ou bloco que está inserido, sempre dentro de uma estrutura switch ou mesmo dentro de uma das estruturas de repetição.
    </p>
    <p>
      O salto continue ao contrário do break, não desvia a instrução para fora da estrutura de repetição ou switch, ele apenas interrompe aquela parte específica e pula para a próxima iteração de forma imediata.
    </p>

</body>

