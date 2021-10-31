# Linguagem de Programação: JavaScript 

# Modelo de tradução

Linguagem de programção interpretada.

# Nomes - Variáveis - Vinculação

Vinculação dinâmica.

# Escopo - Tempo de vida - Ambientes de referência

Em JavaScript, há variáveis locais e globais, além de multiplos escopos. Temos sempre um objeto global, que no Browser geralmente é o "window", de onde podemos acessar variáveis globais ou declarar novas. Também podemos fazer uso da keyword "var" na declaração, que utiliza o escopo imediato ao contrário da keyword "let" "const". 

O tempo de vida das variáveis é implicit heap-dynamic.
Há vários ambientes de referência, o global, o quando um método é chamado, recorrência, etc. 

# Estruturas de controle

O JavaScript suporta um conjunto compacto de declarações, especificamente de fluxo de controle, que você pode utilizar para atribuir uma grande interatividade as páginas web por exemplo.

Exemplo de uma declaração if-else:

```zsh
  if (condicao) {
    declaracao_1;
  } else {
    declaracao_2;
  }
```