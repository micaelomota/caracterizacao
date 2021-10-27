# Caracterização de Linguagens de Programação

## Linguagem de Programação: Elixir 

  * [Apresentação e histórico](#apresentação-e-histórico)
   * [Características da Linguagem](#características-da-linguagem)
  * [Capacidades da Linguagem](#capacidades-da-linguagem)
  * [Produtividade do Desenvolvedor](#produtividade-do-desenvolvedor)
  * [Ecossistema](#ecossistema)
  * [Informações Adicionais](#informa--es-adicionais)
  * [Referências](#referências)

## Apresentação e histórico

_Elixir é uma linguagem de programação funcional brasileira, criada por José Valim. Lançada em 2012 e executada na máquina virtual do Erlang, foi desenvolvida pela Ericsson, antiga empresa de celulares._

_Na linguagem Elixir, os processos são isolados se comunicam por meio de mensagens, o que tornam eles mais independentes e eficientes, um fator importante que influencia no constante crescimento do ecossistema._

_Entre os projetos que utilizam Elixir na sua programação, destacam-se o WhatsApp, Discord, Pinterest, entre outros aplicativos e sites. A presença de Elixir nesses grandes projetos mostram o quão importante ela vem se tornando._


___
## Características da linguagem:
___

## Modelo de compilação:

Elixir sempre compila e executa o código, realizando os dois processos com os comandos elixir ou elixirc. Os passos de compilação e execução são esses a seguir:

+ Carrega os conteúdos do arquivo na memória
+ Produz uma árvore de análise sintática usando um token customizado e yecc (analisador sintático de Erlang).
+ Gera uma árvore de análise sintática extendida, com macros e funções expandidas.
+ Transforma a árvore extendida em uma árvore específica da linguagem Erlang
+ Constrói uma árvore, que possui o formato abstrato do programa.
+ Compila o resultado em um assembly BEAM em tempo real com especificações da linguagem, que retorna um código binário
+ Carrega o código binário na máquina virtual Erlang usando o servidor de códigos de Erlang
+ Chama a função de compilação do Elixir, que possui todo a estrutura do programa. Nesse ponto, a máquina virtual já está executando o programa.


## Nomes, variáveis e vinculação:

A convenção padrão para nomes em Elixir segue o modelo snake_case, ou seja, todas as variáveis começam com letra minúscula, seguida por 0 ou mais letras, com os caracteres opcionais ! ou ? no final. Caso tenha mais de uma palavra, elas são separadas por _.

Nomes de variáveis também podem começar com _, mas somente quando a variável não for utilizada, somente atribuída a alguma outro processo.

Aliases, pseudônimos também utilizados em Elixir, segue o padrão CamelCase, começando cada palavra por letra maiúscula, quando houver mais de uma.

"!" no final significa uma função ou macro que em caso de erro gera uma exceção no final da execução.

```elixir
    File.read!("naoexiste.txt")

    #Retorna uma exceção de erro se o arquivo não existir. se existir, retorna o conteúdodo arquivo em um código binário 
```

"?" no final significa uma função que retorna um valor booleano.

```elixir
    Keyword.keyword?([])

    #Se [] é uma palavra-chave, retorna verdade 
```

O prefixo "is_" verifica tipos de variáveis (se ela for par ou impar, por exemplo), estruturas ou se é uma referência, entre outros tipos, com resposta em variável booleana.

```elixir
    Integer.is_odd(7)

    #Se 7 é ímpar, retorna verdade 
```

As palavras length e size tem características diferentes do que em outras linguagens. Uma operação que utiliza size roda em tempo constante, pois o tamanho é armazenado por toda a estrutura. Uma operação que utiliza length roda em tempo linear, pois toda a estrutura precisa ser percorrida.

Existem 2 tipos de variáveis em Elixir:

+ Variável locais: Declarada dentro de um bloco dentro do programa, como uma função. São acessíveis somente onde foram declaradas.
  
+ Variável global: Declarada para todo o código, acessível a todo o programa

## Escopo, tempo de vida e ambientes de referência:

As variáveis locais fazem parte do escopo do bloco onde foram declaradas, no qual essas variáveis possuem tempo de vida que dura enquanto a execução da função continuar.

As variáveis globais fazem parte do escopo global, no qual essas variáveis possuem tempo de vida que permanece até o fim da execução do programa.

___
## Produtividade do desenvolvedor:
___

## Estruturas de controle:

As estruturas de controle são blocos para avaliar variáveis e escolher as direções válidas a depender dos parâmetros informados. Elas especificam o fluxo do controles nos programas e ajuda a tornar os códigos mais claros e precisos.
Em Elixir, existem 4 estruturas de controle:

### a) if e unless:

O `if` funciona de forma semelhante a outras linguagens de programação, com a diferença de um "do" e um "end", para demarcar o início e o fim da condicional. O uso do else é opcional.

```elixir
if condicao_booleana do
   #Código caso a condição seja aceita
else
   #Código caso a condição não seja aceita
end
```

O `unless` é um pouco diferente, pois funciona de forma negativa ao `if`. O uso do else também é opcional.

```elixir
unless condicao_booleana do
   #Código caso a condição seja falsa
else
   #Código caso a condição seja verdadeira
end
```

Tanto o if quanto o unless em Elixir são construidos como macros, não são construtores da linguagem. Além disso, os únicos valores falsos em elixir são o `nil` e o booleano `false`.

### b) case:

A estrutura `Case` funciona de forma semelhante a estrutura `switch-case`, onde existe varias possibilidades de caso a depender de uma variável. Caso não encontre um valor associado, a condição termina com um CaseClauseError, que indica que nenhum valor correspondente foi encontrado. Para prevenir isso, deve existir um caso com `_`, que vale para todos os valores, e se assemelha com o caso `default` da estrutura `switch-case`.

```elixir
case numero do
      cond_1 -> #Executa se o número corresponde a cond_1
	  cond_2 -> #Executa se o número corresponde a cond_2
	  cond_3 -> #Executa se o número corresponde a cond_3
      ...
	  _ -> #Executa se o número não corresponde a nenhum dos anteriores
end
```

### c) cond:

A estrutura `cond` serve para a associação de várias condições, semelhante a construção `else if` de outras linguagens de programação.

```elixir
cond do
   exp_1 -> #Executa se exp_1 for verdade
   exp_2 -> #Executa se exp_2 for verdade
   ...
   true -> #Executa se nenhuma outra for verdade
end
```

### d) with:

A forma especial `with` é útil para substituir várias estruturas `case` aninhadas ou quando não é possível encadear funções. Essa estrutura possui palavras-chave, depois generators e por último uma expressão.

```elixir
iex> user = %{first: "Sean", last: "Callan"}
%{first: "Sean", last: "Callan"}
iex> with {:ok, first} <- Map.fetch(user, :first),
...>      {:ok, last} <- Map.fetch(user, :last),
...>      do: last <> ", " <> first

"Callan, Sean"  #Saida do código
```

___
## Referências

1. https://www.hostgator.com.br/blog/elixir-linguagem-programacao-brasileira/
2. https://medium.com/@fxn/how-does-elixir-compile-execute-code-c1b36c9ec8cf
3. https://www.tutorialspoint.com/elixir/elixir_variables.htm
4. https://hexdocs.pm/elixir/1.12/naming-conventions.html
5. https://elixirschool.com/pt/lessons/basics/control_structures   