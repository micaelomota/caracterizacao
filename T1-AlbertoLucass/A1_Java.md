# A1 - Java

+ **a) modelo de tradução (compilação, etc.?)**

Implementações Java geralmente usam um processo de compilação de duas etapas. O código-fonte Java é compilado para bytecode pelo compilador Java. O bytecode é executado por uma Java Virtual Machine (JVM). As JVMs modernas usam uma técnica chamada compilação Just-in-Time (JIT) para compilar o bytecode para instruções nativas compreendidas pela CPU do hardware em tempo de execução.

Algumas implementações de JVM podem escolher interpretar o bytecode em vez de JIT compilá-lo em código de máquina e executá-lo diretamente. Embora ainda seja considerado um "intérprete", é bastante diferente dos interpretadores que leem e executam o código-fonte de alto nível (ou seja, neste caso, o código-fonte Java não é interpretado diretamente, o bytecode, saída do compilador Java, é.) 

É tecnicamente possível compilar Java para código nativo com antecedência e executar o binário resultante. Também é possível interpretar o código Java diretamente.

Para resumir, dependendo do ambiente de execução, o bytecode pode ser:

* compilado com antecedência e executado como código nativo (semelhante à maioria dos compiladores C ++)
* compilado just-in-time e executado
* interpretado
* executado diretamente por um processador compatível (bytecode é o conjunto de instruções nativas de algumas CPUs)

![javaCompiler](https://user-images.githubusercontent.com/38790522/135185116-e90a7043-5241-4502-90ab-9b092084bc64.png)

O código escrito em Java é:

* Compilado primeiro para bytecode por um programa chamado javac, conforme mostrado na seção esquerda da imagem acima;
* Em seguida, conforme mostrado na seção direita da imagem acima, outro programa chamado java inicia o Java Runtime Environment e pode compilar e / ou interpretar o bytecode usando o Java Interpreter / JIT Compiler.

**Quando o java interpreta o bytecode e quando o compila?** O código do aplicativo é inicialmente interpretado, mas a JVM monitora quais sequências de bytecode são frequentemente executadas e as traduz em código de máquina para execução direta no hardware. Para bytecode que é executado apenas algumas vezes, isso economiza o tempo de compilação e reduz a latência inicial; para bytecode executado com frequência, a compilação JIT é usada para ser executada em alta velocidade, após uma fase inicial de interpretação lenta. Além disso, como um programa passa a maior parte do tempo executando uma minoria de seu código, o tempo de compilação reduzido é significativo. Finalmente, durante a interpretação inicial do código, as estatísticas de execução podem ser coletadas antes da compilação, o que ajuda a realizar uma otimização melhor.

+ **b) nomes, variáveis e vinculação**

Tipo de Identificador | Regras para Nomenclatura | 	Exemplos
:---------: | :------: | :-------:
Pacotes | O prefixo de um nome de pacote exclusivo é sempre escrito em letras ASCII minúsculas e deve ser um dos nomes de domínio de nível superior, atualmente com, edu, gov, mil, net, org ou um dos códigos de duas letras em inglês identificação de países conforme especificado no padrão ISO 3166, 1981. Os componentes subsequentes do nome do pacote variam de acordo com as convenções de nomenclatura internas da própria organização. Essas convenções podem especificar que certos componentes de nome de diretório sejam nomes de divisão, departamento, projeto, máquina ou login. | com.sun.eng com.apple.quicktime.v2 edu.cmu.cs.bovik.cheese
Classes | Os nomes das classes devem ser substantivos, em maiúsculas e minúsculas com a primeira letra de cada palavra interna. Tente manter os nomes das classes simples e descritivos. Use palavras inteiras - evite acrônimos e abreviações (a menos que a abreviatura seja muito mais usada do que a forma longa, como URL ou HTML). | class Raster; <br />class ImageSprite;
Interfaces | Os nomes das interfaces devem ser escritos em maiúscula como os nomes das classes. | 	interface RasterDelegate; interface Storing;
Métodos | 	Os métodos devem ser verbos, em maiúsculas e minúsculas, com a primeira letra minúscula e a primeira letra de cada palavra interna maiúscula. | corre();<br />corraRapido();<br />getBackground ();
Variáveis | Exceto para variáveis, todas as constantes de instância, classe e classe estão em maiúsculas e minúsculas com uma primeira letra minúscula. Palavras internas começam com letras maiúsculas. Nomes de variáveis ​​não devem começar com caracteres de sublinhado _ ou cifrão $, embora ambos sejam permitidos. Os nomes das variáveis ​​devem ser curtos, mas significativos. A escolha de um nome de variável deve ser mnemônica - isto é, projetada para indicar ao observador casual a intenção de seu uso. Nomes de variáveis ​​de um caractere devem ser evitados, exceto para variáveis ​​temporárias "descartáveis". Os nomes comuns para variáveis temporárias são i, j, k, m, e npara inteiros; c, de epara personagens. | int i;<br />char c;<br />float myWidth;
Constantes | Os nomes das variáveis ​​declaradas como constantes de classe e de constantes ANSI devem ser todos maiúsculos com palavras separadas por sublinhados ("_"). (As constantes ANSI devem ser evitadas para facilitar a depuração.) | static final int MIN_WIDTH = 4;<br />static final int MAX_WIDTH = 999;<br />static final int GET_THE_CPU = 1;







+ **c) escopo, tempo de vida e ambientes de referência.**

Em Java, o escopo define onde uma determinada variável ou método está acessível em um programa. As variáveis ​​podem ser definidas como tendo um dos três tipos de escopo:

* Escopo de nível de classe (variáveis ​​de instância): qualquer variável declarada dentro de uma classe é acessível por todos os métodos dessa classe. Dependendo de seu modificador de acesso (ou seja, publico ou privado), às vezes pode ser acessado fora da classe.

* Escopo no nível do método (variáveis ​​locais): qualquer variável declarada dentro de um método, argumentos incluídos, NÃO é acessível fora desse método.

* Escopo do bloco (variáveis ​​de loop): qualquer variável declarada em uma forcondição de loop não é acessível após o loop, a menos que você tenha definido de antemão.


Tipo de Variável | Escopo | Tempo de Vida
:---------: | :------: | :-------:
Variáveis ​​de instância | Por toda a classe, exceto nos métodos estáticos | Até o objeto estiver disponível na memória
Variáveis ​​de classe | Por toda a classe | Até a finalização do programa
Variáveis ​​Locais | Dentro do bloco no qual é declarada | Até que o controle saia do bloco em que foi declarado





## Referências

https://stackoverflow.com/questions/1326071/is-java-a-compiled-or-an-interpreted-programming-language

https://www.oracle.com/java/technologies/javase/codeconventions-namingconventions.html

https://www.codecademy.com/articles/variable-scope-in-java

https://www.learningjournal.guru/article/programming-in-java/scope-and-lifetime-of-a-variable/
