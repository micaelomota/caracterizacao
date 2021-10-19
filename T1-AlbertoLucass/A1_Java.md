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


# Estruturas de controle em Java

Normalmente, as instruções em um programa Java são executadas sequencialmente, ou seja, na ordem em que são escritas. Isso é chamado de execução sequencial. É possível transferir o controle para um local desejado em um programa por meio da estrutura de controle. Estruturas de controle são blocos de programação que podem mudar o caminho que tomamos por meio dessas instruções. Java permite principalmente tipos de estruturas de controle, que incluem:


1. Estrutura de controle condicional (Ramificação):

 * [if](#if)
 
 * [if else](#if-else)

 * [if else if](#if-else-if) 

 * [nested if](#nested-if)

 * [switch](#switch)  

2. Estrutura de controle de salto:

 * [break](#break) 

 * [labelled break](#labelled-break) 

 * [continue](#continue) 

 * [labelled continue](#labelled-continue) 

 * [return](#return) 

3. Estrutura de controle iterativo (loops):

 * [for loop](#for-loop) 

 * [while loop](#while-loop) 

 * [do while loop](#do-while-loop) 

 * [for each (enhanced for) loop](#for-each-loop) 

## 1. Estrutura de controle condicional (Ramificação):

### If
A estrutura **se** também é chamada de declaração condicional. No **if**, as instruções são executadas apenas quando a condição é verdadeira. Ele omite as declarações baseadas em condição quando a condição é falsa. Chaves não são necessárias se apenas uma afirmação estiver relacionada à condição.

![if](https://user-images.githubusercontent.com/38790522/137969740-44f47a02-4a83-42da-9d9c-0ee6f046f3ae.jpg)

Sintaxe:

~~~
if (condição){
  // afirmações
}
~~~

Exemplo:

```java
int x = 2;
if (x > 0)
  System.out.println (“positivo”);
```

### If-else
As instruções no bloco **if** são executadas apenas quando a condição é verdadeira e as instruções no bloco **else** são executadas apenas quando a condição é falsa.

![if-else](https://user-images.githubusercontent.com/38790522/137970617-5481adab-8b6b-4563-aca4-3c2b08268a73.jpg)

Sintaxe:

~~~
if (condição){
  // afirmações
}
else {
  // afirmações
}
~~~

Exemplo:

```java
int x = 2;
int y = 1;
if (x > y)
  System.out.println (“x é o maior”);
else
  System.out.println (“y é o maior”);
```

### if-else-if
As instruções são executadas em loops apenas quando as condições correspondentes são verdadeiras. As instruções no bloco **else** final são executadas quando todas as outras condições são falsas. O controle verifica uma condição apenas quando todas as condições mencionadas anteriormente são falsas.

![if-else-if](https://user-images.githubusercontent.com/38790522/137971478-037cd8a6-4a18-432f-83a0-688a496d493f.jpg)

Sintaxe:

~~~
if (condição1) {
  //Afirmações
} else if (condição2) {
  //Afirmações
} else if (condição3) {
  //Afirmações
}
else {
  //Afirmações
}
~~~

Exemplo:

```java
int x = 2;
if (x > 0)
  System.out.println (“positivo”);
else if (x < 0)
  System.out.println (“negativo”);
else
  System.out.println (“zero”);
```

### nested-if
Escrevendo if em outro if é chamado de **if aninhado**. O **if** interno é processado apenas quando a condição do **if** externo é verdadeira. Portanto, as instruções que estão dentro do segundo **if** são executadas apenas quando a condição1 e a condição2 são verdadeiras.

![nested if](https://user-images.githubusercontent.com/38790522/137972012-9eb18dc2-f67e-4d2b-b39f-3fd28fe6e678.jpg)

Sintaxe:

~~~
if (condição1) {
   if (condição2) {
      //Afirmações
   } 
}
~~~

Exemplo:

```java
int a = 2;
int b = 1;
int c = 0;
if (a > b) {
  if (a > c)
     System.out.println (“a é o maior”);
}
```

### switch
**Switch** é semelhante a **if else if**. A instrução 1 é executada quando a variável é igual a constant1 e assim por diante. O controle vem para a parte “default” quando todos os casos (constantes), que foram mencionados, não coincidem com o valor da variável. Aqui break e default são opcionais. Quando não há interrupção para um caso, ele continua até encontrar uma interrupção ou o fim do loop do **switch**.

![switch](https://user-images.githubusercontent.com/38790522/137973362-956ff385-565f-4a6d-8a8e-a05c32c6e918.jpg)

Sintaxe:

~~~
switch(variavel){
  case constant1: //Afirmações
    break;
  case constant2: //Afirmações
    break;
  default: //Afirmações
    break;
}
~~~

Exemplo:

```java
int x = 2
int y = 1;
int k = x - y;
switch (k){
  case 0: System.out.println (“ x e y são iguais”);
    break;
  default: System.out.println (“ x e y não são iguais”);
    break;
}
```

## 2. Estrutura de controle de salto:

### break
**Break** fecha o controle do loop iterativo correspondente. Break é válido apenas em **loops iterativos** e **switch**. Break é usado para tirar o controle dos loops iterativos de forma intermediária.

![break](https://user-images.githubusercontent.com/38790522/137974352-8719b7a4-b37b-4fdc-a126-44cc35fc359b.jpg)


Exemplo:

```java
for (int i=1 ; i<=10; i++) {
  System.out.println(“olá”);
  if (i==5)
    break;
}
/* imprime olá 5 vezes */
```

### labelled break
A quebra rotulada fecha o controle do loop iterativo rotulado. A necessidade de interrupção rotulada surge quando precisamos parar a execução do loop externo com base na condição escrita no loop interno. O loop iterativo rotulado é um loop iterativo normal com um rótulo fornecido a ele.

![labelled break](https://user-images.githubusercontent.com/38790522/137974731-892f82b6-bd9d-4cc2-a7bc-9cf2e0a5f12f.jpg)

Exemplo:

```java
ABC:
for ( int i=1 ; i<=10; i++) {
  System.out.println(“Oi”);
  for (int j=1 ; j<=10;j++) {
    System.out.println(“Olá”);
    if (j==2)
      break ABC;
  }
}
/*
Saída:
Oi
Olá
Olá */
```

### continue
**Continue** move o controle para a primeira instrução no loop iterativo correspondente. “Continue” é válido apenas em loops iterativos. Ele omite as instruções escritas após “continue” e reinicia o loop iterativo.

![continue](https://user-images.githubusercontent.com/38790522/137975812-335e13c4-4689-4897-b138-ed37565770b0.jpg)

Exemplo:

```java
int i=0;
while (true){
  System.out.println (“olá”);
  i++;
  if (i<5)
    continue;
  break;
}
/* imprime olá 5 vezes */
```

### labelled continue
**Labeled continue** move o controle para a primeira instrução no loop iterativo rotulado . Ele omite as instruções escritas após “continue” e reinicia o loop iterativo rotulado.

![labelled continue](https://user-images.githubusercontent.com/38790522/137975748-debac5f6-48d4-454e-9c46-fb17282a4c18.jpg)


Exemplo:

```java
int i=0;
XYZ:
while (true) {
  System.out.println(“Oi”);
  while (true) {
    System.out.println(“Olá”);
    i++;
    if (i<2)
      break XYZ;
  }
  break XYZ;
}
/*
Saída
Oi
Olá
*/
```

### return
**Return** é usado em funções. Ele move o controle para a função de chamada do módulo chamado. "return" também é usado para retornar valores ao ponto onde é chamado, mas é possível retornar apenas um valor por vez.

Exemplo:

```java
int sum(int x, int y) {
  return x + y;
}
int k = sum(30,40);
// Aqui, a função “soma” retorna 70 na variável k com a chamada acima.
```

## 3. Estrutura de controle iterativo (loops):

### for loop
As instruções são executadas enquanto a condição for verdadeira. Geralmente, a expressão1 inclui instruções de inicialização e a expressão2 inclui instruções que usam operadores de incremento, decremento e atribuição.

![for loop](https://user-images.githubusercontent.com/38790522/137976775-1a5b51c5-b3bb-4475-ad13-e0c62610d5a1.jpg)

Sintaxe:

~~~
for(expressão1; condição; expressão2) {
 //Afirmações
}
~~~

Exemplo:

```java
for(int i=1 ; i<=10 ; i++)
  System.out.println (“olá”);
/* imprime olá 10 vezes */
```

### while-loop
As instruções são executadas enquanto a condição for verdadeira. Ele verifica a condição primeiro e executa as instruções depois. Também é chamado de loop de controle de entrada.

![while loop](https://user-images.githubusercontent.com/38790522/137977107-c84867db-0fa0-411e-a483-8107ceb68cae.jpg)

Sintaxe:

~~~
while ( condição ) {
 //Afirmações
}
~~~

Exemplo:

```java
int i = 0;
while (i <10) {
  System.out.println (“olá”);
  i = i + 1;
} 
/* imprime olá 10 vezes */
```

### do-while-loop
As instruções são executadas enquanto a condição for verdadeira. É semelhante a **while**, mas executa as instruções primeiro e verifica a condição depois. Ele garante pelo menos uma execução de tempo. É chamado de loop de controle de saída.

![do while loop](https://user-images.githubusercontent.com/38790522/137977619-07eb0a50-1c52-40ff-bbe8-4a10511ed56f.jpg)

Sintaxe:

~~~
do {
 //Afirmações
} while(condição);
~~~

Exemplo:

```java
int i=0;
do {
  System.out.println (“olá”);
  i=i+1;
} while( i<10 );
/* imprime olá 10 vezes */
```

### for-each-loop
O **loop for** aprimorado é chamado **for each** loop. Ele é apresentado no J2SE 5.0. Isso é mais usado com matrizes e enumerações. Geralmente, para acessar os elementos do array, usamos índices. Mas, usando **for-each**, podemos ter acesso direto a cada elemento do array sem índices.

Sintaxe:

~~~
for (variável: expressão) {
 //Afirmações
}
~~~

Exemplo:

```java
int x[]= {10,20,30};
for (int k : x)
  System.out.print(k+” “);
// O código acima é impresso: 10 20 30
```



## Referências

https://stackoverflow.com/questions/1326071/is-java-a-compiled-or-an-interpreted-programming-language

https://www.oracle.com/java/technologies/javase/codeconventions-namingconventions.html

https://www.codecademy.com/articles/variable-scope-in-java

https://www.learningjournal.guru/article/programming-in-java/scope-and-lifetime-of-a-variable/

http://www.smartclass.co/2011/10/control-structure-in-java.html

https://javagoal.com/control-structures-in-java/
