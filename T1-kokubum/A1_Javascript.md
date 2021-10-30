# Trabalho 1 - Atividade A1

### Linguagem de Programação: Javascript

#

## Modelo de compilação:

A linguagem Javascript normalmente é definida como uma linguagem interpretada, ou seja, que não passa pelo processo de parser/compilação, isso se dá muito ao fato de não termos acesso ao binário gerado pelo processo da compilação como nas linguagens padrões, porém isso é um equívoco, visto que antes de ser executado pelo interpretador, o programa definido sofrerá um processo de parser para uma AST(Abstract Syntax Tree - Árvore Sintática Abstrata) e conversão da AST para um tipo de byte code otimizado pelo compilador JIT sendo esse executado pela VM do Javascript. Então sim, podemos dizer que a linguagem Javascript apesar de ser executada no momento, como linguagens de script interpretada, ela também possui aspectos de compilação durante esse processo (parser).

## Nomes, variáveis e vinculação:

### Nomes

#

O Javascript, diferente do Java, não tem um nível de convenção de nomenclatura tão elevado e reconhecido, porêm a comunidade sempre trata de defender determinados padrões a serem utilizados como por exemplo:

- Nome de classes devem seguir o padrão PascalCase.
- Nome de variáveis e funções/métodos devem seguir o padrão CamelCase.
- Constantes devem possuir todas suas letras maiúsculas.
- Os módulos normalmente seguem o padrão CamelCase, a não ser que representem uma única classe, então normalmente é seguido o PascalCase com o nome da classe em questão.

Obs: É válido lembrar que todas essas definições são padrões adotados pela comunidade, mas que podem variar de desenvolvedor para desenvolvedor.

### Variáveis

#

- Variável global: Variáveis que estão disponíveis para acesso em qualquer local do programa, ou seja, são as variáveis que estão linkadas ao objeto global que representa o programa em execução.
- Varável local: São variáveis que estão visíveis apenas dentro do escopo em que foram definidas, podendo esse ser um escopo de uma função, ou de um bloco (if/while)
- Variável de classe: Variáveis de acesso apenas a classe (declarados como "static").
- Variável de instância: Variáveis que foram definidas no corpo de um objeto, e não dentro de métodos do mesmo, sendo essas, nada mais que variáveis locais.

### Vinculação

#

- Dinâmica: O javascript durante as declarações e atribuições de valores as variáveis, sofre o que chamamos de vinculação dinâmica, ja que, em tempo de execução a tipagem daquela variável atribuida será definida com base no valor o qual foi utilizado.

Ex:

```
let n = "string";  // n será tipado como string
let a = 2;   // a será tipado como um number
```

## Escopo, Tempo De Vida e Ambientes de Referência

### Escopo e tempo de vida:

#

- Escopo Global

Uma variável declarada fora de uma função é uma variável global, o que faz com que seu valor seja acessível em todos os contextos.

Tempo de vida - Para essa situação a variável tem o tempo de vida igual ao tempo de execução do programa, visto que a mesma está associada ao objeto global, e esse escopo só é removido, quando o programa é finalizado.

- Escopo Local

Uma variável declarada dentro de uma função é local, o que faz com que ela seja criada e destruída sempre que a função é executada não podendo ser acessada fora da função.

Tempo de vida - Para essa situação, como foi mencionado acima, a variável tem o tempo de vida de duração da execução desse subprograma(função/método), de forma que no momento que a função for finalizada, ela deixa de existir.

- Escopo de Bloco

Uma variável declarada dentro de blocos ou sub-blocos (if/while/for-loop) serão acessadas apenas dentro dos mesmos.

Tempo de vida - Para essa situação a variável sobrevive durante a execução do bloco em questão, por exemplo, se dentro do "if" uma variável "a" for declarada, então, quando esse bloco for finalizado, a variável será também destruida.

### Ambientes de Referência: Estático e Dinâmico

#

- Estático: Escopo que é definido antes da execução do programa, com base na estrutura léxica do mesmo, ou seja, baseado sempre onde cada uma de suas instruções foram declaradas.

Ex:

```
var x = 10;       // Escopo global - pode ser acessada em qualquer lugar, inclusive em f
function f() {
    var y = 20;   // Escopo local - pode ser acessada somente dentro de f
}
```

- Dinâmico: Escopo que é definido com base na pilha de execução.

Ex:

```
var obj = {
  minhaFunc2: minhaFunc
}
function minhaFunc(){
  console.log(this);
}

obj.minhaFunc2(); // referência do obj

minhaFunc(); //window (objeto global)
```

## Estruturas de Controle:

#

Na linguagem Javascript existem algumas estruturas de controle que lhe permitem modificar o fluxo de execução de um programa. Estas estruturas permitem executar o código baseado em condições lógicas ou um número determinado de vezes.

### **1. Condicional:**

#

- **if/else**

```
if (cipher_char === from_char) {
   result = result + to_char;
   x++;
} else {
   result = result + clear_char;
}
```

- **if/else if**

```
if (condição1)
   instrução1 é executada se a condição 1 for verdadeira
else if (condição2)
   instrução2 é executada se a condição1 é falsa e a condição2 é verdadeira
else if (condição3)
   instrução3 é executada se a condição2 é falsa e a condição3 é verdadeira
...
else
   instruçãoN
```

Múltiplas condicionais if ... else podem ser aninhados quando necessário. Observe que não existe elseif (em uma palavra). O correto é a instrução com espaços (else if), conforme abaixo:

### **2. Repetição:**

#

- **for_statement**

```
for ([expressaoInicial]; [condicao]; [incremento])
  declaracao
```

1.1 A expressão expressao Inicial é inicializada e, caso possível, é executada. Normalmente essa expressão inicializa um ou mais contadores, mas a sintaxe permite expressões de qualquer grau de complexidade. Podendo conter também declaração de variáveis.

1.2 A expressão condicao é avaliada. caso o resultado de condicao seja verdadeiro, o laço é executado. Se o valor de condicao é falso, então o laço terminará. Se a expressão condicao é omitida, a condicao é assumida como verdadeira.

1.3 A instrução é executada. Para executar múltiplas declarações, use uma declaração em bloco ({ ... }) para agrupá-las.

1.4 A atualização da expressão incremento, se houver, executa, e retorna o controle para o passo 2.

- **do...while_statement**

```
do
  declaracao
while (condicao);
```

A instrução será executada uma vez antes da condição ser verificada. Para executar multiplas instruções utilize uma declaração de bloco ({ ... }) para agrupá-las.

- **while_statement**

```
while (condicao)
  declaracao
```

Uma declaração while executa suas instruções, desde que uma condição especificada seja avaliada como verdadeira.

- **for...in_statement**

```
for (variavel in objeto) {
  declaracoes
}
```

A declaração for...in executa iterações a partir de uma variável específica, percorrendo todas as propriedades de um objeto. Para cada propriedade distinta, o JavaScript executará uma iteração.

```
function dump_props(obj, obj_name) {
  var result = "";
  for (var i in obj) {
    result += obj_name + "." + i + " = " + obj[i] + "<br>";
  }
  result += "<hr>";
  return result;
}

Output:

car.make = Ford
car.model = Mustang
```

- **for...of_statement**

```
for (variavel of objeto) {
  declaracoes
}
```

A declaração for...of cria uma laço com objetos interativos ((incluindo, Array, Map, Set, assim por conseguinte ), executando uma iteração para o valor de cada propriedade distinta.

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

### **3. Salto**

#

- **label_statement**

```
label : declaracao
```

Um label pode usar qualquer idenficador que não seja uma palavra reservada do JavaScript. Você pode identificar qualquer instrução com um label.

```
markLoop:
while (theMark == true) {
   facaAlgo();
}
```

- **break_statement**

```
for (i = 0; i < a.length; i++) {
  if (a[i] == theValue) {
    break;
  }
}
```

Use break para terminar laços, switch, ou um conjunto que utiliza label.

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

- **continue_statement**

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

A declaração continue pode ser usada para reiniciar uma instrução while, do-while, for, ou label.

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
