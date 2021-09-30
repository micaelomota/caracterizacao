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
