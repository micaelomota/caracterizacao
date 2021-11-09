# Haskell

  * [Apresentação e histórico](#apresenta--o-e-hist-rico)
  * [Características da Linguagem](#caracter-sticas-da-linguagem)
  * [Capacidades da Linguagem](#capacidades-da-linguagem)
  * [Produtividade do Desenvolvedor](#produtividade-do-desenvolvedor)
  * [Ecossistema](#ecossistema)
  * [Informações Adicionais](#informa--es-adicionais)
  * [Referências](#refer-ncias)

## Apresentação e histórico

Haskell é uma linguagem de programação puramente funcional, de propósito geral, nomeada em homenagem ao lógico Haskell Curry. Como uma linguagem funcional, a estrutura de controle primária é a função; a linguagem é baseada nas observações de Haskell Curry e seus descendentes intelectuais. Seu último padrão semi-oficial é o Haskell 98, destinado a especificar uma versão mínima e portável da linguagem para o ensino e como base para futuras extensões.

Haskell é a linguagem funcional sobre a qual mais se realizam pesquisas atualmente. Muito utilizada no meio acadêmico, ė uma linguagem relativamente nova, derivada de outras linguagens funcionais, como por exemplo Miranda e ML. Ela se baseia em um estilo de programação em que se enfatiza mais o que deve ser feito (what) em detrimento de como deve ser feito (how). É uma linguagem que possui foco no alcance de soluções para problemas matemáticos, clareza, e de fácil manutenção nos códigos, e possui uma variedade de aplicações e apesar de simples é muito poderosa.

## Características da Linguagem

Características do Haskell incluem o suporte a funções recursivas e tipos de dados, casamento de padrões, list comprehensions, guard statements e avaliação preguiçosa, esta, um elo em comum entre os diversos grupos de desenvolvimento da linguagem.[13] A combinação destas características pode fazer com que a construção de funções que seriam complexas em uma linguagem procedimental de programação, torne-se uma tarefa quase trivial em Haskell. Segundo dados de 2002, é a linguagem funcional sobre a qual mais pesquisa está sendo realizada. Muitas variantes têm sido desenvolvidas: versões paralelizáveis do MIT e Glasgow, ambas chamadas Parallel Haskell, outras versões paralelas e distribuídas chamadas Distributed Haskell (anteriormente Goffin) e Eden, uma versão chamada Eager Haskell e várias versões orientadas a objetos: Haskell++, O'Haskell e Mondrian.

Uma versão educacional do Haskell chamada Gofer, foi desenvolvida por Mark Jones. Ela é oferecida pelo HUGS. Existe também uma versão do Haskell que permite orientação a aspectos (POA), chamada AspectH.

A linguagem de programação Haskell é fundamentada em Lambda Cálculo, que serve como base no desenvolvimento do artigo e apresenta um único tipo, as funções. Haskell apresenta um tipagem forte e estática, onde as expressões são ligadas a um mesmo tipo em tempo de compilação; e apresenta o polimorfismo universal, e possui um tipo genérico e a mesma definição é usada para vários tipos.

##### Sintaxe
Em Haskell existem apenas funções, e todas as funções são unárias. O que, em outras linguagens de programação seriam funções binárias, ternárias, etc, em Haskell são funções cujo valor de retorno são outras funções - o que se chama currying, termo derivado de Haskell Curry.

Uma função que, dados dois números, retorna sua soma poderia ser declarada como:
```haskell
soma x y =x+y
```
O que parece ser uma função binária é, logicamente, uma função unária (soma, cuja entrada é x) que retorna outra função. Em outras palavras, soma x é a função unária que, dado y retorna x + y, e soma é a função unária que, dado x, retorna x +.

Em Haskell não existem variáveis globais, apenas funções e variáveis locais, definidas dentro do escopo de cada função.
Também não há estruturas de loop, ou instruções do tipo goto.
O if é implementado através de |, que significa a restrição do domínio do argumento da função.
O exemplo abaixo mostra uma implementação do fatorial que usa a recursividade e o if:
```haskell
fat 0 = 1
fat n | n > 0 = n*fat(n-1)
```
Em outras palavras: a primeira linha diz que o fatorial de zero é um; a segunda linha diz que o fatorial de um número n qualquer, desde que n seja maior que zero, pode ser calculado a partir do fatorial de (n-1). Esta implementação não é eficiente, mas serve como exemplo didático.

##### Tipos de dados
+ Bool
+ Char
+ Double
+ Either
+ Float
+ IO
+ IOError
+ Int
+ Integer
+ Maybe
+ Ordering
+ String
+ Tuplas
+ Listas

## Capacidades da Linguagem
  + Metaprogramação  + Gerenciamento de Ciclo de Vida
  + Segurança 
  + Performance
  + Escalabilidade
  + Confiabilidade
  + Concorrência e Threading 
  + Custos

## Produtividade do Desenvolvedor
  + Frameworks e Contâiners
  + Ferramentas Disponíveis
  + Sintaxe, Semântica e Operações Predefinidas
  + Legibilidade
  + Redigibilidade
  + Custos 

## Ecossistema
  + Maturidade
  + Comunidade
  + Governança
  + Fragmentação

---

## Informações Adicionais


## Referências 

1. https://www.gartner.com/en/documents/2071615/programming-languages 
framework for assessing and characterizing programming languages and assessing their applicability to specific projects
2. https://pt.wikipedia.org/wiki/Haskell_(linguagem_de_programa%C3%A7%C3%A3o)
Haskell (linguagem de programação) 
3. https://www.haskell.org/
Haskell