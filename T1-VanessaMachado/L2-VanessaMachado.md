# Trabalho 1 : Versão Final L2 <h1>
##### Autoria: Vanessa Machado Araújo <h5>

### Linguagem de Programação : Elixir <h3>

* [HISTÓRICO E APRESENTAÇÃO](#histórico-e-apresentação)
* [CARACTERÍSTICAS DA LINGUAGEM](#características-da-linguagem)
* [CAPACIDADES DA LINGUAGEM](#capacidades-da-linguagem)
* [PRODUTIVIDADE DO DESENVOLVEDOR](#produtividade-do-desenvolvedor)
* [ECOSSISTEMA](#ecossistema)
* [INFORMAÇÕES ADICIONAIS](#informações-adicionais)

## HISTÓRICO E APRESENTAÇÃO 
<div style="text-align: justify"> 
    <p>
        Origem da linguagem Elixir:
    </p>

![Evolução da linguagem Elixir: ](https://github.com/NessaMd/caracterizacao/blob/main/T1-VanessaMachado/evolucaoElixir.jpg)   

<div style="text-align: justify">
    <p>
        Criada por José Valim em 2012, a linguagem elixir se tornou muito útil nos últimos tempos. Foi criada em um projeto de pesquisa e desenvolvimento patrocinado pela Plataformatec. O principal objetivo do desenvolvedor era melhorar a flexibilidade e produtividade da Máquina Virtual Erlang (BEAM), mantendo a funcionalidade das ferramentas fornecidas pela Erlang.
    </p>
    <p>
        A linguagem foi lançada sob a licença Apache. Esta licença permite que as pessoas usem, modifiquem e distribuam  sem pagar royalties aos desenvolvedores. Isso pode ser visto como uma das razões por trás da popularidade da Elixir.
    </p>
</div>

## CARACTERÍSTICAS DA LINGUAGEM 

### PARADIGMA <h3>
<div style="text-align: justify">
    <p>
        Elixir é uma linguagem multi-paradigma, e é considerada uma linguagem de programação funcional, distribuída, orientada a processos e concorrente.        
    </p>
    </p>
        <b>Programação funcional:</b> É composta por métodos que retornam dados, os quais dependem apenas de seus argumentos. Os mesmos resultados são sempre encontrados se os mesmos argumentos forem utilizados, independentemente de fatores externos como tempo de execução ou variáveis globais. É o paradigma de programação mais utilizado atualmente e tem seu foco na construção de tipos complexos (os objetos), colocando  ênfase em funções e procedimentos sem o uso de objetos, e todas as computações são feitas por meio da aplicação ou execução de funções.<br>
        <b>Programação distribuída :</b> Baseada na ideia de dividir uma aplicação em dezenas, centenas ou até milhares de diferentes aplicações menores que se comunicam e compartilham diferentes recursos e funcionalidades, utilizando uma rede integrada de dispositivos. Isso resulta em uma aplicação paralelizada e redundante, aumenta a responsividade, eficiência, rapidez e estabilidade da aplicação, pois caso uma aplicação falhe, suas funções podem ser distribuídas para serem executadas pelas demais.<br>
        <b>Programação orientada a processos:</b> Delimita a separação de dados e dos métodos que agem sobre eles. Isso permite uma paralelização de redes distribuídas mais eficiente e organizada com processos que compartilham um mesmo conjunto de dados.<br>
        <b>Programação concorrente :</b> Diversas tarefas são executadas dentro do mesmo período de tempo. O início de uma tarefa pode acontecer antes do término de outra, mas não são obrigatoriamente executadas no mesmo instante<br>
    <p>
</div>

### SISTEMA DE TIPAGEM <h3>
<div style="text-align: justify">
    <p>
        Elixir é uma linguagem de tipagem dinâmica. Isso quer dizer que os tipos não são declarados no código e, portanto, são conhecidos/checados em tempo de execução. 
    <p>
</div>

### MODELO DE TRADUÇÃO <h3>
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

### NOMES E VARIÁVEIS <h3>

#### NOMES: <h4>
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
    my_app.ex
~~~

##### Exemplo.4 <h5>
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

##### Exemplo.5 <h5>
~~~
    //versão com (!)

    File.read!("file.txt")
    "file contents"
    File.read!("no_such_file.txt")
    ** (File.Error) could not read file no_such_file.txt: no such file or directory

    //versão sem (!)

    case File.read(file) do
        {:ok, body}      -> # faze algo com o `body`
        {:error, reason} -> # lidar com o erro causado por `reason`
    end
~~~

##### Exemplo.6 <h5>
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

##### Exemplo.7 <h5>
~~~
    map_size(%{a: "foo", b: "bar"}) //retorna o tamanho do map

    String.length("elixir") //retorna o comprimento da string
        
~~~

#### VARIÁVEIS: <h4>
<div style="text-align: justify">
    <p> 
        Em Elixir as variáveis não funcionam como nas linguagens imperativas, nas quais representam "espaços para valores". Em Elixir váriaveis devem ser vistas como "rótulos para valores".
    </p> 
    <p> <b>Elixir apresenta dois diferentes tipos de variavés :</b> </p> 
        <b>Variáveis ​​globais :</b> Aquelas definidas fora de todas as funções do programa. São acessíveis em qualquer ponto do programa (mesmo em outros módulos do programa);<br>
        <b>Variáveis ​​Locais :</b> Aquelas declaradas no início de um subalgoritmo. São visíveis, ou seja, podem ser utilizadas somente pelo subalgoritmo onde foram declaradas. Outros subalgoritmos ou mesmo o algoritmo principal não podem utiliza-las;<br>
    </p>
</div>

### ESCOPO, TEMPO DE VIDA e AMBIENTES DE REFERÊNCIA: <h3> 
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

## CAPACIDADES DA LINGUAGEM 

### MACROS E METAPROGRAMAÇÃO: <h3>
<div style="text-align: justify">
    <p>
    Metaprogramação é escrever programas que manipulam outros programas ou a si próprios.    Macros é uma funcionalidade do Elixir que permite a extensão da linguagem. Em outras palavras, é possível criar “código que escreve código” em tempo de compilação. É bem útil quando se quer adicionar funcionalidades diferentes na linguagem, ou um “sintax sugar” para deixar o código mais legível.
    </p>
</div>

### SEGURANÇA E CONFIABILIDADE: <h3>
<div style="text-align: justify">
    <p>
        Com relação a segurança, sabe-se que uma das características mais positivas da linguagem  Elixir é sua tolerância a falhas. Ela fornece mecanismos de segurança que permitem que a aplicação continue funcionando mesmo quando algo dá errado. Os processos alertam sobre uma falha nos processos dependentes, mesmo em outros servidores, para que os problemas possam ser corrigidos imediatamente.
    </p>
    <p>
        Como já dito em outro tópico, foi na base do Erlang que José Valim desenvolveu o Elixir. Sendo mantido todo o poder da linguagem mãe, como é o caso da confiabilidade.essa manuntenção é possível pois o Elixir compila para a máquina virtual do Erlang, o BEAM (Bogdan’s Erlang Abstract Machine).
    </p>
</div>

### PERFORMANCE: <h3>
<div style="text-align: justify">
    <p>
        Elixir é uma das melhores linguagens de programação para aplicativos de alta performance.       
    </p>
</div>

### ESCALABILIDADE: <h3>
<div style="text-align: justify">
    <p>
        Como o Elixir é executado em Erlang VM, ele é capaz de executar aplicativos em vários nós de comunicação. Isso facilita a criação de aplicativos da Web e IoT maiores que podem ser escalados em vários servidores diferentes. Ter vários servidores virtualizados em um sistema distribuído também leva a um melhor desempenho do aplicativo.
    </p>
</div>

### CUSTO: <h3>
<div style="text-align: justify">
    <p>
    Elixir é ótimo para aplicações que precisam ter alta disponibilidade, apresenta muito boa capacidade de resposta. Sua aplicação pode responder a requisições independente de quantos clientes estão conectados. Ela nunca quebra. Mesmo que você tenha uma código com erro em alguma linha, o restante da aplicação continua funcionando. Com tudo isso, o código Elixir é fácil de crescer e manter, e isso reflete um baixo custo.
    </p>
</div>

## PRODUTIVIDADE DO DESENVOLVEDOR 
<div style="text-align: justify">
    <p>
        Com o Elixir, os desenvolvedores obterão maior produtividade com menos código. Eles podem escrever código fácil de testar e também de manter. Elixir também é muito escalável e possui um sistema de tolerância a falhas embutido para desastres naturais ou outros eventos imprevistos.  
    </p>
</div>

### FRAMEWORS: <h3>
<div style="text-align: justify">
    <p>
        Alguns dos Frameworks mais conhecidos do Elixir são:
    </p>
    <p>
    <b>Phoenix:</b> Permite criar aplicativos interativos na web rapidamente. Pode ser utilizado, portanto, para o desenvolvimento web, de APIs e aplicativos HTML5.<br>
    <b>Nerves:</b> Trata-se da plataforma e infraestrutura de código aberto que permite criar, implantar e gerenciar dispositivos IoT com total segurança, velocidade e em escala. Também serve para Embedded.<br>
    <b>Plug:</b> Destinado para aplicações na web.<br>
    <b>Sugar:</b> Muito utilizado para desenvolvimento web, garantindo rapidez, facilidade e eficácia ao projeto.<br>
    </p>
</div>

### FERRAMENTAS: <h3>
<div style="text-align: justify">
    <p>
        O Elixir conta, por exemplo, com o Mix, uma ferramenta de compilação que fornece tarefas para criar, compilar, testar aplicativos e gerenciar projetos e dependências. E através do Hex, seu package manager oficial, é possível encontrar uma quantidade gigante de libs, incluindo as do Erlang. 
    </p>
    <p>
        Disponibiliza o ExUnit para a realização de testes unitários e, ainda, possui um terminal interativo, o IEx (Elixir’s Interactive Shell), que oferece funcionalidades como: Autocompletar, Histórico e Avaliação de expressões.
    </p>
</div>

### SINTAXE, SEMÂNTICA e OPERAÇÕES PREDEFINIDAS: <h3>

#### LEGIBILIDADE e REDIGIBILIDADE: <h4>
<div style="text-align: justify">
    <p>
        Elixir apresenta sintaxe extremamente legível e inspirada em Ruby, uma linguagem conhecida por ser focada no bem estar do programador. 
    </p>
    <p>
        Podemos, por exemplo, utilizar “?” ou “!” na nomenclatura de funções e variáveis, tornando-as mais legíveis e agradáveis. Parênteses não são obrigatórios e não precisamos declarar o retorno explicitamente em funções com “return”. Também temos “Pattern Matching” (reconhecimento de padrões),”Guards” e o invejável “Pipe Operator”, que torna possível economizar diversas linhas de código e tornar a legibilidade muito alta.
    </p>
    <p>
        Com Elixir temos um código muito mais legível e intuitivo e com uma redigibilidade fácil, permitindo liberdades e abstrações.
    </p>
</div>

#### ESTRUTURAS DE CONTROLE: <h4> 
<div style="text-align: justify">
    <p> 
        Uma estrutura de controle é uma forma sintática em uma linguagem de programação que expressa o fluxo de controle sobre uma lista específica de instruções para tomar decisões entre o caminho alternativo ou caminhos dados e executa as instruções na sequência em que aparecem, uma por uma. Essa condição é chamada de cumprimento da sequência. 
    </p> 
    <p> 
        Em Elixir, existem alguns tipos de estruturas de controle. 
    </p> 
    <p> <b>A saber :</b> </p>            
    </p>
</div>

<div style="text-align: justify"> 
        <b>1. if e unless :</b> São definidos como macros, não como construções de linguagem. Os únicos valores falsos são "nil" e o booleano false.         
    </p>
</div>

<div style="text-align: justify"> 
        <b>1.1 if :</b>             
    </p>
</div>

~~~
    iex> if String.valid?("String") do
    ...>   "String válida!" //caso seja string
    ...> else
    ...>   "String inválida!" //caso não seja string
    ...> end  
~~~

<div style="text-align: justify"> 
        <b>1.2 unless :</b>             
    </p>
</div>

~~~
    iex> unless is_integer("String") do // Caso não respeite a condição, 
                                            entra no bloco
    ...>   "Não é um inteiro!"
    ...> end
    "Não é um inteiro!"  
~~~

<div style="text-align: justify"> 
        <b>2. case :</b> A instrução Case pode ser considerada uma substituição da instrução switch presente em linguagens imperativas. Case pega uma variável e aplica a correspondência de padrões a ela com diferentes casos. Se houver correspondência de qualquer caso,  executa o código associado a esse caso e sai da instrução. Se nenhuma correspondência for encontrada, ele sai da instrução com um CaseClauseError exebindo que nenhuma cláusula correspondente foi encontrada. Deve-se, sempre, ter um caso com "_" que corresponde a todos os valores. Isso ajuda na prevenção do erro mencionado acima e é comparável ao caso padrão em declarações switch-case.         
    </p>
</div>

~~~
    case value do
        match1 
	    match2 
	    match3 
	    ...
	    _ // Executar caso nenhuma correpondência for encontrada 
    end 
~~~

<div style="text-align: justify"> 
        <b>3. cond :</b> As declarações cond são usadas quando queremos executar um código com base em várias condições. Funciona como uma construção if, else em várias outras linguagens de programação.    
    </p>
</div>

~~~
    cond do
        boolean_expressão1 //Executa se a condição for verdadeira
        boolean_expressão2 //Executa se a condição for verdadeira
        ...
        true // Executa se nenhuma das condições acima for verdadeira
    end
~~~

<div style="text-align: justify"> 
        <b>4. With:</b> útil quando é possível usar instruções aninhadas ou em situações que não podem ser combinadas de forma limpa. A estrutura with é composta pelas palavras-chave, os geradores e, finalmente, uma expressão.     
    </p>
</div>

~~~
    iex> usuario = %{primeiro: "João", ultimo: "Silva"}
    %{primeiro: "João", ultimo: "Silva"}
    iex> with {:ok, primeiro} <- Map.fetch(usuario, :primeiro),
    ...> {:ok, ultimo} <- Map.fetch(usuario, :ultimo),
    ...> do: ultimo <> ", " <> primeiro

    Saída: "Callan, Sean"
~~~

<div style="text-align: justify"> 
        <b>5. do/end:</b> Permitem definir o bloco inicial e final a ser executado se uma dada condição for atendida.     
    </p>
</div>

~~~
   iex> if true do
        a = 1 + 2
        a + 10
        end 
~~~

## ECOSSISTEMA 
<div style="text-align: justify">
    <p>
        Embora Elixir seja uma linguagem bastante jovem, tem tempo para desenvolver uma comunidade de usuários ativa, onde até mesmo engenheiros altamente qualificados estão dispostos a ajudar e compartilhar seus conhecimentos. Além disso, há muita ajuda ou tutoriais facilmente disponíveis para desenvolvedores que trabalham com Elixir.
    </p>
    <p>
        Apresenta ótima documentação. Tudo o que precisamos  saber sobre a linguagem está disponível na internet, de forma bem clara. Isso geralmente é um déficit em linguagens que estão a pouco tempo no mercado. Mas no caso de Elixir, isso não ocorre.
    </p>
    <p>
        Por ser uma linguagem extremamente jovem, o Elixir, no ano de 2021, de acordo com pesquisas, é usado por apenas 1,74% dos programadores. Ainda não é amplamente utilizada pelo mercado, embora grandes empresas de tecnologia, como B2W, Locaweb, iFood, Pinterest e Globo Play, já tenham aderido a ela também. No entanto apresenta uma crescente em sua difusão. 
     </p>
</div>

## INFORMAÇÕES ADICIONAIS  

### REFERÊNCIAS: <h3> 
<p> 
    https://hexdocs.pm/elixir/1.12/naming-conventions.html#trailing-bang-foo
</p> 

<p>
    https://medium.com/@fxn/how-does-elixir-compile-execute-code-c1b36c9ec8cf
</p> 

<p>
    https://elixir-lang.readthedocs.io/en/latest/technical/scoping.html
</p> 

<p>
    https://medium.com/@bdias.ti/elixir-quando-e-como-usar-670a84971f78
</p> 

<p> 
https://elixirbridge.org/02_Intro_to_Elixir/07-control-structures.html
</p>

<p> 
https://elixirschool.com/en/lessons/basics/control_structures#with-3
</p>

<p> 
http://elixir-school.herokuapp.com/en/lessons/basics/control-structures#with
</p>

<p> 
https://www.tutorialspoint.com/elixir/elixir_decision_cond.htm
</p>

<p> 
https://www.tutorialspoint.com/elixir/elixir_loops.htm
</p>

<p> 
https://www.tutorialspoint.com/elixir/elixir_decision_case.htm
</p>

<p> 
https://medium.com/true-henrique/elixir-10-motivos-para-aprender-6cd4d6876f05
</p>

<p>
https://www.cleverism.com/skills-and-tools/elixir/ 
</p>

<p> 
https://www.hostgator.com.br/blog/elixir-linguagem-programacao-brasileira/
</p>

<p> 
https://outsourceit.today/how-good-is-elixir-performance/
</p>

<p>
http://www.each.usp.br/petsi/jornal/?p=2459
</p>