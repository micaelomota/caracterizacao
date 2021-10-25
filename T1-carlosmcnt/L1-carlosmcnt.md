# Caracterização de Linguagens de Programação

### Linguagem de Programação: Java

  * [Apresentação e histórico](#apresenta--o-e-hist-rico)
  * [Características da Linguagem](#caracter-sticas-da-linguagem)
  * [Capacidades da Linguagem](#capacidades-da-linguagem)
  * [Produtividade do Desenvolvedor](#produtividade-do-desenvolvedor)
  * [Ecossistema](#ecossistema)
  * [Informações Adicionais](#informa--es-adicionais)
  * [Referências](#refer-ncias)


## Modelo de compilação:

Na linguagem Java, os programas são compilados em bytecode, um código intermediário entre o código fonte e o código de máquina. O conteúdo de cada classe no programa base é separado em vários arquivos com extensão .class. Quando o código está prestes a ser executado, o bytecode é convertido, usando o compilador just-in-time, gerando um código de máquina que será inserido na memória e executado.


## Nomes, variáveis e vinculação:

Existe uma convenção padrão que é seguida para nomes de variáveis, funções, constantes, entre outras estruturas da linguagem. As convenções principais são:

+ Classe: Começa com letra maiúscula. Se possuir mais de um nome, o próximo também começa com maiúscula.
  
+ Interface: Começa com letra maiúscula e precisa ser um adjetivo.

+ Método: Deve ser um verbo e começar com letra minúscula. Caso possua mais de um nome, a primeira letra de cada palavra interna deve ser maiúscula.

+ Variável: Segue o mesmo padrão de escrita de um método, exceto por não precisar ser um verbo.

+ Constante: Deve ser escrito todo em letras maiúsculas. Se possuir mais de um nome, deve ser dividido por "_".

+ Pacote: Deve começar com letra minúscula, e se tiver mais de um nome, deve ser separado por ponto.

Em todos os casos, não se deve começar nenhum dos nomes com caracteres especiais ($, &, @, _, etc).

___

Existem 3 tipos de variáveis em Java:

+ Variável de instância: Declarada dentro de uma classe, mas fora de qualquer método ou bloco

+ Variável de classe: Declarada dentro de uma classe, fora de todos os blocos e também declarada como static

+ Variável local: Todas as outras que não sejam dos tipos anteriores

___

A vinculação em Java ocorre nos dois tipos, estática e dinâmica.

Para o caso da vinculação estática, ela ocorre por meio de métodos static, private e final. Por exemplo, se uma classe e sua superclasse possuirem um método com o mesmo nome, a referência a ser utilizada pelas duas será a declarada pela superclasse. Exemplo:

```java
class Canideo { //Superclasse
  public void uiva() {
    System.out.println("Canideo uiva");
  }
}
class Cachorro extends Canideo {
  public static void uiva() {
    System.out.println("Cachorro uiva");
  }
}
public class VinculacaoEstatica {
  public static void main( String args[]){
    Canideo c = new Cachorro();
    c.uiva();

    Canideo c2 = new Canideo();
    c2.uiva();
  }
}

Saida:
Canideo uiva
Canideo uiva
```

Para o caso da vinculação dinâmica, ela ocorre por meio do método Override. Por exemplo, se uma classe e sua superclasse possuirem um método com o mesmo nome e a subclasse possuir @Override, cada uma terá sua própria referência. Exemplo:

```java
class Canideo { //Superclasse
  public void uiva() {
    System.out.println("Canideo uiva");
  }
}
class Cachorro extends Canideo {
  @Override
  public void uiva() {
    System.out.println("Cachorro uiva");
  }
}
public class VinculacaoDinamica {
  public static void main( String args[]){
    Canideo c = new Cachorro();
    c.uiva();

    Canideo c2 = new Canideo();
    c2.uiva();
  }
}

Saida:
Cachorro uiva
Canideo uiva
```

## Escopo, tempo de vida e ambientes de referência:

O escopo das variáveis de instância permanece por toda a classe, exceto dentro de métodos estáticos. Seu tempo de vida depende do tempo que o objeto da classe está na memória.

O escopo das variáveis de classe ocorre no espaço definido para a classe. Seu tempo de vida permanece até o final do programa.

O escopo das variáveis locais ocorre no espaço definido para o bloco onde são declaradas. Seu tempo de vida permanece até o fim da execução do bloco.

Java é uma linguagem de escopo estático, portanto suas variáveis são referenciadas dentro do ambiente de referência estático. Por exemplo, um método de uma classe não pode fazer referência a uma variável declarada por um ancestral dela. 

Apesar de ser uma linguaguem de escopo estático, Java pode utilizar funções e métodos dinâmicos, como o método Override visto no exemplo da vinculação dinâmica.

## Estruturas de controle:

As estruturas de controle são blocos para avaliar variáveis e escolher as direções válidas a depender dos parâmetros informados. Elas especificam o fluxo do controles nos programas e ajuda a tornar os códigos mais claros e precisos. As estruturas podem ser de repetição, condicionais ou estruturas de salto. 

Estruturas de tomadas de decisão:

### if/else/else if

A estrutura `if` serve para avaliar uma condição. Ela retorna uma resposta em valor booleano `true` ou `false`. Pode existir mais de um `if` após um primeiro, que serão chamados de `else if`, e criam uma árvore de decisão maior, com mais blocos de código. Tanto para o `if` quanto para o `else if` pode existir o bloco `else`, que será executada quando nenhuma outra condição for verdadeira.

```java
String capital = "Salvador";  

if(capital == "Recife") {  
    System.out.println("A cidade é Recife");  
}
else if (capital == "Fortaleza") {  
    System.out.println("A cidade é Fortaleza");  
}
else if(capital == "Natal") {  
    System.out.println("A cidade é Natal");  
}
else {  
    System.out.println(capital);  
}  
```

### switch case

A estrutura `switch case` é semelhante as estruturas `if/else/else if`, mas possui vários blocos de código que são chamados de casos, que serão executados a depender de cada variável a passar pelo switch. A legibilidade dessa estrutura é mais simples. Existe um caso `default` para quando nenhum outro caso tem sua expressão satisfeita. A palavra `break` é utilizada para sair do bloco quando a condição é satisfeita, mas se não houver, os próximos casos serão executados.

```java
int num = 27;  
switch (num){  
case 0:  
    System.out.println("Número é múltiplo de 3");  
    break;  
case 1:  
    System.out.println("Número é múltiplo de 4");  
    break;  
default:  
    System.out.println(num);
}  
```

Estruturas de repetição:

### for

A estrutura `for` é utilizada para quando sabemos a quantidade de vezes que iremos executar um bloco de código. Primeiro, temos a inicialiazação da variável, depois a checagem da condição no bloco e o incremento ou decremento na variável, que vai definir se o loop continuará ou não. A checagem da condição define até quando o loop irá continuar.

```java    
  for(int i=1; i<=4; i++){    
    fat=fat*i;    
  }    
  System.out.println("O fatorial de 4 é: "+fat);    
```




## Referências

1. https://www.javatpoint.com/control-flow-in-java
