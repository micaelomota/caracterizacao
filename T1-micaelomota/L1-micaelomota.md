# Typescript


<!--
Recomendações:
1. A
2. B

Contribuidores:
+ Kenia e Luiz
+ Mauricio Santiago, Gustavo Santos, Matheus Novais, Ivens Joris, Matheus Silva
+ Álvaro Souza Oliveira; Carlos Mosselman Cabral Neto; Thiago Vieira Souza Andrade; Caio Nery Matos Santos; Vanessa Machado Araújo
+ Daniel

Fontes:
+ Criação do TOC
  + [Table of contents generated with markdown-toc](http://ecotrust-canada.github.io/markdown-toc/)
---

-->

# Guia para Caracterização de Linguagens de Programação

- Linguagem de Programação: Typescript

  - [Apresentação e histórico](#apresentação-e-histórico)
  - [Características da Linguagem](#características-da-linguagem)
  - [Capacidades da Linguagem](#capacidades-da-linguagem)
  - [Produtividade do Desenvolvedor](#produtividade-do-desenvolvedor)
  - [Ecossistema](#ecossistema)
  - [Informações Adicionais](#informa--es-adicionais)
  - [Referências](#refer-ncias)

## Apresentação e histórico

<!-- _Breve texto de apresentação._ -->

TypeScript é uma linguagem de programação de código aberto desenvolvida pela Microsoft. É um superconjunto sintático estrito de JavaScript e adiciona tipagem estática opcional à linguagem.

Foi considerada pelo público a 4ª linguagem "mais amada", de acordo com uma pesquisa conduzida pelo site Stack Overflow em 2018, e está entre as 15 linguagens mais populares, de acordo com uma pesquisa conduzida pela RedMonk.

O TypeScript foi divulgado pela primeira vez em outubro de 2012 (na versão 0.8), após dois anos de desenvolvimento interno na Microsoft.

TypeScript 4.0 foi lançado em 20 de agosto de 2020. Embora esta versão não tenha introduzido nenhuma alteração significativa, ele adicionou recursos de linguagem, como Custom JSX Factories e Variadic Tuple Types.

<!-- _Colocar uma figura / árvore, com pais e filhos_. -->

![Typescript](https://user-images.githubusercontent.com/12684971/144700545-3381e03f-77e5-46c7-b78c-ef4a8a1a5aa5.png)


## Características da Linguagem

- Paradigma
- Propósito
- Sistema de Tipagem
- Ambiente de Execução
  
  ### Paradigma
  
  Typescript é uma [Linguagem de programação multiparadigma](https://pt.wikipedia.org/wiki/Linguagem_de_programa%C3%A7%C3%A3o_multiparadigma).
  
  Geralmente se escreve projetos em typescript usando orientação a objetos ou seguindo o paradigma funcional.
  
  ### Propósito
  
  O próposito inicial é tornar projetos escritos em javascript mais manuteníveis, confiáveis e escaláveis. E a linguagem alcança isso com ajuda do conjunto de ferramentas para desenvolvimento que ela fornece.
  
  ### Sistema de Tipagem
  
  Typescript funciona com tipagem estática através de anotações de tipos que são checadas em tempo de compilação. 
  É possível ignorar a tipagem estática e utilizar tipagem dinâmica como no Javascript.
  Os tipos primitivos são number, boolean e strings.
  
  ### Ambiente de Execução
  
  Typescript não é executada em nenhum ambiente. O que é executado no final das contas é o Javascript gerado (podemos dizer traduzido), ao compilar.
  
  Javascript, por sua vez, pode ser executado em navegadores web e em servidores através de motores como Node.js, cada um com a sua implementação e especificidades, mas todos respeitando os padrões definidos para aquela versão da linguagem.
  
## Capacidades da Linguagem

### Metaprogramação

É suportado algo similar ao Reflection no Java. No Typescript se chama __Descriptors__ e ainda é algo novo na linguagem.

### Gerenciamento de Ciclo de Vida

Typescript gerencia o ciclo de vida de variáveis de acordo com o escopo e com instrução com a qual elas são declaradas.
Os ambientes de execução se encarregam de tratar a vinculação e liberação de espaço de acordo com suas próprias definições.

### Segurança

Typescript é uma linguagem tipada estáticamente, e geralmente linguagens estaticamente tipadas são mais seguras porque elas podem encontrar potenciais erros antes de eles serem executados e propagados nas aplicações.

### Performance

No processo de desenvolvimento, o mecanismo de encapsulamento do typescript gera um custo de performance. Por exemplo, se todos os porjetos dependem de um mesmo pacote, algumas partes dos tipos desse parcote será checada várias vezes - uma vez para cada projeto que importa esse pacote. É recomendado dividir projetos em áreas de trabalhos diferentes.

Quanto a performance no tempo de execução, temos os mesmos benefíicios e problemas que javascript tem.

###  Escalabilidade

Typescript foi projetada justamente para resolver os problemas de escalabilidade de projetos javascript, que eram muito sucetíveis a erros devido a alta flexibilidade e fraca tipagem.

### Confiabilidade

Com o forte sistema de tipagem do typescript, os tipos garatem a previsibilidade do comportamento dos programa, a confiabilidade na linguagem é alta e, justamente por isso, há uma grande comunidade de desenvolvedores evangelizando o uso dela.

### Concorrência e Threading

Typescript opera semelhante ao javascript, ou seja, possui um modelo de concorrência baseado em um event loop (laço de eventos, em português), responsável pela execução do código, coleta e processamento de eventos e execução de subtarefas enfileiradas. Este modelo é bem diferente de outras linguagens, como C ou Java, por exemplo.


## Produtividade do Desenvolvedor

- Frameworks e Contâiners
- Ferramentas Disponíveis
- Sintaxe, Semântica e Operações Predefinidas
  - Legibilidade
  - Redigibilidade
- Custos

## Ecossistema

- Maturidade
- Comunidade
- Governança
- Fragmentação

---

## Informações Adicionais

## Referências

1. https://www.gartner.com/en/documents/2071615/programming-languages
   framework for assessing and characterizing programming languages and assessing their applicability to specific projects
2. https://pt.wikipedia.org/wiki/TypeScript
3. https://www.typescriptlang.org/docs/handbook
4. https://medium.com/@danduh/metaprogramming-javascript-typescript-part-1-descriptors-bc443d048fe9
5. https://github.com/microsoft/TypeScript/wiki/Performance#performance-considerations
6. https://itnext.io/writing-scalable-typescript-e62e1f24a013
7. https://developer.mozilla.org/pt-BR/docs/Web/JavaScript/EventLoop
