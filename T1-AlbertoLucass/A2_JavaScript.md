
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

## Referências

https://web.stanford.edu/class/cs98si/slides/overview.html

https://blog.bitsrc.io/how-does-javascript-really-work-part-1-7681dd54a36d

https://www.w3schools.com/js/
