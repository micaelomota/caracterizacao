# Linguagem de Programação: Golang 

# Modelo de tradução

Linguagem de programção compilada.

# Nomes - Variáveis - Vinculação

Vinculação dinâmica e estática.

# Escopo - Tempo de vida - Ambientes de referência

Em Golang, há variáveis locais e globais. Possui também múltiplos escopos. A keyword "var" é utilizada na declaração de variáveis em qualquer contexto de escopo além da keyword "const". 

O tempo de vida das variáveis é implicit heap-dynamic. 

# Estruturas de controle

As estruturas de controle de Go estão relacionadas às de C, mas diferem em aspectos importantes. Não há loop do ou while, apenas um for ligeiramente generalizado; switch é mais flexível; if e switch aceitam uma instrução de inicialização opcional como a do for; as instruções break e continue recebem um rótulo opcional para identificar o que interromper ou continuar; e há novas estruturas de controle, incluindo uma chave de tipo e um multiplexador de comunicações multiway, selecione. A sintaxe também é um pouco diferente: não há parênteses e os corpos devem ser sempre delimitados por chaves.

Em Go um if se parece com isto:

```zsh
  if x > 0 {
    return y
  }
```