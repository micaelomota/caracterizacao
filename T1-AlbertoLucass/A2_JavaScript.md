# A2 - JavaScript

+ **a) modelo de tradução (compilação, etc.?)**

JavaScript é uma linguagem interpretada, não uma linguagem compilada. Um programa como C ou Java precisa ser compilado antes de ser executado. O código-fonte é passado por um programa chamado compilador, que o traduz em bytecode que a máquina entende e pode executar. Em contraste, o JavaScript não tem etapa de compilação. Em vez disso, um interpretador no navegador lê o código JavaScript, interpreta cada linha e a executa. Os navegadores mais modernos usam uma tecnologia conhecida como compilação Just-In-Time (JIT), que compila JavaScript em bytecode executável quando ele está prestes a ser executado.

![javascript](https://user-images.githubusercontent.com/38790522/135303464-46ddd930-5e15-4474-9678-86a59be4ac26.png)

### Analisando e construindo a árvore

O arquivo JavaScript entra no mecanismo e o analisador faz uma análise lexical que divide o código em tokens para identificar seu significado. Esses tokens formam a AST (Abstract Syntax Tree).

![javascript2](https://user-images.githubusercontent.com/38790522/135303786-3ec01c19-2f18-445e-854f-af7e3ad1836a.png)

Os ASTs desempenham um papel crítico na análise semântica onde o compilador valida o uso correto dos elementos da linguagem e palavras-chave. Mais tarde, os ASTs são usados ​​para gerar o bytecode ou código de máquina real.

![javascript3](https://user-images.githubusercontent.com/38790522/135304069-38df2dc5-21a1-4378-b10c-ff525a9e13cf.png)

* O JavaScript é interpretado por um interpretador denominado Ignition , bem como compilado por um compilador de otimização JIT denominado TurboFan .
* Inicialmente, os ASTs gerados na etapa anterior são dados ao interpretador que gera código de máquina não otimizado rapidamente e a execução pode ser iniciada sem atrasos.
* O Profiler observa o código conforme ele é executado e identifica as áreas onde as otimizações podem ser realizadas. Por exemplo, um loop 'for' em execução 100 vezes, mas produzindo o mesmo resultado em cada iteração.
* Usando este profiler, qualquer código não otimizado é passado para o compilador para realizar otimizações e gerar código de máquina que eventualmente substitui sua contraparte no código não otimizado gerado anteriormente pelo interpretador.
* À medida que o profiler e o compilador fazem alterações constantes no bytecode, o desempenho de execução do JavaScript melhora gradualmente.

+ **b) nomes, variáveis e vinculação**

Existem 3 maneiras de declarar uma variável JavaScript:

* Usando var
* Usando let
* Usando const

Variáveis ​​são contêineres para armazenar dados (valores).

Diferente do var, variáveis ​​definidas com let não podem ser declaradas novamente.

```javascript
let x = "Alberto";

let x = 0;

// SyntaxError: 'x' has already been declared
```
Com var é possível



```javascript
var x = "Alberto";

var x = 0;
```

Já o const se difere um pouco mais. Variáveis ​​definidas com const não podem ser redeclaradas, não podem ser reatribuídas, e possui escopo fechado.

```javascript
const PI = 3.141592653589793;
PI = 3.14;      // This will give an error
PI = PI + 10;   // This will also give an erro
```


### Identificadores JavaScript

Todas as variáveis JavaScript devem ser identificadas com nomes exclusivos .

Esses nomes exclusivos são chamados de identificadores .

Os identificadores podem ser nomes curtos (como x e y) ou nomes mais descritivos (idade, soma, volumeTotal).

As regras gerais para construir nomes para variáveis ​​(identificadores únicos) são:

* Os nomes podem conter letras, dígitos, sublinhados e cifrões.
* Os nomes devem começar com uma letra
* Os nomes também podem começar com $ e _ 
* Os nomes diferenciam maiúsculas de minúsculas (y e Y são variáveis ​​diferentes)
* Palavras reservadas (como palavras-chave JavaScript) não podem ser usadas como nomes
* Os identificadores de JavaScript diferenciam maiúsculas de minúsculas.

### Tipos de dados JavaScript

Variáveis ​​JavaScript podem conter números como 100 e valores de texto como "Alberto".

Na programação, os valores de texto são chamados de strings.

JavaScript pode lidar com muitos tipos de dados, tais como objetos, números e strings.

As strings são escritas entre aspas duplas ou simples. Os números são escritos sem aspas.

Se um número é colocado entre aspas, ele será tratado como uma string.

+ **c) escopo, tempo de vida e ambientes de referência.**

O escopo determina a acessibilidade (visibilidade) das variáveis.

JavaScript tem 3 tipos de escopo:

* Escopo do bloco
* Escopo de função
* Âmbito global

### Escopo do Bloco

Antes do ES6(2015), JavaScript tinha apenas escopo global e escopo de função.

ES6 introduziu duas novas palavras-chave JavaScript importantes: let e const.

Essas duas palavras-chave fornecem Block Scope em JavaScript.

Variáveis ​​declaradas dentro de um bloco {} não podem ser acessadas de fora do bloco:

```javascript
{
  let x = 2;
}
// x can NOT be used here
```

Variáveis ​​declaradas com a palavra var NÃO podem ter escopo de bloco.

Variáveis ​​declaradas dentro de um bloco {} podem ser acessadas de fora do bloco.

```javascript
{
  var x = 2;
}
// x CAN be used here
```

### Escopo Local
Variáveis ​​declaradas em uma função JavaScript tornam-se LOCAIS para a função.

```javascript
// code here can NOT use carName

function myFunction() {
  let carName = "Volvo";
  // code here CAN use carName
}

// code here can NOT use carName
```

Variáveis ​​locais têm escopo de função:

* Eles só podem ser acessados ​​de dentro da função.

Como as variáveis ​​locais só são reconhecidas dentro de suas funções, as variáveis ​​com o mesmo nome podem ser usadas em funções diferentes.

Variáveis ​​locais são criadas quando uma função é iniciada e excluídas quando a função é concluída.

### Escopo de Função

JavaScript tem escopo de função: cada função cria um novo escopo.

Variáveis ​​definidas dentro de uma função não são acessíveis (visíveis) de fora da função.

Variáveis declaradas com var, let e const são bastante semelhantes quando declarados dentro de uma função.

Todos eles têm escopo de função:
```javascript
function myFunction() {
  var carName = "Volvo";   // Function Scope
}
```

```javascript
function myFunction() {
  let carName = "Volvo";   // Function Scope
}
```

```javascript
function myFunction() {
  const carName = "Volvo";   // Function Scope
}
```

### Âmbito global
Variáveis ​​declaradas globalmente (fora de qualquer função) têm escopo global .

Variáveis globais podem ser acessadas de qualquer lugar em um programa JavaScript.

Variáveis declaradas com var, let e constsão bastante semelhantes quando declarado fora de um bloco.

Todos eles têm escopo global :

```javascript
var x = 2;       // Global scope
```

```javascript
let x = 2;       // Global scope
```

```javascript
const x = 2;       // Global scope
```


### O tempo de vida das variáveis ​​JavaScript
O tempo de vida de uma variável JavaScript começa quando ela é declarada.

Variáveis ​​de função (locais) são excluídas quando a função é concluída.

Em um navegador da web, as variáveis ​​globais são excluídas quando você fecha a janela do navegador (ou guia).

# Estruturas de controle em Javascript

Normalmente, as instruções em um programa JavascriptScript são executadas sequencialmente, ou seja, na ordem em que são escritas. Isso é chamado de execução sequencial. É possível transferir o controle para um local desejado em um programa por meio da estrutura de controle. Estruturas de controle são blocos de programação que podem mudar o caminho que tomamos por meio dessas instruções. Javascript permite principalmente tipos de estruturas de controle, que incluem:


1. Estrutura de controle condicional(Ramificação):

 * [if](#if)
 
 * [if else](#if-else)

 * [if else if](#if-else-if) 

 * [nested if](#nested-if)

 * [switch](#switch)  

2. Estrutura de controle de salto:

 * [break](#break) 
 

 * [continue](#continue) 

 * [return](#return) 

3. Estrutura de controle iterativo(loops):

 * [for loop](#for-loop) 

 * [while loop](#while-loop) 

 * [do while loop](#do-while-loop) 

 * [for each(enhanced for) loop](#for-each-loop) 

## 1. Estrutura de controle condicional(Ramificação):

### If
A estrutura **se** também é chamada de declaração condicional. No **if**, as instruções são executadas apenas quando a condição é verdadeira. Ele omite as declarações baseadas em condição quando a condição é falsa. Chaves não são necessárias se apenas uma afirmação estiver relacionada à condição.

![if](https://user-images.githubusercontent.com/38790522/137969740-44f47a02-4a83-42da-9d9c-0ee6f046f3ae.jpg)

Sintaxe:

~~~
if(condição){
  // afirmações
}
~~~

Exemplo:

```javascript
var x = 2
if(x > 0)
  console.log('positivo')
```

### If-else
As instruções no bloco **if** são executadas apenas quando a condição é verdadeira e as instruções no bloco **else** são executadas apenas quando a condição é falsa.

![if-else](https://user-images.githubusercontent.com/38790522/137970617-5481adab-8b6b-4563-aca4-3c2b08268a73.jpg)

Sintaxe:

~~~
if(condição){
  // afirmações
}
else {
  // afirmações
}
~~~

Exemplo:

```javascript
var x = 2
var y = 1
if(x > y)
  console.log('x é o maior')
else
  console.log('y é o maior')
```

### if-else-if
As instruções são executadas em loops apenas quando as condições correspondentes são verdadeiras. As instruções no bloco **else** final são executadas quando todas as outras condições são falsas. O controle verifica uma condição apenas quando todas as condições mencionadas anteriormente são falsas.

![if-else-if](https://user-images.githubusercontent.com/38790522/137971478-037cd8a6-4a18-432f-83a0-688a496d493f.jpg)

Sintaxe:

~~~
if(condição1) {
  //Afirmações
} else if(condição2) {
  //Afirmações
} else if(condição3) {
  //Afirmações
}
else {
  //Afirmações
}
~~~

Exemplo:

```javascript
var x = 2
if(x > 0)
  console.log('positivo')
else if(x < 0)
  console.log('negativo')
else
  console.log('zero')
```

### nested-if
Escrevendo if em outro if é chamado de **if aninhado**. O **if** interno é processado apenas quando a condição do **if** externo é verdadeira. Portanto, as instruções que estão dentro do segundo **if** são executadas apenas quando a condição1 e a condição2 são verdadeiras.

![nested if](https://user-images.githubusercontent.com/38790522/137972012-9eb18dc2-f67e-4d2b-b39f-3fd28fe6e678.jpg)

Sintaxe:

~~~
if(condição1) {
   if(condição2) {
      //Afirmações
   } 
}
~~~

Exemplo:

```javascript
var a = 2
var b = 1
var c = 0
if(a > b) {
  if(a > c)
     console.log('a é o maior')
}
```

### switch
**Switch** é semelhante a **if else if**. A instrução 1 é executada quando a variável é igual a constant1 e assim por diante. O controle vem para a parte "default" quando todos os casos(constantes), que foram mencionados, não coincidem com o valor da variável. Aqui break e default são opcionais. Quando não há interrupção para um caso, ele continua até encontrar uma interrupção ou o fim do loop do **switch**.

![switch](https://user-images.githubusercontent.com/38790522/137973362-956ff385-565f-4a6d-8a8e-a05c32c6e918.jpg)

Sintaxe:

~~~
switch(variavel){
  case constant1: //Afirmações
    break
  case constant2: //Afirmações
    break
  default: //Afirmações
    break
}
~~~

Exemplo:

```javascript
var x = 2
var y = 1
var k = x - y
switch(k){
  case 0: console.log(' x e y são iguais')
    break
  default: console.log(' x e y não são iguais')
    break
}
```

## 2. Estrutura de controle de salto:

### break
**Break** fecha o controle do loop iterativo correspondente. Break é válido apenas em **loops iterativos** e **switch**. Break é usado para tirar o controle dos loops iterativos de forma intermediária.

![break](https://user-images.githubusercontent.com/38790522/137974352-8719b7a4-b37b-4fdc-a126-44cc35fc359b.jpg)


Exemplo:

```javascript
for( var i=1  i<=10 i++) {
  console.log('olá')
  if(i==5)
    break
}
/* imprime olá 5 vezes */
```

### continue
**Continue** move o controle para a primeira instrução no loop iterativo correspondente. "Continue" é válido apenas em loops iterativos. Ele omite as instruções escritas após "continue" e reinicia o loop iterativo.

![continue](https://user-images.githubusercontent.com/38790522/137975812-335e13c4-4689-4897-b138-ed37565770b0.jpg)

Exemplo:

```javascript
var i=0
while(true){
  console.log('olá')
  i++
  if(i<5)
    continue
  break
}
/* imprime olá 5 vezes */
```

### return
**Return** é usado em funções. Ele move o controle para a função de chamada do módulo chamado. "return" também é usado para retornar valores ao ponto onde é chamado, mas é possível retornar apenas um valor por vez.

Exemplo:

```javascript
function sum( x, y) {
    return x + y
  }
var k = sum(30,40)
// Aqui, a função 'soma' retorna 70 na variável k com a chamada acima.
```

## 3. Estrutura de controle iterativo(loops):

### for loop
As instruções são executadas enquanto a condição for verdadeira. Geralmente, a expressão1 inclui instruções de inicialização e a expressão2 inclui instruções que usam operadores de incremento, decremento e atribuição.

![for loop](https://user-images.githubusercontent.com/38790522/137976775-1a5b51c5-b3bb-4475-ad13-e0c62610d5a1.jpg)

Sintaxe:

~~~
for(expressão1 condição expressão2) {
 //Afirmações
}
~~~

Exemplo:

```javascript
for( var i=1;  i<=10 ; i++)
  console.log('olá')
/* imprime olá 10 vezes */
```

### while-loop
As instruções são executadas enquanto a condição for verdadeira. Ele verifica a condição primeiro e executa as instruções depois. Também é chamado de loop de controle de entrada.

![while loop](https://user-images.githubusercontent.com/38790522/137977107-c84867db-0fa0-411e-a483-8107ceb68cae.jpg)

Sintaxe:

~~~
while( condição ) {
 //Afirmações
}
~~~

Exemplo:

```javascript
var i = 0
while(i <10) {
  console.log('olá')
  i = i + 1
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
} while(condição)
~~~

Exemplo:

```javascript
var i=0
do {
  console.log('olá')
  i=i+1
} while( i<10 )
/* imprime olá 10 vezes */
```

### for-each-loop
O **loop for** aprimorado é chamado **for each** loop. Isso é mais usado com matrizes e enumerações. Geralmente, para acessar os elementos do array, usamos índices. Mas, usando **for-each**, podemos ter acesso direto a cada elemento do array sem índices.

Sintaxe:

~~~
for(variável: expressão) {
 //Afirmações
}
~~~

Exemplo:

```javascript
var arrayNumeros = [1,2,3,4,5,6]
function verificaPares(elemento){
    if(elemento % 2 == 0) 
    console.log(elemento)
}
arrayNumeros.forEach(verificaPares)
/*saída:
2
4
6
*/
```


## Referências

https://web.stanford.edu/class/cs98si/slides/overview.html

https://blog.bitsrc.io/how-does-javascript-really-work-part-1-7681dd54a36d

https://www.w3schools.com/js/

https://www.javascriptinstitute.org/javascript-tutorial/control-structures/

https://en.wikibooks.org/wiki/JavaScript/Control_structures#:~:text=The%20control%20structures%20within%20JavaScript,of%20a%20block%20of%20code.
