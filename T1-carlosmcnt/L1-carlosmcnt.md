# Caracterização de Linguagens de Programação

## Linguagem de Programação: Java

  * [Apresentação e histórico](#apresentação-e-histórico)
   * [Características da Linguagem](#características-da-linguagem)
  * [Capacidades da Linguagem](#capacidades-da-linguagem)
  * [Produtividade do Desenvolvedor](#produtividade-do-desenvolvedor)
  * [Ecossistema](#ecossistema)
  * [Informações Adicionais](#informa--es-adicionais)
  * [Referências](#referências)

## Apresentação e histórico

_Java é uma linguagem de programação que atua sob o paradigma da orientação a objetos e foi lançada em 1995 por James Gosling, na empresa Sun Microsystems. Atualmente, Java é a segunda linguagem mais popular no mundo, que mostra o quão importante ela é para o mundo da programação._

_As aplicações em Java são executadas na máquina virtual Java, a JVM, que permite que elas funcionem em qualquer plataforma que possua ela, como dispositivos móveis, aplicações para web, entre outros. Justamente por isso, Java é a linguagem mais utilizada no ambiente corporativo_

_Entre os grandes projetos que utilizam Java, existe o jogo Minecraft, os ambientes de desenvolvimento Eclipse e Netbeans, o aplicativo de download Azureus, etc._

___
## Características da linguagem:
___
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
___
## Produtividade do desenvolvedor:
___
### Estruturas de controle:

As estruturas de controle são blocos para avaliar variáveis e escolher as direções válidas a depender dos parâmetros informados. Elas especificam o fluxo do controles nos programas e ajuda a tornar os códigos mais claros e precisos. As estruturas podem ser de repetição, condicionais ou estruturas de salto. 

### Estruturas de tomadas de decisão:

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

### Estruturas de repetição:

### for

A estrutura `for` é utilizada para quando sabemos a quantidade de vezes que iremos executar um bloco de código. Primeiro, temos a inicialiazação da variável, depois a checagem da condição no bloco e o incremento ou decremento na variável, que vai definir se o loop continuará ou não. A checagem da condição define até quando o loop irá continuar.

```java    
    //O iterador começa em um, incrementa após cada iteração e para quando chegar em 4.
  for(int i=1; i<=4; i++){    
    fat=fat*i;    
  }    
  System.out.println("O fatorial de 4 é: " + fat);    
```

### while

A estrutura `while` é utilizada quando não temos a quantidade de vezes que iremos executar um bloco. A única condição desse laço é a que determina até quando ele irá iterar.

```java    
  //Todos os números menores que 10 serão impressos até que pare no 1.
  int n = 10;
  while(n >= 1){    
    System.out.println(n);
    n--;   
  }     
```

### do while

A estrutura `do while` funciona da mesma forma que o while, com a única diferença sendo a checagem da condição, que é feita após executar o loop. Desse jeito, uma iteração é sempre executada nessa estrutura.

```java    
  //Todos os números menores que 10 serão impressos até que pare no 1.
  int n = 10;
  do {
    System.out.println(n);
    n--; 
  } while(n >= 1);       
```

### for each

A estrutura `for each` é uma versão diferente da estrutura `for`, pois ela não precisa de um iterador, e uma variável é utilizada para percorrer uma array ou uma outro conjunto de variáveis.

```java
  //Percorre o vetor de números com a variável numero
  int numeros[] = {1, 2, 3, 4, 5}
  for(int numero: numeros) {
    System.out.println(numero);
  }        
```

### Estruturas de salto:

### continue

A estrutura `continue` age de acordo com o que seu próprio nome diz, pois ela passa por uma parte de um loop e continua depois dela, pulando para uma próxima iteração.

```java    
  //Imprime todos os números de 1 até 10, exceto pelo 5, que é pulado
  for(int i=1; i<10; i++){ 
    if(i == 5){
      continue;
    }
    System.out.println(i);
  }      
```

### break

A estrutura `break` também age de acordo com o que seu próprio nome diz, pois ela quebra o fluxo do programa e sai de um loop (o mais interno, caso tenha um loop dentro de outro) ou `switch case`.

```java    
  //Imprime todos os números de 1 até 5, e sai do loop após o break
  for(int i=1; i<10; i++){ 
    System.out.println(i);
    if(i == 5){
      break;
    }
  }      
```

___
## Referências


1. https://www.tecmundo.com.br/mercado/222806-5-linguagens-programacao-usadas-2021.htm
2. https://mauriciogeneroso.medium.com/java-oca-1z0-808-1-1-java-b%C3%A1sico-como-funciona-o-java-a1b93cea39a4
3. https://www.javatpoint.com/pt/conven%C3%A7%C3%B5es-de-nomenclatura-java
4. https://www.learningjournal.guru/article/programming-in-java/scope-and-lifetime-of-a-variable/
5. https://www.javatpoint.com/static-binding-and-dynamic-binding
6. https://www.javatpoint.com/control-flow-in-java