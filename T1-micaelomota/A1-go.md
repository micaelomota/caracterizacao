# GO

## Modelo de tradução (compilação, etc.?)

GO é linguagem de programação compilada.

## Nomes, variáveis e vinculação

Suporta vinculação dinâmica e estática.

## Escopo, tempo de vida e ambientes de referência.

A instrução var declara uma lista de variáveis em blocos e também em argumento de funções.

Uma variável pode ser declarada no nível do pacote ou no nível de uma função.

GO gerência alocação de memória automáticamente, prefere usar stack, mas suporta heap allocation também.

## Estruturas de controle

O comando if em GO é similar ao das linguagens mais populares atualmente. Não é necessário usar parenteses para a expressão condicional. É obrigatório usar o par {} para delimitar o bloco.

Go tem somente uma instrução para loop: o for.

O comando é similar ao que vemos na linguagem C, mas assim como no if, não é necessário utilizar parenteses.

Geralmente ao usar o for fazemos como no C, declaramos 3 componentes separados por ponto e vírgula.

```go
for i := 0; i < 10; i++ {
	//
}
```

- O comando de inicialização `i := 0` é executado uma vez antes da primeira iteração.
- A expressão condicional `i < 10` é verificada sempre antes de cada iteração.
- O comando posterior `i++` é executado ao final de cada iteração.

Geralmente o comando de inicialização vai declarar uma variável como o `i` no exemplo, as variáveis declaradas nesse componente são visíveis apenas no escopo do for.

## Referencias

Allocation efficiency in high-performance Go services
https://segment.com/blog/allocation-efficiency-in-high-performance-go-services/
