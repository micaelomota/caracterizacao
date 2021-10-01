
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


