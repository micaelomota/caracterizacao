a) Modelo de tradução
Linguagem interpretada

b) Nomes, variáveis e vinculação
JavaScript não é uma linguagem compilada, então a vinculação é dinâmica.

c) Escopo, tempo de vida e ambientes de referência.
Em JavaScript, há variáveis locais e globais, multiplos escopos. Temos sempre um objeto global, que no Browser geralmente é o "window", de onde podemos acessar variáveis globais ou declarar novas. Também podemos fazer uso da keyword "var" na declaração, que utiliza o escopo imediato ao contrário da keyword "let". 

O tempo de vida das variáveis é implicit heap-dynamic.
Há vários ambientes de referência, o global, o quando um método é chamado, recorrência, etc. 


