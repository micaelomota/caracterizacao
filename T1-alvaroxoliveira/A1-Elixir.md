<!-- Caracterização da Linguagem L2 - Elixir - Álvaro Souza Oliveira -->

# Linguagem 2 - Elixir

## Modelo de tradução

<body style="text-align: justify">
    <p>
        Elixir é uma linguagem que suporta multi-paradigma, mas tem centralizado o desenvolvimento primariamente no paradigma funcional.
    </p>
    <p>
        Foi projetada para ser executada em cima da Máquina Virtual Erlang, conhecida por executar sistemas em baixa latência como exemplo principal, redes de telefone.
    </p>
    <p>
        O Earlang VM por sua vez foi projetado para executar como um processo do Sistema Operacional. Por padrão ele executa um thread do SO por núcleo para atingir a utilização máxima da máquina. Esse número de threads é definido automaticamente ao ligar a máquina. Os processor do Erlang são totalmente implementados pela sua VM, assim eles não tem contato direto com os processor do Sistema Operacional. Em um sentido de que a execução do Erlang roda apenas uma thread por núcleo, mesmo com um milhão de processor, podemos chamar a VM Erlang de uma espécie de "Máquina Virtual de Processos".
    </p>
</body>

## Nomes, variáveis e vinculação
### Nomes

<body style="text-align: justify">
<ul>
    <li>Elixir utiliza <code>snake_case</code> ao definir variáveis, nomes de funções atributos de módulo e várias outras declarações.</li>
    <li>Aliases são comumente usados como nomes de módulos são exceção para a regra, pois devem ser escritos em forma <code>CamelCase</code>. Para aliases, as letras maiúsculas são mantidas em siglas.</li>
    <li> Átomos são escritos na forma <code>:snake_case</code> ou <code>:CamelCase</code>, embora a convenção seja na forma snake.</li>
    <li> Nomes de arquivos também devem seguir o padrão <code>:snake_case</code>.</li>
    <li>Valores que não devem ser usados, por exemplo, como parametros de funções, devem seguir o padrão adicionando como prefixo o caractere "_" underline.</li>
    <li>Os chamados <b>Trailing bang</b>, casos que significam que uma função ou macro podem gerar um caso de falha/exceção levam como sufixo o caractere "!" ponto de exclamação.</li>
    <li>As funções que retornam um booleano são nomeadas com um sufixo "?".</li>
    <li>As verificações do tipo booleanas, devem ser nomeadas com um <code>is_</code> como prefixo.</li>
</ul>
    
</body>

### Variáveis

<body style="text-align: justify">
    <p>
        As variáveis no Elixir não funcionam como acontece normalmente em linguagens de paradigma imperativos. No Elixir, as variáveis são rótulos para seus valores, o que diferencia de uma variável apresentar um valor.
    </p>
    <p>
        Temos dois tipos de variáveis no Elixir, que são as variáveis globais, que são aquelas que são visíveis e tem acesso por toda a parte do programa e temos também às variáveis locais, que funcionam dentro de seus blocos ou subprograma.
    </p>
    
</body>

### Vinculação (Binding)

<body style="text-align: justify">
    <p>
      Sua vinculação é do tipo dinâmica e forte, ou seja, não há como mudar o tipo das variáveis, mas a vinculação das variáveis é feita em tempo de execução.
    </p>
</body>

## Escopo, tempo de vida e ambientes de referência.

### Escopo e tempo de vida

<body style="text-align: justify">
    <p>
      Para variáveis globais, seu escopo é inteiramente como seu nome sugere, ou seja, é visível por todo o programa e tem sua vida extendida por toda a execução do programa.
    </p>
    <p>
      Para variáveis locais, seu escopo é inteiramente como seu nome sugere, ou seja, é visível por todo o subprograma em que foi declarada, e tem sua vida até o fim da execução das instruções do bloco ou sobprograma em que foi declarada.
    </p>
</body>

### Ambientes de Referência

<body style="text-align: justify">
    <p>
      A linguagem Elixir é dita de escopo dinâmico e suas variáveis são referenciadas dentro de um ambiente dinâmico.
    </p>
</body>

## Estruturas de controle a nível de Instrução

<body style="text-align: justify">
    <p>
        Elixir possui quatro tipos de desvios de controle principais:
    </p>
    <ol>
        <li>case</li>
        <li>cond</li>
        <li>if and unleess</li>
        <li>do end blocks</li>
    </ol>
</body>

### Case

<body style="text-align: justify">
    <p>
        Case nos permite compara um valor com muitos padrões até encontrarmos um valor correspondente. Podemos ver o caso de uso que existe no site da linguagem:
    </p>
</body>

~~~~
    iex> case {1, 2, 3} do
    ...>   {4, 5, 6} ->
    ...>     "This clause won't match"
    ...>   {1, x, 3} ->
    ...>     "This clause will match and bind x to 2 in this clause"
    ...>   _ ->
    ...>     "This clause would match any value"
    ...> end
    "This clause will match and bind x to 2 in this clause"
~~~~ 

<body style="text-align: justify">
    <p>
        Para padronizar a correspondência com uma variável existente, é preciso usar o <code>^</code> operador.
    </p>
</body>
~~~~
    iex> case {1, 2, 3} do
    ...>   {1, x, 3} when x > 0 ->
    ...>     "Will match"
    ...>   _ ->
    ...>     "Would match, if guard condition were not satisfied"
    ...> end
    "Will match"
~~~~

### Cond


<body style="text-align: justify">
    <p>
        Case é útil quando é preciso comparar valores diferentes. No entanto, em várias circunstancias, queremos verificar várias condições e obter o resultado daquela primeira que não for falsa. Para esse caso usamos o <code>cond</code>. Ele é equivalente ao if/else if em linguagens imperativas. Se todas as condições retornarem <code>nil</code> ou <code>false</code>, um erro <code>CondClauseError</code> será gerado. Então para que isso não ocorra, normalmente é adicionado uma condição no final igual a <code>true</code>, que servirá como um suporte para não cair no erro citado.
    </p>
</body>

~~~~
    iex> cond do
    ...>   2 + 2 == 5 ->
    ...>     "This is never true"
    ...>   2 * 2 == 3 ->
    ...>     "Nor this"
    ...>   true ->
    ...>     "This is always true (equivalent to else)"
    ...> end
    "This is always true (equivalent to else)"
~~~~ 

### If e Unless

<body style="text-align: justify">
    <p>
        Além dessas citadas acima, temos também o if e o unless que tem sua utilidade quando se precisa verificar apenas uma condição. Se a expressão if for verdadeira o bloco entre seu <code>do-end</code> será executado, caso contrário, retorna <code>nil</code> ou <code>false</code>. Exatamente o oposto ocorre para <code>unless</code>. Outra coisa é que também suportam os blocos <code>else</code>.
    </p>
</body>

~~~~ 
    iex> if true do
    ...>   "This works!"
    ...> end
    "This works!"
    iex> unless true do
    ...>   "This will never be seen"
    ...> end
    nil  
~~~~
