
# Atividade 1 – Java 
## Modelo de tradução
Um programa Java é primeiro compilado para uma versão binária dos bytecodes Java, após isso é executado no interpretador Java Virtual Machine (JVM). A JVM por sua vez link-edita os métodos desejados na biblioteca Java enquanto o programa está sendo executado, para conseguir um melhor desempenho, a JVM chama o compilador Just-In-Time (JIT), que compila métodos seletivamente para a linguagem nativa da máquina em que está executando. Detalhando melhor:
### Compilação
O arquivo '.java' é passado para o compilador. Este será convertido em um código-fonte (bytecode). Após isso o compilador executa os seguintes passos:

Parse: Lê um conjunto de arquivos de origem * .java e mapeia a sequência de tokens resultante em nós AST (Abstract Syntax Tree).

Enter : Insere símbolos para as definições na tabela de símbolos.

Process annotations: Se solicitado, processa as anotações encontradas nas unidades de compilação especificadas.

Attribute: Atribui as árvores de sintaxe. Esta etapa inclui resolução de nome, verificação de tipo e constant folding.

Flow : Analisa o fluxo de dados nas árvores, realizando verificação de atributos e também acessibilidade.

Desugar : Reescreve as AST e traduz algum Sintatic Sugar

Generate: São gerados arquivos '.Class'.

### Execução
Os arquivos de classe gerados pelo compilador são independentes da máquina ou do sistema operacional, o que permite que sejam executados em qualquer sistema. Para executar, o arquivo de classe principal (a classe que contém o método main) é passado para a JVM e, em seguida, passa por três estágios principais antes que o código de máquina final seja executado. Essas etapas são:

**Class Loader**

A classe principal é carregada na memória passando seu arquivo ‘.class’ para a JVM, chamando a última. Todas as outras classes referenciadas no programa são carregadas por meio do carregador de classes. 
Existem dois tipos de carregadores de classes: primordial e não primordial. O carregador de classes primordial está integrado em todas as JVMs e é o carregador de classes padrão. Um carregador de classes não primordial é um carregador de classes definido pelo usuário, que pode ser codificado para personalizar o processo de carregamento de classes. O carregador de classes não primordial, se definido, é preferível ao padrão, para carregar classes.

**Bytecode Verifier**

Depois que o bytecode de uma classe é carregado pelo carregador de classe, ele deve ser inspecionado pelo verificador de bytecode, cujo trabalho é verificar se as instruções não executam ações prejudiciais. A seguir estão algumas das verificações realizadas:

As variáveis são inicializadas antes de serem usadas.

As chamadas de método correspondem aos tipos de referências de objeto.

As regras para acessar dados e métodos privados não são violadas.

Os acessos de variáveis locais se enquadram na pilha de tempo de execução.

A pilha de tempo de execução não transborda.

Se alguma das verificações acima falhar, o verificador não permitirá que a classe seja carregada.

**Just-In-Time Compiler**

Este é o estágio final encontrado pelo programa java e seu trabalho é converter o bytecode carregado em código de máquina. Ao usar um compilador JIT, o hardware pode executar o código nativo, ao contrário de ter o JVM interpretando a mesma sequência de bytecode repetidamente e incorrendo na penalidade de um processo de tradução relativamente longo. Isso pode levar a ganhos de desempenho na velocidade de execução, a menos que os métodos sejam executados com menos frequência.

## Nomes, variáveis e vinculação

### Nomes

As convenções de nomenclatura padrão do Java, você facilita a leitura do código. A legibilidade do programa Java é muito importante. Isso indica que menos tempo é gasto para descobrir o que o código faz.

As principais regras que devem ser seguidas por todos os identificadores:

  o	O nome não deve conter espaços em branco.

  o	O nome não deve começar com caracteres especiais como & (e comercial), $ (dólar), _ (sublinhado).

**Classe**

  o	Deve começar com a letra maiúscula.
  
  o	Deve ser um substantivo como Cor, Botão, Sistema, Tópico, etc.
  
  o	Use palavras apropriadas, em vez de siglas.
  
**Interface**

  o	Deve começar com a letra maiúscula.
  
  o	Deve ser um adjetivo como Runnable, Remote, ActionListener.
  
  o	Use palavras apropriadas, em vez de siglas.
  
**Método**

  o	Deve começar com letra minúscula.
  
  o	Deve ser um verbo como main(), print(), println().
  
  o	Se o nome contiver várias palavras, inicie-o com uma letra minúscula seguida por uma letra maiúscula, como actionPerformed().
  
**Variável**

  o	Ele deve começar com uma letra minúscula, como id, nome.
  
  o	Não deve começar com caracteres especiais como & (e comercial), $ (dólar), _ (sublinhado).
  
  o	Se o nome contiver várias palavras, inicie-o com a letra minúscula seguida por uma letra maiúscula como firstName, lastName.
  
  o	Evite usar variáveis de um caractere, como x, y, z.
  
**Pacote**

  o	Deve ser uma letra minúscula, como java, lang.
  
  o	Se o nome contiver várias palavras, ele deverá ser separado por pontos (.) Como java.util, java.lang
  
**Constante**

  o	Deve estar em letras maiúsculas, como VERMELHO, AMARELO.
  
  o	Se o nome contiver várias palavras, ele deverá ser separado por um sublinhado (_), como MAX_PRIORITY.
  
  o	Pode conter dígitos, mas não como a primeira letra.
  
**CamelCase em convenções de nomenclatura java**

Java segue a sintaxe camelCase para nomear a classe, interface, método e variável.
Se o nome for combinado com duas palavras, a segunda palavra começará com letras maiúsculas sempre como actionPerformed(), firstName, ActionEvent, ActionListener, etc.

### Variáveis

Em Java as variáveis são:

**Variável de instância**

Variável cujo valor é específico ao objeto e não à classe. Uma variável de instância em geral possui uma valor diferente em cada objeto representante da classe.

**Variável de classe**

Uma variável cujo valor é comum a todos os objetos representantes da classe. Mudar o valor de uma variável de classe em um objeto automaticamente muda o valor para todos os objetos instâncias da mesma classe. Um exemplo óbvio de uma variável de classe seria o número de instâncias desta classe que já foram criadas.

Uma variável é considerada como de instância por "default". Para declarar uma variável de classe, acrescenta-se a palavra-chave static.

**Variáveis globais** 

São declaradas fora de qualquer método (usualmente no cabeçalho da classe) e são acessíveis por qualquer método da classe

**Variáveis locais**

São declaradas dentro de um determinado método, ou até dentro de um bloco.

**Variáveis constantes**

Refere-se a variáveis cujo valor não pode mudar durante a execução do programa. Tais variáveis são caracterizadas pela palavra-chave final, e por convenção recebem usualmente nomes escritos inteiramente em maiúsculas.

 **Tipos de variáveis**

O Java é uma linguagem fortemente tipada, ou seja, é obrigatório que toda variável tenha um tipo definido na sua declaração.

Os tipos de dados/variáveis primitivas no Java são: byte, short, char, int, long, float, double e boolean.

### Vinculação

Em Java, a vinculação é a conexão entre uma chamada de função ao corpo do método. Existem dois tipos de vinculação: vinculação estática e dinâmica. Quando a ligação acontece durante em tempo de compilação, chama-se estático. Quando a ligação acontece durante run-time, chama-se dinâmico.

**Vinculação estática**

Geralmente, os métodos que são estáticos, privados e finais são vinculativos estáticos. Isso ocorre porque a substituição de método não é possível para esses métodos. Portanto, o compilador sabe qual método de classe chamar durante o próprio tempo de compilação.

**Vinculação dinâmica**

Ocorre principalmente na substituição de métodos. Na substituição de métodos, a superclasse e as subclasses têm o mesmo nome de método. Com base no tipo de objeto, que é determinado em tempo de execução, ele chama o método de classe correspondente durante o processo de vinculação.

 **Diferença entre vinculação estática e dinâmica**
 Vinculação estática | Vinculação Dinâmica
 ------------------- | -------------------
Também chamado de vinculação inicial ou vinculação em tempo de compilação	| Também chamado de late binding ou runtime binding
A sobrecarga de método é uma ligação estática | Substituição de método é vinculação dinâmica
Usa tipo de classe para resolver a ligação | Usa o tipo de objeto para resolver a ligação
Execução mais rápida | Execução lenta

## Escopo, tempo de vida e ambientes de referência


 **Variáveis locais** 
 
 Escopo: No bloco onde foi declarada
 
 Tempo de vida: Até o fim do bloco

 **Variáveis de instância** 
 
 Escopo: Por toda classe, exceto nos métodos estáticos
 
 Tempo de vida: Até que o lixo do objeto seja coletado
 
 **Variáveis de classe** 
 
 Escopo: Por toda classe
 
 Tempo de vida: Até o final do programa
 
 







