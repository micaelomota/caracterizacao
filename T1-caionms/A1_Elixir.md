<!-- Caracterização da Linguagem Elixir - Caio Nery Matos Santos -->
# Linguagem 1 - Elixir

## Modelo de tradução

<body>
	<p>
		É uma linguagem executada através da Erlang VM, uma máquina virtual conhecida por criar aplicações distribuídas com baixa latência e tolerante a falhas. Por ser executado através dessa Virtual Machine, permite que os desenvolvedores utilizem todas as bibliotecas do Erlang enquanto desenvolvem com o Elixir.
	</p>
	<p>
		O Erlang VM é executado como um processo de sistema operacional. Por padrão, ele executa um thread do SO por núcleo para atingir a utilização máxima da máquina. O número de threads e em quais núcleos eles são executados pode ser definido quando a VM é iniciada. Os processos Erlang são implementados inteiramente pela VM Erlang e não têm conexão com os processos do SO ou threads do SO. Portanto, mesmo se você estiver executando um sistema Erlang com mais de um milhão de processos, ele ainda será apenas um processo do sistema operacional e um thread por núcleo. Portanto, neste sentido, a VM Erlang é uma "máquina virtual de processo", enquanto o próprio sistema Erlang se comporta como um SO e os processos Erlang têm propriedades muito semelhantes aos processos do SO, por exemplo, isolamento.
	</p>
</body>

## Nomes, variáveis e vinculação

### Nomes

#### Casing
<body>
	<p>
		Os desenvolvedores do Elixir devem usar <code>snake_case</code> ao definir variáveis, nomes de funções, atributos de módulo e assim por diante.
	</p>
	<p>
		Aliases, comumente usados como nomes de módulos, são uma exceção, pois devem ser escritos em maiúsculas e escritos em <code>CamelCase</code>, como <code>OptionParser</code>. Para aliases, as letras maiúsculas são mantidas em siglas, como <code>ExUnit.CaptureIO</code> ou <code>Mix.SCM</code>. 
	</p>
	<p>
		Os átomos podem ser escritos em: <code>snake_case</code> ou <code>CamelCase</code>, embora a convenção seja usar a versão snake case em todo o Elixir. 
	</p>
	<p>
		De um modo geral, os nomes dos arquivos seguem a convenção <code>snake_case</code> do módulo que eles definem. Por exemplo, <code>MyApp</code> deve ser definido dentro do arquivo <code>my_app.ex</code>. No entanto, esta é apenas uma convenção. No final das contas, qualquer nome de arquivo pode ser usado, pois eles não afetam o código compilado de forma alguma. 
	</p>
</body>

#### Underscore <code>_foo</code>

<body>
	<p>
		Elixir utiliza de sublinhados em diferentes situações:
	</p>
	<p>
		<ol>
			<li>
				Um valor que não deve ser usado deve ser atribuído a _ ou a uma variável começando com sublinhado.
			</li>
			<li>
				Os nomes das funções também podem começar com um sublinhado. Essas funções nunca são importadas por padrão.
			</li>
			<li>
				Devido a essa propriedade, o Elixir depende de funções que começam com sublinhado para anexar metadados de tempo de compilação aos módulos. Essas funções geralmente estão no formato <code>__foo__</code>. Por exemplo, cada módulo no Elixir tem uma função <code>__info __/1</code>. 
			</li>
			<li>
				Elixir também inclui cinco formas especiais que seguem o formato de sublinhado duplo: <code>__CALLER__/0</code>, <code>__DIR__/0</code>, <code>__ENV__/0</code> e <code>__MODULE__/0</code> recuperam informações de tempo de compilação sobre o ambiente atual, enquanto __STACKTRACE __ / 0 recupera o stacktrace para a exceção atual.
			</li>
		</ol>
	</p>
</body> 

#### Trailing bang <code>foo!</code> 

<body>
	<p>
		Um trailing bang (ponto de exclamação) significa uma função ou macro em que os casos de falha levantam uma exceção. 
	</p>
	<p>
		Muitas funções vêm em pares, como <code>File.read/1<code/> e <code>File.read!/1<code/>. <code>File.read/1<code/> retornará uma tupla de sucesso ou falha, enquanto <code>File.read!/1<code/> retornará um valor simples ou então levantará uma exceção 
	</p>
	<p>
		A versão sem ! é preferível quando você deseja lidar com resultados diferentes usando correspondência de padrões.
	</p>
	<p>
		No entanto, se você espera que o resultado sempre seja bem-sucedido (por exemplo, se você espera que o arquivo sempre exista), a variação bang pode ser mais conveniente e irá gerar uma mensagem de erro mais útil (do que uma correspondência de padrão com falha) em caso de falha.
	</p>
	<p>
		Mais exemplos de funções emparelhadas: <code>Base.decode16/2<code/> e <code>Base.decode16!/2<code/>, <code>File.cwd/0<code/> e <code>File.cwd!/0<code/>.
	</p>
	<p>
		Existem também algumas funções não emparelhadas, sem variante não bang. O trailing bang ainda significa que gerará uma exceção em caso de falha. Exemplo: <code>Protocol.assert_protocol!/1<code/>.
	</p>
</body>

#### Trailing question mark <code>foo?</code>

<body>
	<p>
		As funções que retornam um booleano são nomeadas com um ponto de interrogação à direita. 
	</p>
	<p>
		Exemplos: <code>Keyword.keyword?/1</code>, <code>Mix.debug?/0</code>, <code>String.contains?/2</code>.
	</p>
	<p>
		No entanto, as funções que retornam booleanos e são válidas em guardas seguem outra convenção, descrita a seguir. 
	</p>
</body>

#### <code>is_</code> prefix <code>is_foo</code>

<body>
	<p>
		As verificações de tipo e outras verificações booleanas permitidas nas cláusulas de guarda são nomeadas com um prefixo <code>is_</code>. 
	</p>
	<p>
		Exemplos: <code>Integer.is_even/1</code>, <code>Kernel.is_list/1</code>
	</p>
	<p>
		Essas funções e macros seguem a convenção Erlang de um prefixo <code>is_</code>, em vez de um ponto de interrogação final, precisamente para indicar que são permitidas em cláusulas de guarda.
	</p>
	<p>
		Observe que as verificações de tipo que não são válidas nas cláusulas de proteção não seguem esta convenção. Por exemplo: <code>Keyword.keyword?/1</code>. 
	</p>
</body> 

#### Nomes especiais

<body>
	<p>
		Alguns nomes têm um significado específico em Elixir. Segue esses casos abaixo:
	</p>
</body>

##### length and size

<body>
	<p>
		Quando você vê o tamanho em um nome de função, significa que a operação é executada em tempo constante, porque o tamanho é armazenado junto com a estrutura de dados.
	</p>
	<p>
		Exemplos: <code>Kernel.map_size/1</code>, <code>Kernel.tuple_size/1</code>
	</p>
	<p>
		Quando você vê o comprimento, a operação é executada em tempo linear ("tempo O (n)") porque toda a estrutura de dados deve ser percorrida.
	</p>
	<p>
		Exemplos: <code>Kernel.length/1</code>, <code>String.length/1</code>
	</p>
	<p>
		Em outras palavras, as funções que usam a palavra "size" em seu nome levarão o mesmo tempo, independentemente de a estrutura de dados ser pequena ou enorme. Por outro lado, as funções com "length" no nome levarão mais tempo à medida que a estrutura de dados aumenta de tamanho. 
	</p>
</body>
