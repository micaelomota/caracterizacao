<!-- Caracterização da Linguagem L1 - Java - Álvaro Souza Oliveira -->

# Linguagem 1 - Java

## Modelo de tradução

<body style="text-align: justify">
    <p >
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

## Escopo, tempo de vida e ambientes de referência.
