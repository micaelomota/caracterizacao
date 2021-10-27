
# Atividade 1 – Java Script
## Modelo de tradução

JavaScript é uma linguagem de programação leve e interpretada. O navegador recebe o código JavaScript em sua forma de texto original e executa o script a partir dele. Do ponto de vista técnico, a maioria dos intérpretes modernos de JavaScript realmente usa uma técnica chamada compilação just-in-time para melhorar o desempenho, o código-fonte JavaScript é compilado em um formato binário mais rápido enquanto o script está sendo usado, para que possa ser executado o mais rápido possível. No entanto, o JavaScript ainda é considerado uma linguagem interpretada, pois a compilação é manipulada em tempo de execução, e não antes.
Os compiladores de JavaScript mais conhecidos são o V8 e o Rhino, que transformam o código para C++ e JAVA Bytecode, estes compiladores suportam e utilizam o JIT nas suas estratégias de compilação.

## Nomes, variáveis e vinculação

### Nomes

Segundo Douglas Crockford, todos os padrões descritos em javascript.crockford.com/code.html são os mesmos utilizados em Java.

**Nomeando arquivos**

Os arquivos, tanto .js quanto .css devem ter seus nomes desta forma: nome-do-arquivos.css ou apenas nome-do-arquivos.js. Caso o arquivo faça referência a um framework ou biblioteca use por exemplo: bootstrap-nome-do-arquivos.js ou jquery-nome-do-arquivos.js.

**Funções**

Devem começar com letra minúscula e para cada palavra, a primeira letra deve ser maiúscula (lowerCamelCase).

**Variáveis**

As variáveis devem começar com letra minúscula e para cada palavra, a primeira letra deve ser maiúscula (lowerCamelCase).

**Parâmetros**

Os parâmetros devem começar com letra minúscula e para cada palavra, a primeira letra deve ser maiúscula (lowerCamelCase). Os parâmetros não possuem tipos.

### Variáveis

**var**

Declara uma variável, opcionalmente, inicializando-a com um valor.

**let**

Declara uma variável local de escopo do bloco, opcionalmente, inicializando-a com um valor.

**const**

Declara uma constante de escopo de bloco, apenas de leitura

Variáveis let não podem ser redeclaradas, variáveis const não podem ser redeclaradas ou reatribuídas.

**Variável de instância**

Variável cujo valor é específico ao objeto e não à classe. Uma variável de instância em geral possui uma valor diferente em cada objeto representante da classe.

**Variável de classe**

Uma variável cujo valor é comum a todos os objetos representantes da classe. Mudar o valor de uma variável de classe em um objeto automaticamente muda o valor para todos os objetos instâncias da mesma classe. Um exemplo óbvio de uma variável de classe seria o número de instâncias desta classe que já foram criadas. Para declarar uma variável de classe, acrescenta-se a palavra-chave static.

**Variáveis globais**

Acessiveis em qualquer local do programa

**Variáveis locais**

Visiveis apenas no local ou escopo onde foram definidas.

### Vinculação

A vinculação em Java Script é dinâmica ou seja em tempo de execução a tipagem da variável é definida com base no valor atribuido.

## Escopo, tempo de vida e ambientes de referência

**Escopo do Bloco**

Uma variável declarada dentro de blocos são visiveis apenas dentro deles. As palavras chave let e const proporcionam o escopo de bloco.
Tempo de vida igual a duração da execução do bloco, ao ser finalizado a variável também é.

**Escopo Local**

Uma variável declarada dentro de uma função é local, as variáveis locais só são reconhecidas dentro de suas funções.

Tem tempo de vida referente o tempo de execução da função ou metodo, ao ser finalizado a variável expira.

**Escopo Global**

Variáveis globais são visiveis em qualquer contexto, são declaradas fora das funções. Tempo de vida é a duração até a finalização do programa.

## Estruturas de controle

**For**

Um laço for é repetido até que a condição especificada seja falsa. O laço for no JavaScript é similar ao Java e C. Uma declaração for é feita da seguinte maneira:

```
for ([expressaoInicial]; [condicao]; [incremento])
  declaracao
```

Quando um for é executado, ocorre o seguinte:

1. A expressão expressao Inicial é inicializada e, caso possível, é executada. Normalmente essa expressão inicializa um ou mais contadores, mas a sintaxe permite expressões de qualquer grau de complexidade. Podendo conter também declaração de variáveis.

2. A expressão condicao é avaliada. caso o resultado de condicao seja verdadeiro, o laço é executado. Se o valor de condicao é falso, então o laço terminará. Se a expressão condicao é omitida, a condicao é assumida como verdadeira.

3. A instrução é executada. Para executar múltiplas declarações, use uma declaração em bloco ({ ... }) para agrupá-las.

4. A atualização da expressão incremento, se houver, executa, e retorna o controle para o passo 2.

**Declaração do...while**

A instrução do...while repetirá até que a condição especificada seja falsa.

```
do
  declaracao
while (condicao);
```

A instrução será executada uma vez antes da condição ser verificada. Para executar multiplas instruções utilize uma declaração de bloco ({ ... }) para agrupá-las. Caso a condicao seja verdadeira, então o laço será executado novamente. Ao final de cada execução, a condicao é verificada. Quando a condição contida no while for falsa a execução do laço é terminada e o controle é passado para a instrução seguinte a do...while.

Exemplo:

```
do {
  i += 1;
  console.log(i);
} while (i < 5);
```

**Declaração while**

Uma declaração while executa suas instruções, desde que uma condição especificada seja avaliada como verdadeira. Segue uma declaração while: 

```
while (condicao)
  declaracao
  ```
Se a condição se tornar falsa,  a declaração dentro do laço para a execução e o controle é passado para a instrução após o laço.


O teste da condição ocorre antes que o laço seja executado. Desta forma se a condição for verdadeira o laço executará e testará a condição novamente. Se a condição for falsa o laço termina e passa o controle para as instruções após o laço.

Para executar múltiplas declarações, use uma declaração em bloco ({ ... }) para agrupar essas declarações.

```
n = 0;
x = 0;
while (n < 3) {
  n++;
  x += n;
}
```

**Declaração label**

Um label provê um identificador que permite que este seja referenciado em outro lugar no seu programa. Por exemplo, você pode usar uma label para identificar um laço, e então usar break ou continue para indicar quando o programa deverá interromper o laço ou continuar sua execução.

Sintaxe da instrução label:

label : declaracao
Um label pode usar qualquer idenficador que não seja uma palavra reservada do JavaScript. Você pode identificar qualquer instrução com um label.

Exemplo

```
markLoop:
while (theMark == true) {
   facaAlgo();
}
```

**Declaração break**

Use break para terminar laços, switch, ou um conjunto que utiliza label.

Quando você utiliza break sem um label, ele encerrará imediatamente o laço mais interno while, do-while, for, ou switch e transferirá o controle para a próxima instrução.

Quando você utiliza break com um label, ele encerrará o label específico.

Sintaxe do break:

break;

break label;

Na primeira opção será encerrado o laço de repetição mais interno ou switch. Já na segunda opção será encerrada o bloco de código referente a label.

```
for (i = 0; i < a.length; i++) {
  if (a[i] == theValue) {
    break;
  }
}
```

```
var x = 0;
var z = 0
labelCancelaLaco: while (true) {
  console.log("Laço exterior: " + x);
  x += 1;
  z = 1;
  while (true) {
    console.log("Laço interior: " + z);
    z += 1;
    if (z === 10 && x === 10) {
      break labelCancelaLaco;
    } else if (z === 10) {
      break;
    }
  }
}
```
**Declaração continue**

A declaração continue pode ser usada para reiniciar uma instrução while, do-while, for, ou label.

Quando você utiliza continue sem uma label, ele encerrará a iteração atual mais interna de uma instrução while, do-while, ou for e continuará a execução do laço a partir da próxima iteração. Ao contrário da instrução break, continue não encerra a execução completa do laço. Em um laço while, ele voltará para a condição. Em um laço for, ele pulará para a expressão de incrementação.

Quando você utiliza continue com uma label, o continue será aplicado ao laço identificado por esta label. 
Segue a sintaxe do continue:

continue;
continue label;

```
i = 0;
n = 0;
while (i < 5) {
  i++;
  if (i == 3) {
    continue;
  }
  n += i;
}
```

```
checkiandj:
  while (i < 4) {
    console.log(i);
    i += 1;
    checkj:
      while (j > 4) {
        console.log(j);
        j -= 1;
        if ((j % 2) == 0) {
          continue checkj;
        }
        console.log(j + " é estranho.");
      }
      console.log("i = " + i);
      console.log("j = " + j);
  }
 ```
 **Declaração for...in**
 
A declaração for...in executa iterações a partir de uma variável específica, percorrendo todas as propriedades de um objeto.
Para cada propriedade distinta, o JavaScript executará uma iteração. Segue a sintaxe:

```
for (variavel in objeto) {
  declaracoes
}
```

Exemplo:

```
function dump_props(obj, obj_name) {
  var result = "";
  for (var i in obj) {
    result += obj_name + "." + i + " = " + obj[i] + "<br>";
  }
  result += "<hr>";
  return result;
}
```
**Declaração for...of**
 A declaração for...of cria uma laço com objetos interativos incluindo Array, Map, Set, assim por conseguinte , executando uma iteração para o valor de cada propriedade distinta.
 
```
for (variavel of objeto) {
  declaracoes
}
```

O exemplo a seguir mostra a diferença entre o for...of e o for...in. Enquanto o for...in interage com o nome das propriedades, o for...of interage com o valor das propriedades.
```
let arr = [3, 5, 7];
arr.foo = "hello";

for (let i in arr) {
   console.log(i); // logs "0", "1", "2", "foo"
}

for (let i of arr) {
   console.log(i); // logs "3", "5", "7"
}
```
