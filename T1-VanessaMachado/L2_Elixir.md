# Trabalho 1 : Atividade Parcial L2 <h1>

### Linguagem de Programação : ELIXIR <h3>

## Modelo de Tradução <h2>
<div style="text-align: justify">
    <p>  
    Elixir sempre compila e sempre executa o código-fonte. 
    </p>
    <p> <b>As principais fases de compilação do Elixir são:</b> </p> 
        <b>1 :</b> Carregamento do conteúdo do arquivo na memória;<br>
        <b>2:</b> Produção de árvore sintática utilizando tokens;<br>
        <b>3:</b> Ocorrência de diversas transformações. Fase de expansão - produz uma árvore sintática extendida, em conformidade com as mesmas especificações;<br>
        <b>4 :</b> Transformação dessa árvore sintática final no formato abstrato Erlang, ou seja uma representação padrão da árvores usando termos Erlang;<br>
        <b>5 :</b> Construção manual de uma árvore de formato abstrato;<br>
        <b>6 :</b> Compilação do resultado para a montagem, retornando um binário (Nenhum arquivo é gravado);<br>
        <b>7 :</b> Carregamento do binário referido na sessão anterior na VM Earlang usando o servidor de código Earlang;<br>
        <b>8 :</b> Chamada da função de compilação do Elixir. Uma vez que essa função tem todo o seu programa como corpo, finalmente a VM está efetivamente executando o programa;<br>
    </p>
</div>

## Nomes, Variáveis e Vinculação <h2>

### NOMES <h3>
<div style="text-align: justify">
    <p> 
        Os desenvolvedores do Elixir devem usar snake_case (Definição 1.1) ao definir <b>variáveis</b>, <b>nomes de funções</b>, <b>atributos de módulo</b> e assim por diante. Veja exemplo.1
    </p> 
    <p> 
        <b>Aliases</b>, comumente usados ​​como nomes de módulos, são uma exceção, pois devem ser escritos em maiúsculas e CamelCase (Definição 1.2). Veja exemplo.2
    </p> 
    <p> 
        Os <b>atoms</b> , constante cujo o nome é seu valor, podem ser escritos em :snake_case ou ou CamelCase, embora a convenção seja usar a versão snake_case em todo o Elixir. Veja exemplo.3
    </p> 
    <p> 
        De modo geral, os <b>nomes dos arquivos</b> seguem a convenção snake_case. No entanto, esta é apenas uma convenção. De fato, qualquer nome de arquivo pode ser usado, pois eles não afetam o código compilado de forma alguma. Veja exemplo.4
    </p>
    <p> 
        Elixir depende de <b>sublinhados</b> em diferentes situações. Por exemplo, é utilizado em um <b>valor não usado </b> ou em uma <b>variável</b> começando com sublinhado. Os <b>nomes das funções</b> também podem começar com um sublinhado. Devido a esta propriedade, Elixir depende de funções começando com sublinhado para anexar metadados de tempo de compilação aos módulos. Veja exemplo.5
    </p>
    <p> 
        Elixir também inclui cinco formas especiais que seguem o formato sublinhado duplo: __CALLER__/0, __DIR__/0, __ENV__/0 e __MODULE__/0 , usados para recuperar informações em tempo de compilação sobre o ambiente atual, enquanto __STACKTRACE__/0 é usado para recuperar o stacktrace para a exceção atual.
    </p>
    <p> 
        O uso de <b>ponto de exclamação</b>(!) a direita significa uma função ou macro em que os casos de falha levantam uma exceção. A versão sem (!) é a preferida quando deseja-se lidar com resultados diferentes usando correspondência de padrões. Veja exemplo.6
    </p>
    <p> 
        As funções que retornam um <b>booleano</b> são nomeadas com um <b>ponto de interrogação</b> (?) à direita. No entanto, as funções que retornam booleanos e são válidas em guardas seguem outra convenção. Essas funções e macros seguem a convenção Erlang de um is_prefixo, em vez de um ponto de interrogação, precisamente para indicar que são permitidas em cláusulas de guarda. Veja exemplo.7
    </p>
    <p> 
        <b>Nomes especiais :</b> Alguns nomes têm um significado específico em Elixir. <b>Comprimento e tamanho </b> - <b>Size</b> em um nome de função, significa que a operação é executada em tempo constante porque o tamanho é armazenado junto com a estrutura de dados. <b>length</b>, a operação é executada em tempo linear ("tempo O (n)") porque toda a estrutura de dados deve ser percorrida. Veja exemplo.8
    </p>
    <p> <b>Definições:</b> </p> 
        <b>Definição 1.1 :</b> Refere-se ao estilo de escrita em que cada espaço é substituído por um caractere sublinhado (_) e a primeira letra de cada palavra é escrita em minúsculas;<br>
        <b>Definição 1.2 :</b> Rrefere-se à prática de escrever as palavras compostas ou frases, onde cada palavra é iniciada com maiúsculas e unidas sem espaços.<br>     
    </p>    
  
</div>

#### Exemplos: <h4>

##### Exemplo.1 <h5>
~~~
    some_map = %{this_is_a_key: "and a value"}
    is_map(some_map)
~~~
##### Exemplo.2 <h5>
~~~
    OptionParser
~~~
##### Exemplo.3 <h5>
~~~
    
~~~
##### Exemplo.4 <h5>
~~~
    my_app.ex
~~~
##### Exemplo.5 <h5>
~~~
    //valor que não deve ser usado 
    {:ok, _contents} = File.read("README.md")

    //nomes das funções começados com um sublinhado
    defmodule Example do
        def _wont_be_imported do
            :oops
        end
    end

    //funções para anexar metadados 
    String.__info__(:functions)
~~~
##### Exemplo.6 <h5>
~~~
    //versão com (!)

    File.read!("file.txt")
    "file contents"
    File.read!("no_such_file.txt")
    ** (File.Error) could not read file no_such_file.txt: no such file or directory

    //versão sem (!)

    case File.read(file) do
        {:ok, body}      -> # do something with the `body`
        {:error, reason} -> # handle the error caused by `reason`
    end
~~~
##### Exemplo.7 <h5>
~~~
    //Retorna true se term for uma lista de palavras-chave; caso contrário, retorna false
        
        Keyword.keyword?([{Foo, 1}])
            true

        Keyword.keyword?([:key])
            false
    
    //Retorna true se o dado integer for um número par, caso contrário, ele retorna false.
    //Permitido em cláusulas de guarda.

        Integer.is_even(10)
            true

        Integer.is_even(5)
            false


        
~~~
##### Exemplo.8 <h5>
~~~
    map_size(%{a: "foo", b: "bar"}) //retorna o tamanho do map

    String.length("elixir") //retorna o comprimento da string
        
~~~

### VARIÁVEIS <h3>
<div style="text-align: justify">
    <p> 
        Em Elixir as variáveis não funcionam como nas linguagens imperativas, nas quais representam "espaços para valores". Em Elixir váriaveis devem ser vistas como "rótulos para valores".
    </p> 
    <p> <b>Elixir apresenta dois diferentes tipos de variavés :</b> </p> 
        <b>Variáveis ​​globais :</b> Aquelas definidas fora de todas as funções do programa. São acessíveis em qualquer ponto do programa (mesmo em outros módulos do programa);<br>
        <b>Variáveis ​​Locais :</b> Aquelas declaradas no início de um subalgoritmo. São visíveis, ou seja, podem ser utilizadas somente pelo subalgoritmo onde foram declaradas. Outros subalgoritmos ou mesmo o algoritmo principal não podem utiliza-las;<br>
    </p>
    
</div>

### VINCULAÇÃO <h3> 
<div style="text-align: justify">
    
    
</div>


## Escopo, Tempo De Vida e Ambientes de Referência <h2> 

<div style="text-align: justify">
    <p> 
        Analisando cada tipo de váriavel com relação ao Escopo e Tempo De Vida, tem-se:
    </p> 
    <p> <b>Variáveis Globais</b> </p>
    <p> <b>Escopo :</b> São acessíveis em qualquer parte do programa; <br>
        <b>Tempo De Vida :</b> Até que o programa seja finalizado; </p> 
    <p> Variáveis ​​Locais </p>
        <b>Escopo :</b> Dentro do bloco  em que está declarado;<br>
        <b>Tempo De Vida :</b> Até que o controle saia do bloco em que foi declarado;
    </p> 
</div>








