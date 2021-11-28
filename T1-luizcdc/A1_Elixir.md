# Atividade A1 - Elixir

+ **a) modelo de tradução (compilação, etc.?)**
  + Elixir é uma linguagem compilada e interpretada. Arquivos da extensão ".ex" são compilados para arquivos ".beam" que contém bytecode da máquina virtual BEAM (originalmente projetada para a linguagem Erlang), e então interpretados por essa máquina virtual. Arquivos ".exs" são compilados em memória apenas no momento da execução e o código compilado naquele momento é executado na máquina virtual BEAM. A máquina virtual BEAM, por sua vez, tem rotinas de compilação JIT que independem do Elixir e se aplicam a qualquer bytecode gerado para ela.
+ **b) nomes, variáveis e vinculação**
  + Elixir suporta identificadores Unicode tal qual especificado pelo anexo 31 do Padrão Unicode, restringido à forma de normalização C para comparação de strings Unicode, com algumas modificações<sup>[1]</sup>. Identificadores não têm limite de tamanho. Há 15 palavas reservadas em Elixir<sup>[2]</sup>.
  + Variáveis são dinamicamente tipadas. Os tipos básicos oferecidos são:
    + Integer (64 bits)
    + Float (64 bits)
    + Boolean (true ou false)
    + String (utf-8)
    + Lambda (função anônima que pode ser atribuída a uma variável)
    + Coleções (listas, tuplas, etc)
  
<!--
  + Os caracteres aceitos são baseados em subconjuntos do padrão Unicode. Indentificadores não podem começar com numerais arábicos, mas podem começar letras maiúsculas, letras minúsculas, tipos especiais de letras (modificadoras, _titlecase_, letras-números) e outros caracteres na categoria Unicode _Other_ID_Start_. Todos esses tipos de caracteres podem ser utilizados na parte do meio dos nomes inclusive números. Nenhum caractere das categorias Unicode _Pattern_Syntax_ e _Pattern_White_Space_ pode aparecer em identificadores em Elixir, porém o último caractere de um identificador pode também ser, excepcionalmente, ? e !.
--->

  + Como em Elixir temos uma máquina virtual que interpreta o código compilado, a vinculação sempre acontece em tempo de execução, nunca em tempo de compilação. Alguns valores são vinculados no início da interpretação do arquivo compilado, porém, tal como átomos.
 
+ **c) escopo, tempo de vida e ambientes de referência.**
  + Elixir é uma linguagem de escopo estático, e suas regras de escopo determinam que um escopo aninhado tem acesso às variáveis de todos os escopos que o englobam, inclusive o escopo global. Essa regra não vale para funções nomeadas, que precisam explicitamente utilizar a macro `unquote()` para acessar variáveis dos seus escopos externos. Variáveis declaradas num escopo são acessíveis naquele escopo e nos seus escopos externos, e se tiver o mesmo nome de uma variável já declarada num escopo externo "esconde" a variável do escopo externo temporariamente durante seu tempo de vida. Outra exceção é que independentemente do escopo em que uma declaração de um módulo for embutida, o módulo estará acessível no escopo global, porém se sua declaração for interna à declaração de outro módulo, seu nome incluirá como prefixo o nome do outro módulo.
  + O tempo de vida de variáveis do Elixir é igual ao tempo da execução do seu escopo, exceto para átomos, que são globais no nível da máquina virtual (e não apenas do arquivo) e nunca são desalocados, e para módulos, que são processados em tempo de compilação.
  + As regras para ambientes de referência são similares a regras de escopo, com poucas exceções. Uma dessas exceções é que funções não-anônimas declaradas num módulo não podem ser referenciadas dentro desde mesmo módulo, ou seja, só entram no ambiente de referência após o fim da declaração do módulo.


## Referências

1. https://hexdocs.pm/elixir/1.12/unicode-syntax.html
Unicode Syntax - Elixir v1.12.3
2. https://hexdocs.pm/elixir/1.12/syntax-reference.html
Syntax Reference - Elixir v1.12.3
3. https://elixir-lang.readthedocs.io/en/latest/technical/scoping.html
Scoping Rules in Elixir (and Erlang)