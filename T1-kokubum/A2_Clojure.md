# Trabalho 1 - Atividade A1

### Linguagem de Programação: Clojure

#

## Modelo de compilação:

A linguagem Clojure é definida como uma linguagem compilada pelo fato de rodar sob a JVM (máquina virtual Java) compilando seu código "on the fly" para o byte code e permitindo que você rode o código em qualquer ambiente sem necessidade de recompilação.

## Nomes, variáveis e vinculação:

### Nomes

#

O Clojure não tem um padrão de nomenclatura obrigatório, mas assim como a maioria das linguages, ele possui algumas diretrizes que são adotadas pela comunidade.

- Funções puras: Definidas através de substantivos, com todas as letras minúsculas e separadas pelo "-".
- Funções com efeitos colaterais: Definidas com verbos que descrevem a ação seguindo a mesma ideia das funções puras de letras minúsculas e separadas pelo "-".
- Funções que retornam funções: Devem ter o sufixo -fn
- Aliases de namespaces: Podem economizar em repetições (products/price em vez de products/product-price) e evitar conflitos locais em bindings
- Variáveis: Seguem sempre o mesmo padrão de letras minúsculas seguidas de "-".

### Variáveis

#

- Variável global: Variáveis criadas através da keyword "def".

Ex:

```
(def variavel "exemplo") variavel ;; => "exemplo"
```

- Variavel de namespace: Variáveis que são definidas após a definição do "namespace".

Ex:

```
(ns 'exemplo)

(def variavel "exemplo") variavel ;; => "exemplo"

;; De forma gráfica, o escopo seria assim:

+----------------------+
|ns exemplo            |
+----------------------+
|variavel = "exemplo"  |
|                      |
|                      |
+----------------------+
```

- Varável local: São variáveis que estão visíveis apenas dentro do escopo em que foram definidas, geralmente uma função.

Ex:

```
(ns 'exemplo)

(def variavel 1)

(let [nova-variavel 2]
  (println (+ variavel nova-variavel)))

variavel ;; => 1
nova-variavel ;; => Erro

;; De forma gráfica, o escopo seria assim:

+-------------------------------------+
| ns exemplo                          |
+-------------------------------------+
| variavel = 1                        |
|                                     |
|   +---------------------------------+
|   | let                             |
|   +---------------------------------+
|   | nova-variavel = 2               |
|   |                                 |
|   |                                 |
|   | (println                        |
|   |     (+ variavel nova-variavel)) |
|   |                                 |
+---|---------------------------------+

```

### Vinculação

#

- Dinâmica: O Clojure tem o processo de vinculação dinâmica, ou seja, em tempo de execução, proporciado simplismente pelo uso da keyword "bindind".

Ex:

```
user> (defn foo [] (println x))
user> (binding [x 1] (foo))
1
nil
```

- Estática: O clojure tem a vinculação de valores que ocorre em tempo de compilação proporcionada pelo simples uso do "let" na atribuição.

```
user> (defn foo [] (println x))
user> (let [x 1] (foo))
0
nil
```

## Escopo, Tempo De Vida e Ambientes de Referência

### Escopo e tempo de vida:

#

- Escopo Global

Uma variável declarada através da keyword "def" é responsável pela definiçào de símbolos globais.

Tempo de vida - Para essa situação a variável tem o tempo de vida igual ao tempo de execução do programa.

Ex:

```
(def denominator 0)
```

- Escopo Local

Uma variável declarada através da "let-expression", basicamente uma macro cujo primeiro parâmetro é um vetor (que em Clojure declaramos com [ e ] - encare como o Array de outras linguagens, exceto que não precisamos de vírgulas entre os elementos, logo um vetor com os valores 1 4 5 seria escrito [1 4 5]) que precisa ter elementos par – o elemento par é o nome da variável/símbolo, e o elemento ímpar é seu valor.

Tempo de vida - Para essa situação, como foi mencionado acima, a variável tem o tempo de vida de duração da execução dessa função, de forma que no momento que a função for finalizada, ela deixa de existir.

Ex:

```
(let [variable-1 "Hello"
      variable-2 "World!"]
  (str variable-1 ", " variable-2))
```

### Ambientes de Referência: Estático e Dinâmico

#

- Estático: Escopo que é definido antes da execução do programa, com base na estrutura léxica do mesmo, ou seja, baseado sempre onde cada uma de suas instruções foram declaradas.

Ex:

```
(def x 0)
;=> #'user/x

;; Escopo estático
(defn f [] x)
;=> #'user/f
(f)
;=> 0
(defn g [] (let [x 1] (f)))
;=> #'user/g
(g)
;=> 0
```

- Dinâmico: Escopo que é definido com base na pilha de execução.

Ex:

```
;; Leve como base que o código acima também tenha sido definido aqui.

;; Escopo dinâmico

(defn h [] (binding [x 1] (f)))
;=> #'user/h
(h)
;=> 1
```

## Estruturas de Controle:

#

Na linguagem clojure, podemos perceber a existência de diversas estruturas de controle que tem o mesmo propósito das estruturas das linguagens tradicionais, porém com uma sintaxe diferente.

### **1. Condicional:**

#

- **if/else**

Clojure possui o operador if e o if-not. O interessante é que a palavra "else" não é utilizada; if realiza uma verificação lógica (true ou false) e caso seja true realiza a operação do primeiro input, caso não a do segundo. if-not tem o mesmo comportamento só que ao contrário.

```
(ns learn-structures.core
  (:gen-class))

(defn learn-if
  "exemplo simples if/else"
  [x]
  (if (= x 1)
    (println "É um")
    (println "Não é um")))

(defn learn-if-not
  "exemplo simples if-not/else"
  [x]
  (if-not (= x 1)
    (println "Não é um")
    (println "É um")))
```

- **when**

É parecido com if, mas apenas produz um resultado para caso a condição seja atendida

```

(defn learn-when
  "exemplo simples when"
  [x]
  (when (< x 10) (throw (AssertionError. "Entrada errada"))))
```

- **Cond, Condp e Case**

As três funções se assemelham com o construct switch de outras linguagens, então recebe uma variável e, com base em seu valor, faz comparações para produzir um resultado. A diferença entres as três está nas comparações; cond avalia diferentes operações que passamos diretamente e retorna a primeira que for satisfeita (podemos passar :else para avaliar o caso em que nenhuma condição tenha sido satisfeita). condp é semelhante à cond, mas recebe também a operação (função) a ser utilizada em todos os casos. Por fim, case faz uma comparação simples de igualdade. Nas duas últimas, não precisamos de uma keyword para definir um valor padrão.

```
(defn learn-cond
  "exemplo simples cond"
  [x]
  (cond
    (< x 1) "menor que 1"
    (> x 1) "maior que 1"
    :else "1"))

(defn learn-condp
  "exemplo simples condp"
  [x]
  (condp = x
    3 "é 3"
    2 "é 2"
    1 "é 1"
    "Valor inesperado"))

(defn learn-case
  "exemplo simples case"
  [x]
  (case x
    3 "é 3"
    2 "é 2"
    1 "é 1"
    "Valor inesperado"))
```

### **2. Repetição:**

#

Clojure possui uma macro for, porém não é muito utilizada e não é igual a outras linguagens (afinal Clojure é imutável). É mais comum utilizar loop em conjunto de recur.

- **for**

```
(defn learn-for
  (for [x [0 1 2 3 4 5]
        :let [y (* x 3)]
        :when (even? y)]
    y))
```

A função recebe um vetor com valores e/ou binding forms e produz um resultado. No exemplo abaixo, um vetor x é declarado, e com ajuda de :let, for irá iterar x e atribuir um valor a y. Após isso, when filtrará os pares e a função retorna y diretamente (que é uma lazy sequence).

- **loop**

```
(defn learn-loop
  "learn-loo simples loop"
  (loop [n x]
        (when (> n 0)
        (prinln n)
        (recur (dec n)))))
```

loop é usada em conjunto com recur para que haja efeito. Veja que ele atribui x a n e que quando n for maior que zero, imprime seu valor, subtrai um com dec e volta para when. Quando for zero, quebra o loop e retorna.
