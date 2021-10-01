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



