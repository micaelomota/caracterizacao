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
