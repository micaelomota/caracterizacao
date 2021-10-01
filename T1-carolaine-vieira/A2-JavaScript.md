# JavaScript

## Modelo de Tradução

JS(JavaScript) é uma linguagem intepreda, não necessitando ser compilada. O código é executado diretamente no browser.

## Nomes

JS é case-sensitive e usa a formatação unicode.

## Variáveis

- As variáveis devem ser definidas antes da execução;
- Podem conter 0-9, A-Z, a-z, "\_", mas devem começar com letras, underscore ou `$`;
- Possui nomes reservados que não podem ser usados;

```
var this = 0;
```

- É possível declarar variáveis usando let, var e const;

```
let a;
var b;
const c;
```

- Aceita seis tipos de dados primitivos: Boolean, null, undefined, Number, String e Symbol. E o tipo objeto;
- Usa

## Vinculação

A vinculação é feita dinâmicamente. O tipo da variável é aplicado conforme atribuição na execução do código.

```
var dado;
// "dado" pode ser qualquer coisa antes de
dado = "Apenas uma string";
```

## Escopo

Uma variável pode ser global, local ou do bloco. A disponibilidade da variável depende de onde ela for declarada.

| Variável | Disponibilidade       |
| :------- | :-------------------- |
| var      | escopo global e local |
| const    | escopo local e bloco  |
| let      | escopo local e bloco  |

Existia um problema nesse quesito até antes da ECMAScript 6, porque variáveis "var" mesmo sendo declaradas em um escopo local, podiam ser referenciadas externamente. Isso foi resolvido com o uso de "const e let", que se restrigem ao escopo da função.

Para restringir o uso de var's também é possível usar:

```
use strict;
```

Se recomenda usar let em escopos de bloco de loop para que essa varáviel receba atribuição somento neste escopo evitando eventuais bugs.

```
for( let i = 0; i < 10 ; i++ ) {
console.log("Teste");
}
```

## Tempo de Vida

- O tempo de vida de uma variável em JS começa quando ela é declarada. Até então, nenhum espaço é alocado;
- Variáveis locais são armazenadas somente enquanto a função é executada;
- Variáveis globais são excluídas quando a página é fechada.

## Ambientes de Referência

### Local

As variáveis locais são definidas dentro de uma função.

### Dinâmico

```

```
