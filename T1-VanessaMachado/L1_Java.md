# Trabalho 1 : Atividade Parcial L1 <h1>

### Linguagem de Programação : JAVA <h3>

## Modelo de Tradução <h2>
<div style="text-align: justify">
    <p>  
    Java, por ser uma linguagem de programação que independe de plataforma, não irá funcionar na compilação em apenas uma etapa. Envolve uma execução em duas etapas: a primeira, por meio de um compilador, o qual é independente do sistema operacional; e uma segunda, em uma JVM (Máquina virtual), onde cada Sistema Operacional tem sua própria customizada. A seguir, as duas etapas:
    </p>
</div>

### Compilação  <h3>
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
        <b>Geração :</b> São gerados arquivos '.Class'; <br>
    </p>
    
</div>

### Execução  <h3>
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

## Nomes, Variáveis e Vinculação <h2>

### Nomes <h3>
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

#### Exemplos: <h4>

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

### Variáveis <h3>
<div style="text-align: justify">
    <p> 
        Java apresenta três diferentes tipos de variavés.
    </p> 
    <p> <b>Tipos:</b> </p> 
        <b>Variáveis ​​de instância :</b> Aquela que é declarada dentro de uma classe, mas fora fora de quaisquer métodos e blocos;<br>
        <b>Variáveis ​​de classe :</b> Aquela que é declarada dentro de uma classe, fora de todos os blocos e é declarada como estática;
        <b>Variáveis ​​Locais :</b> TAquelas declaradas no início de um subalgoritmo. São visíveis, ou seja, podem ser utilizadas somente pelo subalgoritmo onde foram declaradas. Outros subalgoritmos ou mesmo o algoritmo principal não podem utiliza-las;<br>
    </p>
    
</div>

### Vinculação <h3> 
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

## Escopo, Tempo De Vida e Ambientes de Referência <h2> 

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
</div>

Java é uma linguagem de escopo estático, portanto suas variáveis são referenciadas dentro do ambiente de referência estático. Por exemplo, um método de uma classe não pode fazer referência a uma variável declarada por um ancestral dela.

#### Referências <h4> 
https://www.learningjournal.guru/article/programming-in-java/scope-and-lifetime-of-a-variable/
https://www.oracle.com/java/technologies/javase/codeconventions-namingconventions.html
https://www.geeksforgeeks.org/compilation-execution-java-program/
https://www.javatpoint.com/static-binding-and-dynamic-binding
https://techvidvan.com/tutorials/static-and-dynamic-binding-in-java-differences-and-examples/
