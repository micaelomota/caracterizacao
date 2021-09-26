# Atividade A1 - Python

+ **a) modelo de tradução (compilação, etc.?)**
  + Python é uma linguagem interpretada com um passo intermediário de compilação para bytecode (na sua implementação de referência, CPython). Há outras implementações da linguagem que compilam para máquinas virtuais diferentes (IronPython, Jython), uma versão interpretada com um compilador JIT (PyPy) e uma versão compilada que traduz código Python para código C e o compila.
+ **b) nomes, variáveis e vinculação**
  + Python suporta identificadores Unicode tal qual especificado pelo anexo 31 do Padrão Unicode. Na versão atual (3.9) possui 35 palavras reservadas. 
+ **c) escopo, tempo de vida e ambientes de referência.**
  + A linguagem tem escopo estático, e suas regras de escopo determinam que um escopo aninhado tem acesso às variáveis de todos os escopos que o englobam, inclusive o escopo global. Definir uma função e seus argumentos, importar um módulo ou um conteúdo de um módulo, definir uma classe ou atribuir um valor a uma variável são formas de introduzir um novo nome ao escopo local. Os escopos em Python são gerenciados através de namespaces, implementados (e acessíveis em tempo de execução) com dicionários que são atributos de cada função, módulo, etc. Apenas funções criam novos escopos em Python, e declarações de funções podem estar aninhadas (mas uma função declarada dentro de outra função só é acessível dentro da função externa imediata e dentro dela mesma, recursivamente, porém não nos escopos mais externos e global).
  + Tempo de vida
    O tempo de vida de uma variável declarada dentro de uma função dura da primeira atribuição da variável na função até o momento que a execução da função é finalizada. Uma exceção é quando se usa a keyword _global_, que permite que variáveis globais sejam declaradas ou reatribuidas dentro de funções. Variáveis globais têm tempo de vida igual ao tempo de execução do programa.
    Um caso especial são objetos do tipo _generator_, que sintaticamente são similares a funções mas na prática são classes que armazenam o estado de execução de uma função (valores de suas variáveis e o ponto em que a execução parou) que retorna múltiplas vezes (continuando cada vez do ponto em que retornou), e quando não há mais o que executar retorna uma exceção _StopIterationError_. O tempo de vida de variáveis de um _generator_ dura enquanto o _generator_ ainda não tiver gerado o _StopIterationError_ e também ainda tiver referências ativas no código (não está disponível para coleção de lixo).
    Python oferece ainda a keyword _del_ que apaga um nome do ambiente de referenciamento atual, podendo dessa forma manualmente finalizar o tempo de vida de uma variável de qualquer tipo.
  + Ambientes de referência
    Basicamente explicado na explicação sobre escopo. Para trazer novos nomes ao ambiente de referência atual, além das formas de criar novas variáveis, há a keyword _import_.

## Referências

1. https://docs.python.org/3/reference/lexical_analysis.html
Lexical analysis - Python 3.9.7 documentation