# Trabalho 1 - Atividade A1

### Linguagem de Programação: Elixir

#

## Modelo de compilação:

Elixir sempre compila e executa o código, realizando os dois processos com os comandos elixir ou elixirc. Os passos de compilação e execução são esses a seguir:

+ Carrega os conteúdos do arquivo na memória
+ Produz uma árvore de análise sintática usando um token customizado e yecc (analisador sintático de Erlang).
+ Gera uma árvore de análise sintática extendida, com macros e funções expandidas.
+ Transforma a árvore extendida em uma árvore específica da linguagem Erlang
+ Constrói uma árvore baseada na instrução interior para uma função em um módulo "elixir_compiler_X", que possui o formato abstrato do programa.
+ Compila o resultado em um assembly BEAM em tempo real com especificações da linguagem, que retorna um código binário
+ Carrega o código binário na máquina virtual Erlang usando o servidor de códigos de Erlang
+ Chama a função no módulo "elixir_compiler_X", que possui todo a estrutura do programa. Nesse ponto, a máquina virtual já está executando o programa.


## Nomes, variáveis e vinculação:

A convenção padrão para nomes em Elixir segue o modelo snake_case, ou seja, todas as variáveis começam com letra minúscula, seguida por 0 ou mais letras, com os caracteres opcionais ! ou ? no final.

Nomes de variáveis também podem começar com _, mas somente quando a variável não for ser utilizada, somente atribuída a alguma outra coisa.

"!" no final significa uma função ou macro que em caso de erro gera uma exceção no final da execução.

"?" no final significa uma função que retorna um valor booleano.

O prefixo "_is" verifica tipos de variáveis (se ela for par ou impar, por exemplo), estruturas ou se é uma referência, entre outros tipos, com resposta em variável booleana.

As palavras length e size tem características diferentes do que em outras linguagens. Uma operação que utiliza size roda em tempo constante, pois o tamanho é armazenado por toda a estrutura. Uma operação que utiliza length roda em tempo linear, pois toda a estrutura precisa ser percorrida.

Existem 2 tipos de variáveis em Elixir:

+ Variável de função: Declarada dentro de uma função
  
+ Variável global: Declarada para todo o código

## Escopo, tempo de vida e ambientes de referência:

As variáveis de função fazem parte do escopo da função, no qual essas variáveis possuem tempo de vida que dura enquanto a execução da função continuar.

As variáveis globais fazem parte do escopo global, no qual essas variáveis possuem tempo de vida que permanece até o fim da execução do programa.

Assim como Java, Elixir é uma linguagem de escopo estático, portanto suas variáveis são referenciadas dentro do ambiente de referência estático. Por exemplo, um método de uma classe não pode fazer referência a uma variável declarada por um ancestral dela. 

Mesmo sendo do escopo estático, funções e métodos dinâmicos ainda podem ser implementados.