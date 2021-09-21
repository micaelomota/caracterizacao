# Trabalho 1 : Atividade Parcial L1 <h1>

### Linguagem de Programação : JAVA <h3>

## Modelo de Tradução <h2>
<div style="text-align: justify"> 
    Java, por ser uma linguagem de programação que independe de plataforma, não irá funcionar na compilação em apenas uma etapa. Envolve uma execução em duas etapas: a primeira, por meio de um compilador, o qual é independente do sistema operacional; e uma segunda, em uma JVM (Máquina virtual), onde cada Sistema Operacional tem sua própria customizada. A seguir, as duas etapas:

</div>

#### Compilação : <h5>
<div style="text-align: justify"> 
    Primeiramente, o arquivo principal '.java' é passado para o compilador. Este será convertido em um código-fonte (bytecode). Ao realizar essa conversão, o compilador segue os seguintes passos:

    __Análise :__ Lê o arquivo principal '.java' e mapeia a sequência de tokens resultante da árvore sintática;

    __Enter:__ insere símbolos, para as definições, na tabela de símbolos;

    __Anotações do processo:__ Caso seja solicitado, processa as anotações encontradas nas unidades de compilação em questão;

    __Fluxo:__ Analisa o fluxo de dados nas árvores, realizando verificação de atributos e também acessibilidade;

    __Desugar:__ Reescreve a árvore sintática;

    __Geração:__ São gerados arquivos '.Class'; 

</div>

#### Execução : <h5>
<div style="text-align: justify"> 
    O arquivo '.Class' gerado na etapa anterior é passado para a JVM e, em seguida, transcorre por três estágios antes que o código final de máquina seja finalmente executado. A saber: 

    __lass Loader (Carregador de classe) :__ A classe principal é carregada na memória passando seu arquivo '.class' para a JVM;

    __Bytecode Verifier (Verificador de Bytecode) :__Depois que o bytecode de uma classe é carregado na etapa anterior, este deverá ser agora inspecionado, afim de verificar se as instruções não executam ações prejudiciais;

    __Just-In-Time Compiler (Compilador Just-In-Time) :__ Este é o estágio final encontrado pelo programa java e seu trabalho é converter o bytecode carregado em código de máquina o qual será inserido na memória e finalmente executado;

</div>


## Nomes, Variáveis e Vinculação <h2>

#### Nomes: <h5>
<div style="text-align: justify"> 
    As convenções de nomenclatura tornam os programas mais fáceis de serem lidos. Fornecem também, informações sobre a função do identificador por exemplo, se é uma constante, pacote ou classe o que pode ser útil para um bom entendimento do código. Em Java, ficou convencionado o seguinte:

    __Packages:__ O prefixo de um nome de pacote é sempre escrito em letras  minúsculas e deve ser um dos nomes de domínio de nível superior. Caso esse pacote tenha mais de um nome, estes devem ser separados por um "." (ponto);
    *Exemplo: paradigmas; parcial.de.paradigmas*

    __Classes:__ O nome de uma classe deve ser sempre iniciado em letra maiúscula, caso aja mais de um, este também se iniciará dessa forma;
    *Exemplo: class Animal; class AnimalMarinho*

    __Interfaces:__ Segue o mesmo padrão da escrita dos nomes de classes;
    *Exemplo: interface Modelo; interface ModeloConvencional*

    __Métodos:__ Os métodos devem ser verbos, em maiúsculas e minúsculas, iniciando com letra minúscula e a primeira letra de cada palavra interna maiúscula;
    *Exemplo: movimentar(); movimentarCachorro()*

    __Variáveis:__ Segue o mesmo padrão da escrita de um método, sem a obrigatoriedade de ser um verbo; Não devem começar com caracteres de sublinhado _ ou cifrão $, embora ambos sejam permitidos.
    *Exemplo: int a; double d; String alunoGraduacao*

    __Constantes:__ Devem ser escritos todos maiúsculos com palavras separadas por sublinhados ("_"), caso aja mais de uma. 
    *Exemplo: MIN; MIN_VALOR; MAX_Valor*
    
</div>

#### Variáveis: <h5>
<div style="text-align: justify"> 
    Java apresenta três diferentes tipos de variavés, que são:

    __Variáveis ​​de instância:__ Aquela que é declarada dentro de uma classe, mas fora fora de quaisquer métodos e blocos;

    __Variáveis ​​de classe:__ Aquela que é declarada dentro de uma classe, fora de todos os blocos e é declarada como estática;

    __Variáveis ​​Locais:__ Todas aquelas ​​que não são variáveis ​​de instância ou classe;

</div>

#### Vinculação: <h5> 
<div style="text-align: justify"> 
    Em Java existem dois tipos de vinculação: vinculação estática e dinâmica.

    __Vinculação Estática:__ Quando o tipo do objeto é determinado em tempo de compilação (pelo compilador). Se houver qualquer método privado, final ou estático em uma classe, haverá esse tipo de vinculação;

    __Vinculação Dinâmica:__  Quando o tipo do objeto é determinado em tempo de execução;

</div>

## Escopo, Tempo De Vida e Ambientes de Referência <h2> 
<div style="text-align: justify"> 
    Analisando cada tipo de váriavel com relação ao Escopo e Tempo De Vida, tem-se:

    *Variáveis ​​de instância* 
    __Escopo :__ Em toda a classe, exceto nos métodos estáticos;
    __empo De Vida :__ Até que o objeto da classe esteja na memória;

    *Variáveis ​​de classe* 
    __Escopo :__ Em toda a classe;
    __Tempo De Vida :__ Até que o programa seja finalizado;

    *Variáveis ​​Locais* 
    __Escopo :__ Dentro do bloco  em que está declarado;
    __Tempo De Vida :__ Até que o controle saia do bloco em que foi declarado;
    
    
</div>







