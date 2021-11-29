# Guia para Caracterização de Linguagens de Programação

+ Linguagem de Programação: Elixir

  + [Apresentação e histórico](#apresenta--o-e-hist-rico)
  + [Características da Linguagem](#caracter-sticas-da-linguagem)
  + [Capacidades da Linguagem](#capacidades-da-linguagem)
  + [Produtividade do Desenvolvedor](#produtividade-do-desenvolvedor)
  + [Ecossistema](#ecossistema)
  + [Informações Adicionais](#informa--es-adicionais)
  + [Referências](#refer-ncias)

## Apresentação e histórico

O [Elixir](http://elixir-lang.org/) é uma linguagem funcional desenvolvida por um brasileiro o Jose Valim. inspirada na linguagem ruby e python e utilizando a virtual machine da erlang (BEAN) para a implementação de uma sintaxe de programação funcional.

Sua maior utilização no momento é no desenvolvimento de aplicações web, mas pode ser utilizado em qualquer contexto.

Com o uso do Phoenix o elixir se tornou uma forte alternativa para aplicações como sockets e bancos de dados. Devido a sua capacidade de escalar muito bem e a confiabilidade da BEAN para resistir a erros de execução.

Com a imutabilidade, característica do paradigma funcional, abre a possibilidade de concorrência de processos pois evita que ocorram locks no sistema ou que o mesmo dado seja alterado por mais de um processo.

## Características da Linguagem

+ Paradigma: É funcional.

+ Propósito: Ser confiavel e limpa.

+ Sistema de Tipagem: Possui a tipagem dinamica.

+ Ambiente de Execução: O Elixir é uma linguagem compilada e executada como dentro da VM BEAN.

+ Implementação: Sua implementação é feita com a compilação do codigo para a BEAN.

+ Custos:
O seu principal custo é a diferença de paradigmas onde as linguagens funcionais tem menos pessoas ativamente utilizando.

## Capacidades da Linguagem

+ Metaprogramação: O elixir possui os macros que são usados para extender a utilidade do programa assim podemos manipular a AST e gerarmos novos programas.

+ Gerenciamento de Ciclo de Vida: O Ciclo de vida no Elixir é gerenciado pela VM logo uma variavel é declarada na execução de uma função e após a execução o garbage collector a remove.

+ Segurança: Como todo o codigo é executado dentro de uma maquina virtual o acesso ao sistema é um pouco mais dificil porem ainda há riscos e a maioria relacionados a dependências externas.

+ Performance: O Elixir é uma linguagem que não é focada em velocidade porem não deixa a desejar.

+ Escalabilidade: O Elixir é considerado bastante escalavel devido a imutabilidade facilitar a concorrência.

+ Confiabilidade: Graças a Bean ser uma VM muito testada e feita para ser confiavel essa se torna uma caracteristica do elixir.

+ Concorrência e Threading: O elixir possui um sistema de agentes e tasks que possibilitam programas concorrentes, tambem é facilitado pela imutabilidade que impede deadlocks e side-effects.

+ Custos: Por mais que possua uma grande capacidade e inumeras aplicações seus custos são relacionados a uma maior complexidade de desenvolvimento.

## Produtividade do Desenvolvedor

+ Frameworks e Contâiners

O [Phoenix](https://www.phoenixframework.org/) é um framework para apis que cuida de requisições HTTP e sockets.

Já [Nerve](https://www.nerves-project.org/) é um framework para IOT e sistemas embarcados com elixir.

+ Ferramentas Disponíveis

Como ferramentas o Mix que é o gerenciador de pacotes elixir e permite a compilação e formatação do codigo, o iex que é o ambiente de execução interativa do elixir e o hexdocs que é um gerenciador de documentação do elixir.

+ Sintaxe, Semântica e Operações Predefinidas

### Estruturas de Controle

+ if:

```elixir
if String.valid?("Hello") do
  "Valid string!"
end
```

+ else:

```elixir
if String.valid?("Hello") do
  "Valid string!"
else  
  "Invalid string."
end
```

+ match:

O Elixir possui pattern matching que é uma forma de se comparar valores com um padrão e é exaustivo logo possui um _ que serve para definir um caso padrão.

```elixir
case {:ok, "Hello World"} do
  {:ok, result} -> result
  {:error} -> "Uh oh!"
  _ -> "Catch all"
end
```

### Estrutura de Repetição

+ loop:

O elixir não possui um operador de loop, porem os loops podem ser feitos por meio da recursividade ou por enums.

```elixir
numbers = [12, 3, 7, -2, 4]

transformed_numbers = numbers
 |> Enum.with_index()
 |> Enum.map(fn {index, number} -> number * index end)

#The result is [0, 3, 14, -6, 16]
```

+ Legibilidade
+ Redigibilidade
+ Custos

## Ecossistema

+ Maturidade

Por mais que seja uma linguagem relativamente nova já possui o apoio de empresas grandes como o Discord, Mozilla, Heroku entre outros.

+ Comunidade

Sua comunidade tem crescido bastante no mundo inteiro, chegou ao mainstream após ser aparecer no curso da rocketseat e tem sido adotada por diversas empresas.

+ Governança

A governança do Elixir é pela Erlang Ecosystem Foundation [EEF](https://erlef.org/) e a proposta de novas funcionalidades é feita criando uma discussão na lista de email do time de [Elixir Core](https://groups.google.com/group/elixir-lang-core).

+ Fragmentação

---

## Informações Adicionais

## Referências

1. <https://www.gartner.com/en/documents/2071615/programming-languages>
framework for assessing and characterizing programming languages and assessing their applicability to specific projects.

2. <https://elixirschool.com/pt>
Elixir documentation for beginners to intermediate level Elixir developers.

3. <https://elixir-lang.org/>
Elixir oficial website.
