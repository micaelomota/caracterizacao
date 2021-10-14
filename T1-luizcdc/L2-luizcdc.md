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

+ Linguagem de Programação: **Elixir**

  + [Apresentação e histórico](#apresenta--o-e-hist-rico)
  + [Características da Linguagem](#caracter-sticas-da-linguagem)
  + [Capacidades da Linguagem](#capacidades-da-linguagem)
  + [Produtividade do Desenvolvedor](#produtividade-do-desenvolvedor)
  + [Ecossistema](#ecossistema)
  + [Informações Adicionais](#informa--es-adicionais)
  + [Referências](#refer-ncias)

## Apresentação e histórico

Elixir é uma linguagem de programação funcional e concorrente dinâmica e moderna criada em 2011 pelo desenvolvedor brasileiro José Valim, suportando metaprogramação e polimorfismo (através de seus [protocolos](https://elixir-lang.org/getting-started/protocols.html)). Executa na máquina virtual Beam permitindo que interaja e se componha com os programas e bibliotecas disponíveis no Erlang. Tem como objetivo facilitar a construção de aplicações de baixa latência em tempo real, distribuídas e tolerantes a falhas. É empregada no backend de vários serviços e websites como o Pinterest, Moz, The Financial Times e Discord.

_Comentar sobre perspectivas / papéis._


![image](./res/elixir-tree.png)

## Características da Linguagem

+ Paradigma
  :  A linguagem provê uma coleção de ferramentas ricas para o paradigma de programação funcional, que são complementadas por uma série características e constructos que favorecem a programação concorrente. A linguagem também oferece um processador de macros poderoso, tornando-se uma das linguagens de programação mais propícias à metaprogramação.
+ Propósito
+ Sistema de Tipagem
+ Ambiente de Execução
  : O Elixir é compilado para bytecode da máquina virtual da linguagem Erlang, BEAM (_Bogdan/Björn's Erlang Abstract Machine_). Bytecode gerado pela Elixir é completamente compatível com bytecode Erlang, portanto o ambiente de execução do Elixir inclui todas as bibliotecas e programas disponíveis também para o Erlang, e mantém as mesmas capacidades de interface com bibliotecas e programas de outras linguagens e do sistema operacional.
+ Implementação
  : Embora as versões iniciais do Elixir tenham sido escritas em Erlang, a linguagem é atualmente implementada majoritariamente com código em Elixir, com uma porcentagem significativa mas minoritária de seu código em Erlang. A implementação consta em um compilador que traduz os arquivos ".ex" em arquivos ".beam", e um interpretador que na verdade compila os arquivos ".exs" em memória ao ser solicitada a execução e executa o bytecode gerado. Um detalhe importante de se destacar é que recentemente a máquina virtual BEAM implementou rotinas de compilação JIT, e mesmo sem participação direta dos desenvolvedores do Elixir a linguagem teve um ganho de desempenho considerável.
+ Custos
 _Custos aqui ..._

## Capacidades da Linguagem

+ Metaprogramação
+ Gerenciamento de Ciclo de Vida
+ Segurança
+ Performance
+ Escalabilidade
+ Confiabilidade
+ Concorrência e Threading
+ Custos
  _Custos aqui ..._

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
2. https://elixirforum.com/t/jit-in-erlang-what-does-it-mean-for-elixir/34311/2
JIT in Erlang – what does it mean for Elixir?
3. https://github.com/elixir-lang/elixir
Github - elixir-lang/elixir
4. https://www.monterail.com/blog/famous-companies-using-elixir
Eight Famous Companies Using Elixir—And Why They Made the Switch