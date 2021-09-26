# Atividade A1 - Python

+ **a) modelo de tradução (compilação, etc.?)**
  + Python é uma linguagem interpretada com um passo intermediário de compilação para bytecode (na sua implementação de referência, CPython). Há outras implementações da linguagem que compilam para máquinas virtuais diferentes (IronPython, Jython), uma versão interpretada com um compilador JIT (PyPy) e uma versão compilada que traduz código Python para código C e o compila.
+ **b) nomes, variáveis e vinculação**
  + Python suporta identificadores Unicode tal qual especificado pelo anexo 31 do Padrão Unicode. Na versão atual (3.9) possui 35 palavras reservadas. 
+ **c) escopo, tempo de vida e ambientes de referência.**
  + A linguagem tem escopo estático, e suas regras de escopo determinam que um escopo aninhado tem acesso às variáveis de todos os escopos que o englobam, inclusive o escopo global. Definir uma função e seus argumentos, importar um módulo ou um conteúdo de um módulo, definir uma classe ou atribuir um valor a uma variável são formas de introduzir um novo nome ao escopo local. Os escopos em Python são gerenciados através de namespaces, implementados (e acessíveis em tempo de execução) com dicionários que são atributos de cada função, módulo, etc. Apenas funções criam novos escopos em Python, e declarações de funções podem estar aninhadas (mas uma função declarada dentro de outra função só é acessível dentro da função externa imediata e dentro dela mesma, recursivamente, porém não nos escopos mais externos e global).
  + Tempo de vida
  + Ambientes de referência

## Referências

1. https://docs.python.org/3/reference/lexical_analysis.html
Lexical analysis - Python 3.9.7 documentation