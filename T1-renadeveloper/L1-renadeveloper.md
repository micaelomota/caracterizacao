# Python

## Contexto Histórico

## Principais Características

Python é uma linguagem fortemente tipada, ou seja, é uma linguagem em que se deve fazer operações com a necessidade da realização de cast, e também dinamicamente tipada, ou seja, é uma linguagem em que o tipo de uma variável pode ser alterado durante a execução do código.


### Variáveis

Python é uma linguagem case-sensitive, ou seja, sensível às letras maíusculas e minúsculas - na qual se você cria uma variável com nome `linguagem`  esta é diferente de outra variável chamada `Linguagem` .

As variáveis em Python possuem sequência de tamanho ilimitado, podem conter caracteres alfanuméricos (A-z 0-9), podem conter sublinhados, podem iniciar com letra (A-z) e podem iniciar com sublinhado - apesar de não ser indicado.

As variáveis em Python não podem conter pontos, espaços em branco, não podem ser iniciadas com números ou ser palavra-chave ou palavra reservada da linguagem.

#### Tipos de Variáveis
### Escopo
### Vinculação

Python é uma linguagem de vinculação dinâmica: em tempo de execução a tipagem de uma variável na linguagem será definida com base no valor o qual foi utilizado. 
Exemplo:

```py

------------------------ INPUT --------------------------------

nome = "Renata"
print(nome) #será printado "Renata"
profissao = ", estudante de computação"
print(nome + profissao)  #será printado "Renata, estudante de computação"
print(type(profissao)) #será printado que o tipo da variável profissão é str (string)
profissao = 20
print(type(profissao)) #será printado que o tipo da variável profissão é int (inteiro)

```

```py

------------------------ OUTPUT --------------------------------

Renata
Renata, estudante de computação
<class 'str'>
<class 'int'>

```

### Tempo de Vida

---

## Referências 

1. https://blog.grancursosonline.com.br/python-e-r-variaveis-e-tipos-das-linguagens/

