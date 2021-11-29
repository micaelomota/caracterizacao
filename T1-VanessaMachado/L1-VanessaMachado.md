# Trabalho 1 : Versão Final L1 <h1>
##### Autoria: Vanessa Machado Araújo <h5>

### Linguagem de Programação : JAVA <h3>


* [HISTÓRICO E APRESENTAÇÃO](#histórico-e-apresentação)
* [CARACTERÍSTICAS DA LINGUAGEM](#características-da-linguagem)
* [CAPACIDADES DA LINGUAGEM](#capacidades-da-linguagem)
* [PRODUTIVIDADE DO DESENVOLVEDOR](#produtividade-do-desenvolvedor)
* [ECOSSISTEMA](#ecossistema)
* [INFORMAÇÕES ADICIONAIS](#informações-adicionais)
  

## HISTÓRICO E APRESENTAÇÃO 
<div style="text-align: justify"> 
    <p>
        Origem e descendência da linguagem JAVA:
    </p>

![Evolução da linguagem JAVA, contendo pais e filhos:](https://github.com/NessaMd/caracterizacao/blob/main/T1-VanessaMachado/evolu%C3%A7%C3%A3oJava.jpg)   
    <p>
        Java é uma linguagem de programação orientada a objetos.Começou a ser desenvolvida em 1991, na Sun Microsystems. Teve inicio com o Green Project, no qual os mentores foram Patrick Naughton, Mike Sheridan, e James Gosling. Este projeto, inicialmente, não tinha intenção de criar uma linguagem de programação, mais sim de antecipar a “próxima onda” que aconteceria na área da informática e programação.
    </p>
    <p>
        Nesta época, a internet estava ficando cada vez mais popular, e a equipe do Green Project começou a pensar em aplicações para o Oak na internet, onde a palavra chave é interação. Eles conseguiram adaptar a linguagem Oak para a internet, e em 1995 foi lançado o Java, que era uma versão atualizada do Oak para a internet.
    </p>
    <p>
        Java é uma linguagem de programação expressamente projetada para uso no ambiente distribuído da Internet. Ele foi projetado para ter a “aparência e comportamento” da linguagem de programação C ++ , mas é mais simples de usar e impõe um modelo de programação orientado a objetos .
     </p>
     <p>
        Foi testado, refinado, estendido e comprovado por uma comunidade dedicada de desenvolvedores, arquitetos e entusiastas de Java. Apesar de suas origens remontar a quase duas décadas, Java tem evoluído de forma consistente ao longo dos anos. Mesmo entre a ascensão de linguagens rivais,permanece popular entre as empresas. 
    </p>
</div>

## CARACTERÍSTICAS DA LINGUAGEM 

### PARADIGMA <h3>
<div style="text-align: justify">
    <p>
        Java  é uma linguagem de programação orientada a objetos (OPP), um dos modelos mais populares do mundo. Tudo o que é desenvolvido dentro dela faz a utilização de classes e objetos.
    </p>
    <p>
        O papel dessas classes é atuar como modelo para que sejam criados diversos objetos, nos quais serão utilizados atributos e métodos fornecidos pela classe. Assim, são desenvolvidas coleções de objetos com estrutura e comportamentos próprios.
    </p>
</div>

### SISTEMA DE TIPAGEM <h3>
<div style="text-align: justify">
    <p>
        A linguagem java utiliza a tipagem estática, o que a torna fortemente tipada, ao usar variáveis com tipos específicos. Nesse sentido, há uma verificação dos tipos usados em dados e variáveis e isso não permite que haja alteração do tipo da variável após essa ser declarada. Isso dá uma maior seguraça ao códico.
    </p>
</div>

### MODELO DE TRADUÇÃO <h3>
<div style="text-align: justify">
    <p>  
    Java, por ser uma linguagem de programação que independe de plataforma, não irá funcionar na compilação em apenas uma etapa. Envolve uma execução em duas etapas: a primeira, por meio de um compilador, o qual é independente do sistema operacional; e uma segunda, em uma JVM (Máquina virtual), onde cada Sistema Operacional tem sua própria customizada. A seguir, as duas etapas:
    </p>
</div>

#### COMPILAÇÃO:  <h4>
<div style="text-align: justify">
    <p> 
        Primeiramente, o arquivo principal '.java' é passado para o compilador. Este será convertido em um código-fonte (bytecode). Ao realizar essa conversão, o compilador segue seis passos.
    </p> 
    <p> <b>Passos:</b> </p> 
        <b>Análise :</b> Lê o arquivo principal '.java' e mapeia a sequência de tokens resultante da árvore sintática;<br>
        <b>Enter :</b> insere símbolos, para as definições, na tabela de símbolos;<br>
        <b>Anotações do processo :</b> Caso seja solicitado, processa as anotações encontradas nas unidades de compilação em questão;<br>
        <b>Fluxo :</b> Analisa o fluxo de dados nas árvores, realizando verificação de atributos e também acessibilidade;<br>
        <b>Desugar :</b> Reescreve a árvore sintática;<br>
        <b>Geração :</b> São gerados arquivos '.Class';<br>
    </p>
</div>

#### EXECUÇÃO:  <h4>
<div style="text-align: justify">
    <p> 
        O arquivo '.Class' gerado na etapa anterior é passado para a JVM e, em seguida, transcorre por três estágios antes que o código final de máquina seja finalmente executado.
    </p> 
    <p> <b>A saber:</b> </p> 
        <b>Class Loader (Carregador de classe) :</b> Classe principal é carregada na memória passando seu arquivo '.class' para a JVM;<br>
        <b>Bytecode Verifier (Verificador de Bytecode) :</b> Depois que o bytecode de uma classe é carregado na etapa anterior, este deverá ser agora inspecionado, afim de verificar se as instruções não executam ações prejudiciais;<br>
        <b>Just-In-Time Compiler (Compilador Just-In-Time) :</b> Este é o estágio final encontrado pelo programa java e seu trabalho é converter o bytecode carregado em código de máquina o qual será inserido na memória e finalmente executado;<br>
    </p>  
</div>

### NOMES, VARIÁVEIS e VINCULAÇÃO <h3>

#### NOMES: <h4>
<div style="text-align: justify">
    <p> 
        As convenções de nomenclatura tornam os programas mais fáceis de serem lidos. Fornecem também, informações sobre a função do identificador por exemplo, se é uma constante, pacote ou classe o que pode ser útil para um bom entendimento do código.
    </p> 
    <p> <b>Em Java, ficou convencionado o seguinte:</b> </p> 
        <b>Packages :</b> O prefixo de um nome de pacote é sempre escrito em letras  minúsculas e deve ser um dos nomes de domínio de nível superior. Caso esse pacote tenha mais de um nome, estes devem ser separados por um "." (ponto); Veja em Exemplo.1<br>
        <b>Classes :</b> O nome de uma classe deve ser sempre iniciado em letra maiúscula, caso aja mais de um, este também se iniciará dessa forma; Veja em Exemplo.2<br>
        <b>Interfaces :</b> Segue o mesmo padrão da escrita dos nomes de classes; Veja em Exemplo.3<br>
        <b>Métodos :</b> Os métodos devem ser verbos, em maiúsculas e minúsculas, iniciando com letra minúscula e a primeira letra de cada palavra interna maiúscula; Veja em Exemplo.4<br>
        <b>Variáveis :</b> Segue o mesmo padrão da escrita de um método, sem a obrigatoriedade de ser um verbo; Não devem começar com caracteres de sublinhado _ ou cifrão $, embora ambos sejam permitidos; Veja em Exemplo.5<br>
        <b>Constantes :</b> Devem ser escritos todos maiúsculos com palavras separadas por sublinhados ("_"), caso aja mais de uma; Veja em Exemplo.6 
    </p>
</div>

##### Exemplo.1 <h5>
~~~
    package atividade.paradigmas.java;
~~~

##### Exemplo.2 <h5>
~~~
    public class LinguagemJava {
        ...
    }
~~~

##### Exemplo.3 <h5>
~~~
    public interface ILinguagemJava{
        ...
    }
~~~

##### Exemplo.4 <h5>
~~~
    public void reservarLivro(parâmetro) {
        ...
    }

    public void comprarLivro() {
        ...
    }
~~~

##### Exemplo.5 <h5>
~~~
    String livro
    int quantidadeLivro
    double precoLivro
~~~

##### Exemplo.6 <h5>
~~~
    int MIN, MIN_VALOR, MAX_Valor;
~~~

#### VARIÁVEIS: <h4>
<div style="text-align: justify">
    <p> 
        Java apresenta três diferentes tipos de variavés.
    </p> 
    <p> <b>Tipos:</b> </p> 
        <b>Variáveis ​​de instância :</b> Aquela que é declarada dentro de uma classe, mas fora fora de quaisquer métodos e blocos;<br>
        <b>Variáveis ​​de classe :</b> Aquela que é declarada dentro de uma classe, fora de todos os blocos e é declarada como estática;<br>
        <b>Variáveis ​​Locais :</b> TAquelas declaradas no início de um subalgoritmo. São visíveis, ou seja, podem ser utilizadas somente pelo subalgoritmo onde foram declaradas. Outros subalgoritmos ou mesmo o algoritmo principal não podem utiliza-las;<br>
    </p>
</div>

#### VINCULAÇÃO: <h4> 
<div style="text-align: justify">
    <p> 
        Em Java existem dois tipos de vinculação: vinculação estática e dinâmica.
    </p> 
    <p> <b>Tipos:</b> </p> 
        <b>Estática :</b> Quando o tipo do objeto é determinado em tempo de compilação (pelo compilador). Se houver qualquer método privado, final ou estático em uma classe, haverá esse tipo de vinculação; Veja em Exemplo.7 <br>
        <b>Dinâmica :</b> Quando o tipo do objeto é determinado em tempo de execução; Veja em Exemplo.8
    </p>
</div>

#### Exemplo.7 <h4>
<div style="text-align: justify">
    <p> 
        A referência para a classe pai e a classe filha é a mesma (Usuário). Ou seja, um único objeto se refere a ambos. Como o método é estático, o compilador está ciente de que esse método não pode ser sobrescrito na classe filha e sabe qual método chamar. Portanto, não há ambigüidade e a saída será a mesma em ambos os casos.
        Esses métodos só podem ser acessados ​​pelo objeto da classe local. Portanto, a vinculação desses métodos sempre ocorre durante a compilação.
    </p> 
</div>

~~~
    classe Usuario {
        public void reservaLivro () {
            System.out.println("O usuário reservou o Livro X");
        }
    }

    classe Aluno extend Usuario {
        public static void speak () {
            System.out.println("O usuário reservou o Livro X");
        }
    }

    public class StaticBinding {
        public static void main ( String args [ ]){
            // Referência e objeto são do tipo Usuario.
            Usuario usuario = new Usuario () ; 
            usuario.reservaLivro() ;
            // A referência é do tipo Usuario e o objeto é do tipo Aluno
            Usuario aluno = new Aluno (); 
            aluno.reservaLivro() ;  
        }
    }

    Saida:
    O usuário reservou o Livro X
    O usuário reservou o Livro X
~~~

#### Exemplo.8 <h4>
<div style="text-align: justify">
    <p> 
        Durante a compilação, o compilador não sabe qual método deverá ser chamado, aqui o método pode ser sobrescrito. Isso ocorre porque o compilador não vai de acordo com o tipo do objeto, mas verifica apenas de acordo com a variável de referência. Portanto, a vinculação é atrasada para o tempo de execução, de modo que o método será chamada com base no tipo do objeto em questão.
    </p> 
</div>

~~~
    classe Usuario {
        public void reservaLivro () {
            System.out.println("O usuário reservou o Livro X");
        }
    }

    classe Aluno extend Usuario {
        @override
        public static void speak () {
            System.out.println("O aluno reservou o Livro X");
        }
    }

    public class DynamicBinding {
        public static void main ( String args [ ]){
            // Referência e objeto são do tipo Usuario.
            Usuario usuario = new Usuario () ; 
            usuario.reservaLivro() ;
            // A referência é do tipo Usuario e o objeto é do tipo Aluno
            Usuario aluno = new Aluno (); 
            aluno.reservaLivro() ;
        }
    }

    Saida:
    O usuário reservou o Livro X
    O aluno reservou o Livro X
~~~

### ESCOPO, TEMPO DE VIDA e AMBIENTES DE REFERÊNCIA: <h3> 

<div style="text-align: justify">
    <p> 
        Analisando cada tipo de váriavel com relação ao Escopo e Tempo De Vida, tem-se:
    </p> 
    <p> <b>Variáveis ​​de instância</b> </p>
        <b>Escopo :</b> Em toda a classe, exceto nos métodos estáticos;<br>
        <b>Tempo De Vida :</b> Até que o objeto da classe esteja na memória;
    </p>
    <p> <b>Variáveis ​​de classe</b> </p>
    <p> <b>Escopo :</b> Em toda a classe; <br>
        <b>Tempo De Vida :</b> Até que o programa seja finalizado; </p> 
    <p> Variáveis ​​Locais </p>
        <b>Escopo :</b> Dentro do bloco  em que está declarado;<br>
        <b>Tempo De Vida :</b> Até que o controle saia do bloco em que foi declarado;
    </p> 
</div>

<div style="text-align: justify">
    <p> 
        Apesar de ter recursos que permitem vinculações estáticas e também vinculações dinâmicas, Java é considerada uma linguagem de escopo estático. Desta forma, a referência de variáveis se dá dentro do ambiente estático. 
    </p> 
    <p> 
        Java é uma linguagem de escopo estático, portanto suas variáveis são referenciadas dentro do ambiente de referência estático. Por exemplo, um método de uma classe não pode fazer referência a uma variável declarada por um ancestral dela.
    </p> 
</div>


## CAPACIDADES DA LINGUAGEM 

### METAPROGRAMAÇÃO: <h3>
<div style="text-align: justify">
    <p>
        Metaprogramação é escrever programas que manipulam outros programas ou a si próprios com base em metadados. Um bom caso de uso é salvar metadados digitalizados para uso posterior durante o tempo de execução, permitindo a inicialização mais rápida de seu aplicativo.
    </p>
    <p>
        Metaprogramação é o segredo por trás do sucesso de muitos frameworks Java, como Spring e Struts 2, e constitui a espinha dorsal de muitas das APIs mais fundamentais em toda a pilha de tecnologia Java. Mais importante ainda, a metaprogramação pode ser usada para melhorar seus aplicativos e testes de aplicativos. 
    </p>
</div>

### SEGURANÇA E CONFIABILIDADE: <h3>
<div style="text-align: justify">
    <p>
        Java é uma linguagem de programação bastante segura. Fornece todos os seguintes recursos para garantir isso:
    </p>
    <b>JVM:</b> Desempenha um papel vital para fornecer segurança. Atua verificando o código de byte. Fornece garantias de que nenhuma operação insegura será executada e também ajuda a diminuir as possibilidades de que os programadores sofram com falhas de segurança de memória.<br>
    <b>API's de segurança:</b> As bibliotecas de classes Java fornecem várias APIs que levam à segurança. Essas APIs contêm algoritmos criptográficos e protocolos de autenticação que levam à comunicação segura.<br>
    <b>Byte Code:</b> Sempre que um usuário compila o programa Java, o compilador cria um arquivo de classe com Bytecode, que é testado pelo JVM no momento da execução do programa em busca de vírus e outros arquivos maliciosos.<br>
    <b>Gerente de segurança:</b> O gerenciador de segurança é responsável por verificar as permissões e propriedades das classes. Ele monitora os recursos do sistema acessados ​​pelas classes autorizadas. Ele também controla as conexões de soquete.<br>
    <b>Nenhum conceito de ponteiros:</b> Java não oferece suporte para o conceito de ponteiros. O uso de ponteiros pode levar a operações não autorizadas de leitura ou gravação. Portanto, o usuário não pode apontar para nenhum local da memória.<br>
    <b>Gerenciamento de memória:</b> Java gerencia automaticamente a memória, que é conhecida como coleta de lixo. A própria JVM gerencia a memória. Os programadores estão livres desse gerenciamento. Conseqüentemente, não há chance de falha no gerenciamento de memória.<br>
    <b>Verificação de tempo de compilação:</b> A verificação do tempo de compilação também torna o Java seguro. Considere um cenário no qual um método não autorizado está tentando acessar a variável privada, neste caso, a JVM fornece o erro de tempo de compilação, evitando, assim, que o sistema trave.<br>
    <b>Segurança criptográfica:</b> Java fornece uma classe chamada java.secrurity.SourceCode que também fornece segurança. Se obtivermos código de outras fontes, devemos verificar de onde o código está vindo. A classe mantém as informações de origem e fornece garantias para manter uma assinatura digital e segurança criptográfica.<br>
    <b>Java Sandbox:</b> Java Sandbox é um componente importante quando se trata de segurança. É uma área restrita onde os miniaplicativos são executados. Java não fornece recursos de sistema sem verificar se um miniaplicativo deve ser executado.<br>
    <b>Manipulação de exceção:</b> O recurso de tratamento de exceções adiciona mais segurança em Java. O recurso relata o erro ao programador durante o tempo de execução e assim, o código não será executado até que o programador o retifique.<br>
    <b>Java ClassLoader:</b> Existem vários carregadores de classes presentes na JVM. Ele fornece e mantém namespaces para classes específicas. A vantagem do ClassLoader é que as classes não confiáveis ​​não se comportariam como uma classe confiável.<br>
    <p>
        Os autores a consideram  como uma linguagem confiável. No entanto, Java não é, por exemplo, uma escolha muito confiável na programação do sistema porque não expõe os detalhes de hardware de nível inferior aos desenvolvedores. Mas, apesar de suas falhas, nenhuma outra linguagem se compara ao Java em termos de flexibilidade e integração perfeita com outras estruturas e tecnologias.
    </p>
</div>

### PERFORMANCE: <h3>
<div style="text-align: justify">
    <p>
        Em termos de agilidade, Java é mais rápido do que outras linguagens de programação interpretadas tradicionais, isso porque o bytecode Java é "próximo" do código nativo. 
    </p>
    <p>
        Por outro lado, Java é uma linguagem interpretada, por isso, ainda é um pouco mais lenta do que as linguagens compiladas, por exemplo, C, C ++, etc.
    </p>
</div>

### ESCALABILIDADE: <h3>
<div style="text-align: justify">
    <p>
        Escalabilidade significa que um aplicativo pode lidar com mais e mais usuários alterando a configuração do hardware em vez do próprio aplicativo. Normalmente, isso significa, entre outras coisas, que é particionado em partes que podem ser executadas em servidores separados.
    </p>
    <p>
        Escalável pode significar coisas diferentes no contexto da linguagem de programação e do tempo de execução.
    </p>
    <p>
        A linguagem Java suporta modularidade e verificação estática em um nível suficiente para construir grandes sistemas (grandes projetos com vários desenvolvedores etc.). O desempenho de compilação e tempo de execução é suficiente para ter um ambiente de compilação e teste de integração contínua para um grande projeto. Existem ferramentas de suporte suficientes para análise, depuração, criação de perfil, entre outros. A linguagem e as bibliotecas fornecem fornecem algoritmos e estruturas de dados assintoticamente ideais.As construções de linguagem permitem e exploram o potencial de otimização e se adaptam bem ao hardware moderno. Por outro lado o tempo de execução, em java, não está livre de sobrecarga e custos de funcionalidade desnecessários ou indesejados,em particular, há muita sobrecarga de espaço. 
    </p>
</div>

### CUSTO: <h3>
<div style="text-align: justify">
    <p>
        É projetado para permitir o desenvolvimento de aplicativos portáteis de alto desempenho para a mais ampla gama de plataformas de computação possível, permitindo, portanto, os princípios fundamentais de acessibilidade abrangente, bem como interação de plataforma cruzada. Ao disponibilizar aplicativos em ambientes heterogêneos, as empresas podem fornecer mais serviços e aumentar a produtividade, comunicação e colaboração do usuário final - e reduzir drasticamente o custo de propriedade de aplicativos corporativos e de consumo.
    </p>
</div>

## PRODUTIVIDADE DO DESENVOLVEDOR 
<div style="text-align: justify">
    <p>
        Java se tornou inestimável para os desenvolvedores, permitindo-lhes:
    </p>
    <p>
    <b>*</b> Escrever software em uma plataforma e executá-lo em praticamente qualquer outra plataforma.<br>
    <b>*</b> Criar programas que podem ser executados em um navegador da web e acessar os serviços da web disponíveis.<br>
    <b>*</b> Desenvolver aplicativos do lado do servidor para fóruns online, lojas, enquetes, processamento de formulários HTML e muito mais.<br>
    <b>*</b> Usar a linguagem Java para criar aplicativos ou serviços altamente personalizados.<br>
    <b>*</b> Escrever aplicativos poderosos e eficientes para telefones celulares, processadores remotos, microcontroladores, módulos sem fio, sensores, gateways, produtos de consumo e praticamente qualquer outro dispositivo eletrônico.<br>
    <b>*</b> Entre outros.<br>
    </p>
    <p>
        Os programas escritos em Java são portáteis, pois podem ser executados em qualquer tipo de sistema operacional e de hardware. Isso se apresenta como uma enorme vantagem para desenvolvedores e empresas que não querem se limitar a um único ambiente.
    </p>
</div>

### FRAMEWORS e CONTÂINERS: <h3>
<div style="text-align: justify">
    <p>
        Frameworks Java são grupos de códigos previamente escritos e reutilizáveis, usados como templates pelos desenvolvedores na criação de aplicações. Esses frameworks eliminam o trabalho manual excessivo ao programar uma aplicação uma vez que os desenvolvedores só precisam incluir código personalizado se for necessário.
    </p>
    <p>
        Esses frameworks podem incluir funções e classes predefinidas,como categorias de objetos, que são usadas para processar, inserir e gerenciar dispositivos de hardware, além de interagir com o software do sistema. Isso depende do tipo de framework, da habilidade do desenvolvedor Java, do que ele está tentando realizar e das preferências pessoais dele.
    </p>
    <p>
        Há vários frameworks Java disponíveis. O que determina qual deles usar são as habilidades do desenvolvedor ou os requisitos do site ou aplicação. A seguir, estão alguns frameworks open source muito usados:
    </p>
    <p>
    <b>Quarkus:</b> Framework Java de stack completo, compatível com infraestruturas nativas em nuvem e baseadas em microsserviços.<br>
    <b>Grails:</b> Escrito na linguagem de programação Groovy, oferece frameworks de aplicação web com recursos de exibição para plugins CSS e HTML.<br>
    <b>Google Web Toolkit (GWT):</b> Conecta as equipes de desenvolvimento de front-end às de back-end.<br>
    <p>
        Outros frameworks Java muito usados:
    </p>
    <p>
    <b>Vaadin:</b> Voltado às interfaces de usuário.<br>
    <b>JavaServer Faces (JSF) do Oracle:</b> Oferece frameworks de front-end aos desenvolvedores de back-end.<br>
    <b>Play:</b> Compatível com a linguagem de programação Scala, simplifica o desenvolvimento de aplicações web.<br>
    </p>
    <p>
        Dificilmente uma aplicação gráfica é composta por um único componente, mas sim por vários componentes inter-relacionados. Para este tipo de aplicação, um componente fundamental é a área onde os demais componentes da aplicação estarão dispostos. Um componente que pode conter outros componentes é denominado um container.
    </p>
    <p>
        Em Java, a classe Container é a classe abstrata que define as funcionalidades básicas associadas a um container, tais como adicionar e remover componentes, o que é possível através dos métodos add() e remove(), respectivamente. É possível também estabelecer qual a estratégia de disposição de componentes no container, ou seja, qual o método de gerência de layout, através do método setLayout().
    </p>
</div>

### FERRAMENTAS: <h3>
<div style="text-align: justify">
    <p>
        Dentre as diversas etapas do desenvolvimento de um software existem ferramentas que podem auxiliar o desenvolvedor na entrega de um produto muito melhor. Saber escolhe-las é um passo fundamental, pois elas também podem atrasar o projeto final. As ferramentas disponíveis para a plataforma Java são em sua grande maioria gratuitas, o que facilita a sua disseminação e a criação de aplicativos por terceiros.  
    </p>
    <p>
        Compilação, configuração e deploy de aplicações, por exemplo, podem ser feitos através da própria IDE, como Eclipse. Entretanto, quando os projetos se tornam maiores e mais complexos, as construções automáticas se tornam bastante necessárias. Daí, trabalhar com ferramentas que automatizam todo o processo de construção pode economizar muito tempo e trabalho, ao invés de persistir em ficar na própria IDE. Em outros casos, a melhor alternativa é a utilização ferramentas de integração contínua, que fazem ainda mais além do que as ferramentas de construção, adicionando mais etapas e automatizando ainda mais o processo como um todo.
    </p>
    <p>
        A seguir, algumas das ferramentas mais usadas atualmente:
    </p>
    <p>
    <b>JUnit:</b> Para testes de unidade na plataforma Java e tem como benefício a integração com o Eclipse.<br>
    <b>Make:</b> Ferramenta de linha de comando original para o processo de construção. Compila executáveis baseando-se em regras, dependências e comandos.<br>
    <b>Ant:</b> É o padrão oficial para compilar projetos Java. Assim como o Make, ele trabalha com targets, dependências e comandos, porém a sintaxe é completamente diferente do Make. Além disso, o Ant utiliza um documento no padrão XML para cada projeto e elementos XML para listar comandos.<br>
    <b>Maven:</b> Esta substituindo o Ant em diversos projetos. Ele é considerado mais do que uma ferramenta de construção, pois é conhecido como Project Object Model (Modelo de Objeto de Projeto).<br>
    <b>CruiseControl:</b> É uma das ferramentas de integração contínua mais utilizadas pelas organizações. Inclui dezenas de plugins para uma grande variedade de funcionalidades como controle de código-fonte, tecnologias de build, notificações incluindo e-mail e mensagens instantâneas, entre outras funcionalidades.<br>
    <b>Jenkins:</b> É uma ferramenta de integração contínua que realiza rapidamente tarefas que são demoradas como compilação do projeto, execução dos testes automatizados e alerta aos desenvolvedores a cada mudança de código no repositório ou em caso de erros ou falhas nos testes automatizados.<br>
    <b>Entre outras</b> ...<br>
    </p>
</div>

### SINTAXE, SEMÂNTICA e OPERAÇÕES PREDEFINIDAS: <h3>

#### LEGIBILIDADE e REDIGIBILIDADE: <h4>
<div style="text-align: justify">
    <p>
        A sintaxe da linguagem deve ser o mais próxima possível da notação matemática padrão e os programas nela contidos devem ser legíveis com poucas explicações adicionais.Com relação a <b>legibilidade</b>, Java é mais simples e mais elegante, por exemplo, do que a outra linguagem principal imperativa/orientada a objetos, que é C++. Os tipos primitivos de Java não são objetos baseados em classes. Java não tem ponteiros, tipos de enumeração, subprogramas autônomos ou herança múltipla. Java foi projetado para ser mais simples, para ser uma linguagem de facil legibilidade, e de fato é.
    </p>
    <p>
        Com relação a <b>redigibilidade</b>, estruturas de bloco, passando parâmetros para subprogramas e procedimentos recursivos permitiram aos programadores uma capacidade de escrita que eles nunca tiveram antes. Uma questão em discussão é que em java, por exemplo, não se pode atribuir uma coerção de tipo de float a int, enquanto em C e C ++ isso é possível e frequentemente feito, ou seja, java não permite ao programador tanta liberdade, na escrita, mas isso não é um grande problema.
    </p> 
    <p>
        Se comparada com outras linguagens, pode-se dizer que Java é uma linguagem até fácil de se escrever. Permite, por exemplo, abstração por meio de funções, basta escrever uma função uma vez e chamá-la várias vezes e permite expressividade ao possibilitar convenientemente várias maneiras de escrever uma certa rotina. 
    </p>
</div>

#### ESTRUTURAS DE CONTROLE: <h4> 

<div style="text-align: justify">
    <p> 
        Uma estrutura de controle é uma forma sintática em uma linguagem de programação que expressa o fluxo de controle sobre uma lista específica de instruções para tomar decisões entre o caminho alternativo ou caminhos dados e executa as instruções na sequência em que aparecem, uma por uma. Essa condição é chamada de cumprimento da sequência. A instrução que será realizada a seguir não está necessariamente localizada na próxima linha. Este cenário é conhecido como transferência de controle do programa.
    </p> 
    <p> 
        Em Java, existem três tipos de estruturas de controle. 
    </p> 
    <p> <b>A saber :</b> </p>            
    </p>
</div>

<div style="text-align: justify"> 
<b>1. Ramificações ou declarações condicionais :</b> Usadas para escolher entre dois ou mais caminhos. Determina se uma certa instrução ou bloco de instruções será executado ou não. Se a condição for verdadeira, um bloco da instrução será executado, caso contrário, não. São três: <br> 
</div>

<div style="text-align: justify"> 
        <b>1.1 if / else / else if :</b>             
    </p>
</div>

<div style="text-align: justify"> 
        <b>1.1.1 : if </b>             
    </p>
</div>

~~~
    if (condição) { 
        // código que deverá ser executado caso resposta para a condição seja verdadeira
    }   
~~~

<div style="text-align: justify"> 
        <b>1.1.2 : if, else </b>             
    </p>
</div>

~~~
    if (condição) { 
        // código que deverá ser executado caso resposta para a condição seja verdadeira
    } 
    else { 
        // código que deverá ser executado caso resposta para a condição verificada no if seja falsa
    }
~~~

<div style="text-align: justify"> 
        <b>1.1.3 : if, else if, else </b>             
    </p>
</div>

~~~
    if (condição1) { 
        // código que deverá ser executado caso resposta para a condição seja verdadeira
    } else if (condição2) { 
        // código que deverá ser executado caso resposta para a condição seja verdadeira
    } 
    … 
    else { 
        // código que deverá ser executado caso resposta para todas as condições anteriores forem falsas 
    }
~~~

<div style="text-align: justify">
    <p> <b>1.2 Estruturas if, else if e else aninhadas  :</b> As instruções aninhadas significam uma instrução certa estrutura envolvida por uma outra estrutura mais externa.<br>
</div>

~~~
    if (condição1) { 
        // código que deverá ser executado caso resposta para a condição seja verdadeira
        if (condição2) { 
            // código que deverá ser executado caso resposta para a condição seja verdadeira          
        }
        ...
    }   
~~~
<div style="text-align: justify">
    <p> 
        O mesmo pode ser feito para aninhar as demais estruturas. Em tese, é possível encadear ou aninhar blocos infinitamente, mas isso é tido como prejudicial para a legibilidade do código.
    </p> 
</div>

<div style="text-align: justify">
    <p> <b>1.3 Switch case :</b> Usada quando tem-se vários casos para escolher. A expressão switch (condição) é avaliada uma vez e o valor da expressão é comparado com os valores de cada caso. Se houver uma correspondência, o bloco de código associado será executado. Se não houver correspondência, o programa irá procurar a cláusula padrão opcional e, se encontrada, transfere o controle para essa cláusula, executando as instruções associadas.<br>
</div>

~~~
    switch (expressão) { 
        caso n: 
            bloco de código 
        caso n+1: 
            bloco de código 
        ...
        padrão: 
            bloco de código 
    }
~~~

<div style="text-align: justify">
        <b>2. Loops :</b> Usados ​​para iterar por meio de vários valores / objetos e executar repetidamente blocos de código específicos. Os tipos básicos de loop em Java são : <br>          
    </p>
</div>

<div style="text-align: justify"> 
        <b>2.1 for  :</b>             
    </p>
</div>

~~~
    for (expressão 1; condição; expressão 2){
        // comando que será executado até que a condição não seja 
            mais respeitada
    }
~~~

<div style="text-align: justify"> 
        <b>2.2 while  :</b>             
    </p>
</div>

~~~
    while (condição) {
        // comando que será executado até que a condição não seja 
            mais respeitada
    }
~~~

<div style="text-align: justify"> 
        <b>2.3 do while  :</b>             
    </p>
</div>

~~~
    do {
		// comando que será executado ao menos uma vez
    }   
    while(condição); //Se a resposta pra condição for true o bloco de 
                        comando é executado novamente.
~~~

<div style="text-align: justify">
        <b>3. Ramificação de instruções :</b> usadas para alterar o fluxo de controle em loops. Existem dois tipos em Java :<br>              
    </p>
</div>

<div style="text-align: justify"> 
        <b>3.1 break :</b>             
    </p>
</div>

~~~
    for (expressão 1; condição1; expressão 2){
        // comando que será executado até que a condição não seja 
            mais respeitada
        if (condição2) { 
            break; //Se a condição2 for verdadeira, sai mais cedo do loop 
                    mesmo que a condição1 ainda seja respeitada
        }
    }
~~~

<div style="text-align: justify"> 
        <b>3.2 continue :</b>             
    </p>
</div>

~~~
    for (expressão 1; condição1; expressão 2){
        // comando que será executado até que a condição não seja 
            mais respeitada
        if (condição2) { 
            continue; //Se a condição2 for verdadeira, pula o resto do 
                        loop em que estamos
        }
    }
~~~


## ECOSSISTEMA 
<div style="text-align: justify">
<p> 
    A maturidade, padrões, multiplataforma, retrocompatibilidade e a maior comunidade de desenvolvimento do mundo são algumas das características que tornam o Java a principal plataforma de desenvolvimento. 
</p>
<p>
    A comunidade de desenvolvedores Java reúne-se em grupo denominados JUGs (Java User Groups). No Brasil o movimento de grupos de usuários expandiu-se bastante e tem formado alguns dos maiores grupos de usuários Java do mundo,como por exemplo, o PortalJava, GUJ e o JavaFree.
</p>
<p>
    Java representa um enorme ecossistema e fonte de empregos. Estima-se que existam nove milhões de desenvolvedores Java em todo o mundo em 2017, de acordo com a Oracle. Uma pesquisa recente no site de empregos Dice.com encontrou quase 12.000 empregos relacionados a Java nos EUA, em comparação com aproximadamente 9.000 empregos em JavaScript e 7.600 em Python.
</p>
</div>

## INFORMAÇÕES ADICIONAIS  

### REFERÊNCIAS: <h3> 
<p> 
https://www.learningjournal.guru/article/programming-in-java/scope-and-lifetime-of-a-variable/
</p>

<p> 
https://www.oracle.com/java/technologies/javase/codeconventions-namingconventions.html
</p>

<p> 
https://www.geeksforgeeks.org/compilation-execution-java-program/
</p>

<p> 
https://www.javatpoint.com/static-binding-and-dynamic-binding
</p>

<p> 
https://techvidvan.com/tutorials/static-and-dynamic-binding-in-java-differences-and-examples/
</p>

<p>
https://medium.com/javarevisited/control-structures-in-java-conditional-statements-e4d8da0421cc
</p>

<p>
https://www.baeldung.com/java-control-structures
</p>

<p> 
http://b.web.umkc.edu/buckleyb/cs_441.htm
</p>

<p>
https://www.devmedia.com.br/principais-ferramentas-de-apoio-ao-desenvolvimento-java/34126 
</p>

<p> 
https://www.redhat.com/pt-br/topics/cloud-native-apps/what-is-a-Java-framework
</p>

<p> 
https://codeinstitute.net/blog/what-is-java/
</p>

<p> 
https://www.devmedia.com.br/java-historia-e-principais-conceitos/25178
</p>


<p> 
https://www.javatpoint.com/why-java-is-secure
</p>

<p> 
https://www.javatpoint.com/features-of-java#High-Performance
</p>

<p> 
https://blogs.oracle.com/java/post/metaprogramming-manipulating-data-about-data
</p>
