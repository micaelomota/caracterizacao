# Typescript

## Modelo de tradução (compilação, etc.?)

Typescript é uma linguagem "transcompilada". A compilação de typescript gera um código em javascript que é por fim interpretado e executado por um navegador ou algum motor como NodeJs.

## Nomes, variáveis e vinculação

Em typesript os nomes são tratados como na maioria das linguagens. Podemos atribuir funções a variáveis.

Para declarar variáveis no TypeScript podemos usar de três formas, let,
var e const.
○ Var, let e const possuem a mesma sintaxe:
let <NomeDaVariável>:Tipo = Valor;
const <NomeDaVariável>:Tipo = Valor;
var <NomeDaVariável>:Tipo = Valor;

- Podemos inferir ou não valores às variáveis durante sua declaração.
- Podemos ou não dizer o tipo de dado que ela agrega.
- Podem receber funções como valores.

## Escopo, tempo de vida e ambientes de referência.

Declarações var possuem escopo de função.

```Typescript
function m1(): void {
 var x: boolean = true;
 if (x) {
 var loucura = "Xoxo"
 }
 console.log(loucura); //Xoxo
}
```

Existe o conceito de elevação, onde você pode declarar
variáveis globais no final do código e em tempo de execução ela ser
elevada ao topo. O mesmo ocorre para subprogramas.

Let declarações já se assemelham com a maioria das linguagens e
possui escopo de bloco.

O conceito de elevação só se aplica para let quando se trata de variáveis
globais.

Re-declaração e sombreamento
Utilizando var, múltiplas declarações de uma mesma variável é
válida!

TypeScript possui escopo estático e aninhado (Closures)

## Estruturas de controle

Há dois comandos para desvio de fuxo: if-else e switch e são semelhantes aos da linguagem C.

Há uma variaedade de estruturas para loops:

- for (semelhante ao C)
- for of (semelhante ao C++14)
- for in
- while (semelhante ao C)
- do … while (semelhante ao C)

For in serve para inspecionar propriedades do objeto, sempre
fazendo um loop em cima dos nomes das propriedades, enquanto
for of é para repetir dados, funcionando apenas em objetos iteráveis.
