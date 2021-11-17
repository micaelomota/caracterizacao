A1 C++ 
a) Modelo de tradução(compilação, etc): 
A compilação de um programa C++ envolve três etapas:
Pré-processamento: o pré-processador usa um arquivo de código C++ e lida com #includes, #defines e outras diretivas de pré-processador. A saída desta etapa é um arquivo C++ "puro" sem diretivas de pré-processador.
Compilação: o compilador pega a saída do pré-processador e produz um arquivo de objeto a partir dele.
Vinculação: o vinculador obtém os arquivos de objeto produzidos pelo compilador e produz uma biblioteca ou um arquivo executável.

b) Nomes, variáveis e vinculação.
Nomes: C++ → sem restrição de tamanho, É case-sensitive;
variáveis: bool, char, int, double e float;
Vinculação: estática
Vinculações de Armazenamento:  Variáveis heap-dinâmicas explícitas: Exemplos em linguagens de programação: – Objetos dinâmicos em C++ (new e delete). 

c) Escopo, tempo de vida e ambientes de referência.
Escopo: estático;
Tempo de vida: Escopo e o tempo de vida de uma variável parecem estar relacionados, mas são conceitos diferentes. Por exemplo, em C e C++, uma variável declarada em uma função usando o especificador static está estaticamente vinculada ao escopo dela e, também, estaticamente vinculada ao armazenamento: 
void sub1() {
static int a = 10; 
... 
}
Ambientes de Referência: é formado pelas variáveis locais e todas as variáveis visíveis em todos os escopos superiores (mais externos).

d) Estruturas de controle: Os comandos de fluxo de controle de uma linguagem de programação especificam a ordem em que processamento é feito.
decisão:  if, if-else, switch e o operador condicional.
seleção: if, if- else, switch-case.
iteração: while, do e for
