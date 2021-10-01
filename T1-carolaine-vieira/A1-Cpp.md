# C++

## Modelo de Tradução

O código em C++ precisa ser compilados para a linguagem Assembly gerando um código binário, para posteriormente ser compilado pelo computador.

## Nomes

- Geralmente não têm limite de tamanho;
- É case-sensitive;
- Só pode ser definido uma vez.

## Variáveis

- Tipos de variáveis: `bool`, `char`, `int`, `double` e `float`;
- Utiliza o sistema carmelCase;
- Podem conter 0-9, A-Z, a-z e "\_".

## Vinculação

Na execução, uma variável é associada com:

- tipo;
- nome;
- endereço;
- valor.

As variáveis são estáticas. Devem ser declaradas antes da execução do programa e permanecem alocadas até a finalização do programa.

> _Se você tentar utilizar a variável antes de especificar o seu valor, você obterá "lixo"._ [https://www.inf.ufpr.br/ci208/NotasAula.pdf]

## Escopo

Em C++ existem os seguintes tipos de escopos:

- **global:** variáveis que são declaradas fora de qualquer bloco são consideradas globais e podem ser utilizadas em qualquer lugar do arquivo;
- **local:** as variáveis declaradas dentro de metódos são acessadas apenas dentro da função;
- **classe:** sofrem as restrições de `public`, `private` e `protected`;
- **instrução:** variáveis declaradas dentro de `while`, `for`, `if` e `switch` e que ficam disponíveis apenas dentro desse bloco;
- função;
- namespace.

```
#include <iostream>
using namespace std;

int carol = 22; // variavel global

int main() {
  cout << carol;
}
```

## Tempo de Vida

As variavéis estáticas são alocadas no inicio da execução do programa e permanecem assim até que a execução finalize.

## Ambientes de Referência
