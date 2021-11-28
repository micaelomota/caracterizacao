<!-- Caracterização da Linguagem Java - Caio Nery Matos Santos -->
# Linguagem 1 - Java

## Modelo de tradução

<body>
	<p> 
		Java é uma linguagem compilada e interpretada. O compilador Java, chamado javac, compila o código-fonte do Java para um código de nível intermediário chamado códigos de bytes. Esses códigos de bytes não são diretamente executáveis em qualquer plataforma de hardware existente; mas esses códigos são interpretados pelo interpretador Java, o qual pode operar por si mesmo ou como parte de um navegador Web. Podemos dizer então que sua compilação ocorre em duas etapas, onde a primeira vai envolver um compilador independente do SO e na segunda através da Java Virtual Machine, que é adaptada para cada tipo de SO que suporta seu código.
	</p>
	<p>
		Em intermédio entre a primeira e a segunda compilações, ao converter o código-fonte em bytecode, o compilador segue as seguintes etapas de forma cronológica:
 		<ul>
			<li><b>Etapa de Análise</b>: Lê os arquivos de origem <code>.java</code> e faz o mapeamento da sequência de tokens resultante em nós de uma AST <b>Árvore Sintática Abstrata (Abstract Sintax Tree).</b></li>
			<li><b>Enter</b>: Insere elementos para as suas definições na tabela de símbolos.</li>
			<li><b>Anotações de Processos</b>: Processa as anotações encontradas nas unitdades de compilação especificadas.</li>
			<li><b>Atribuição</b>: Atribui as árvores de sintaxe. Esta etapa inclui resolução de nome, verificação de tipo e dobra constante</li>
			<li><b>Fluxo/Flow</b>: Executa a análise de fluxo da etapa anterior, incluindo as verificações de atribuições e também os acessos.</li>
			<li><b>Desugar</b> Reescreve as AST e traduz o que se chama de <i>Sintatic Sugar</i>.</li>
			<li><b>Geração</b>: Gera os arquivos do tipo <code>.Class</code></li> 
 		</ul>
 	</p>
</body>

## Compilação e Execução

<body>
	<p>
		As cinco fases pelas quais a aplicação passa até ser realmente executada podem ser divididas em:
		<ul>
			<li>
				<b>Criação/edição de um programa Java</b>: Nesta primeira fase se dá a criação ou edição de arquivos em um programa editor, onde são inseridos os códigos pelo programador, os quais são posteriormente salvos em uma unidade física de armazenamento como um programa de extensão <code>.java</code>.
			</li>
			<li>
				<b>Compilação do programa Java em bytecodes</b>: Supondo que em um exemplo geramos um arquivo chamado <code>Ola.java</code>, na hora da compilação, o compilador produz um arquivo <code>.class</code> chamado <code>Ola.class</code> onde contém a versão compilada. O compilador Java converte o código-fonte em bytecodes que representam tarefas a serem executadas na fase de execução. Os bytecodes são executados pela Java Virtual Machine (JVM) - uma parte do JDK e a base da plataforma Java. Máquina Virtual (Virtual Machine - VM) é um aplicativo software que simula um computador, mas oculta o sistema operacional e o hardware subjacente dos programas que interagem com ela, o que garante a possibilidade de execução de programas Java em vários sistemas operacionais distintos.
			</li>
			<li>
				<b>Carregando um programa na memória</b>: A JVM armazena o programa na memória para executá-lo, efetuando o carregamento. O carregador de classe da JVM pega os arquivos <code>.class</code> que contêm os bytecodes do programa e os transfere para a memória primária.
			</li>
			<li>
				<b>Verificação de bytecode</b>: Enquanto as classes são carregadas, o verificador examina seus bytecodes para assegurar que são válidos e não violam restrições de segurança do Java.
			</li>
			<li>
				<b>Execução</b>: As JVMs executam bytecodes utilizando uma combinação de interpretação chamada compilação JIT (Just In Time) - conhecido como compilador Java HotSpot. O Java HotSpot traduz os bytecodes para a linguagem de máquina, quando a JVM encontra novamente essas partes compiladas, o código de linguagem de máquina é executado mais rápido. Uma explicação mais detalhada é que o programa Java passa por duas fases de compilação que são:
				<ul>
					<li>
						Quando o código-fonte é traduzido em bytecodes que acaba tendo uma portabilidade entre JVMs em diferentes plataformas do computador
					</li>
					<li>
						E a outra é durante a execução, os bytecodes são traduzidos em linguagem de máquina para o computador real em que o programa é executado.
					</li>
				</ul>
			</li>
		</ul>
	</p>
</body>

## Nomes, variáveis e vinculação

### Nomes

<body>
	<p>
		As convenções de nomenclatura tem como objetivo tornar os programas mais compreensíveis, tornando-os mais fáceis de ler. Eles podem também fornecer informações sobre a função do identificador, por exemplo, quer se trate de um pacote, constante, ou de classe que pode ser útil na compreensão do código.
	</p>
    <p>
		As convenções de nomes mais impactantes são:
		<li><b>Packages</b>: O prefixo do nome do pacote deve ser único, deve sempre ser escrito em letras minúsculas todo-ASCII e deve ser um dos nomes de domínio de nível superior, atualmente com, edu, gov, mil, net, org, códigos de duas letras identificando os países, tal como especificado na norma ISO 3166, 1981. Componentes subseqüentes do nome do pacote varia de acordo com uma organização próprias convenções de nomenclatura internos. Tais convenções podem especificar que certos componentes do nome do diretório haver divisão, departamento, projeto, máquina, ou nomes de login.</li>
		<div align=center><code> com.apple.quicktime.v2 </code></div>
		<li><b>Classes</b>: Os nomes de classe devem ser substantivos, em maiúsculas e minúsculas com a primeira letra de cada palavra interna em maiúscula. Tente manter seus nomes de classe simples e descritivo. Sempre evite palavras-ligadas , evite todas siglas e abreviaturas, seja semântico. </li>
		<div align=center><code> class MyClass{} </code></div>
		<li><b>Interfaces</b>: Nomes de interfaces devem ser usadas com as primeiras letras em maiúsculas como nome de classes.</li>
		<div align=center><code> interface MyInterface </code></div>
		<li><b>Methods</b>: Métodos devem ser verbos, com a letra minúscula em primeiro lugar, com a primeira letra de cada palavra interna em maiúscula.</li>
		<div align=center><code> public void myMethod() </code></div>
		<li><b>Variables</b>: Os nomes de variáveis não deve começar com underscore _ ou sinal de dólar $ personagens, mesmo que ambos não são permitidos. Os nomes de variáveis devem ser curtos, mas significativo. A escolha de um nome variável deve ser mnemônico, isto é, concebidos para indicar ao observador casual a intenção da sua utilização. Um personagem nomes de variáveis devem ser evitadas, exceto para temporários "descartáveis" variáveis. Os nomes comuns para variáveis temporárias são i, j, k, m, n e para inteiros, c, d, e e para caracteres.</li>
		<div align=center><code> char myVariable</code></div>
		<li><b>Constants</b>: Os nomes de variáveis declaradas constantes de classes e de constantes ANSI deve ser todo em letras maiúsculas com palavras separadas por sublinhados ("_").</li>
		<div align=center><code> static final int MIN_WIDTH = 4 </code></div>
	</p>
</body>

### Variáveis

<body>
	<p>
		Uma variável é uma estrutura que permite armazenar dados na memória durante a execução do programa, para processamento de informações. Todas as variáveis devem ser declaradas antes que possam ser usadas. Declarar uma variável significa criá-la em algum ponto do programa. A linguagem Java é fortemente tipada. Isso significa que cada variável obrigatoriamente deve ter um tipo declarado antes que possa ser utilizada. Podemos dividir as variáveis em 3 tipos:
	</p>
		<ol>
			<li><b>Variáveis Locais</b>: Podem ser utilizadas dentro do método onde foram declaradas, não sendo acessíveis de outros pontos do programa.</li>
			<li><b>Variáveis de Instância</b>: Uma classe pode conter variáveis que são declaradas fora dos métodos, chamadas de Variáveis de Instância. São usadas pelos objetos para armazenar seus estados. Seus valores são específicos de cada instância e não são compartilhados entre as instâncias.</li>
			<li><b>Variáveis de Classe</b>: Variáveis declaradas como estáticas são variáveis compartilhadas entre todos os objetos instanciados a partir de uma classe. Por isso, essas variáveis também são conhecidas como Variáveis de Classe.</li>
		</ol>
	</p>
</body>

### Vinculação (Binding)

<body>
	<p>
		Os dois tipos de vinculação que temos na linguagem são:
	</p>
	<p>
      <ul>
        <li><b>Vinculação Estática</b>: A variável é determinada pelo compilador antes do programa ser executado, ou seja, em tempo de compilação. Temos este tipo de vinculação quando há algum método <code>private</code>, <code>static</code> ou <code>final</code>.</li>
        <li><b>Vinculação Dinâmica</b>: A variável é determinada em tempo de execução. Ocorre em situações de código mais livre de encapsulamento, tornando o código mais versátil.</li>
      </ul>
    </p>
</body>

## Escopo, tempo de vida e ambientes de referência.

### Escopo e tempo de vida

<body>
	<p>
		Escopo é a vida de uma variável em Java, tratando-se dos locais nos quais ela pode ser acessada. Em Java, o escopo de variáveis vai de acordo com o bloco onde ela foi declarada. A variável é criada no primeiro acesso a ela e destruída após o interpretador sair do bloco de execução ao qual ela pertence.
	</p>
	<p>
		Logo, se uma variável for criada dentro de um determinado método, quando este método chegar ao final, esta variável é  destruída. Se uma variável for declarada no começo da classe (fora dos métodos), estas variáveis podem ser acessadas por todos os métodos da classe. São os chamados atributos da classe.
	</p>
</body>

### Ambientes de Referência

<body>
	<p>
		A linguagem Java é dita de escopo estático e apesar de ter recursos os quais podemos fazer vinculações dinâmicas, suas variáveis são referenciadas dentro de um ambiente estático.
	</p>
</body>

## Estruturas de controle

<body>
	<p>
		Controle de fluxo é a habilidade de ajustar a maneira como um programa realiza suas tarefas. Por meio de instruções especiais, chamadas comandos, essas tarefas podem ser executadas seletivamente, repetidamente ou excepcionalmente. Não fosse o controle de fluxo, um programa poderia executar apenas uma única seqüência de tarefas, perdendo completamente uma das características mais interessantes da programação: a dinâmica.
	</p>
	<p>
		Podemos classificar os comandos aceitos pela linguagem Java em basicamente quatro categorias: 
	</p>
	<p>
		<ol>
			<li>
				Tomada de decisões: <code>if-else, switch-case</code>
			</li>
			<li>
				Laços ou repetições: <code>for, while, do-while</code>
			</li>
			<li>
				Apontamento e tratamento de excessões: <code>try-catch-finally, throw</code>
			</li>
			<li>
				Outros: <code>break, continue, label:, return</code>
			</li>
		</ol>
	</p>
</body>

### Execução Condicional

<body>
	<p>
		A forma mais simples de controle de fluxo é o comando if-else. Ele é empregado para executar seletivamente ou condicionalmente um outro comando mediante um critério de seleção. Esse critério é dado por uma expressão, cujo valor resultante deve ser um dado do tipo booleano, isto é, true ou false. Se esse valor for true, então o outro comando é executado; se for false, a excecussão do programa segue adiante. 
	</p>
	<p>
		Uma variação do comando if-else permite escolher alternadamente entre dois outros comandos a executar. Nesse caso, se o valor da expressão condicional que define o critério de seleção for true, então o primeiro dos outros dois comandos é executado, do contrário, o segundo. 
	</p>
</body>

### Execução Seletiva de Múltiplos Comandos

<body>
	<p>
		Frequentemente, desejamos que um único comando (ou único bloco de comandos) de uma lista seja executado mediante um dado critério. Isso pode ser feito através do aninhamento ou acoplamento de vários comandos if-else.
	</p>
	<p>
		A presença do último else, juntamente com seu comando, é opcional. Neste código, o [comando 1] será executado (e os demais saltados) caso a primeira condição seja true, o [comando 2] será executado (e os demais saltados) caso a primeira condição seja false e a segunda condição seja true, e assim sucessivamente. O [comando n] (se houver) somente será executado (e os demais saltados) caso todas as condições sejam false. 
	</p>
</body>

#### Execução Seletiva por Valores

<body>
	<p>
		Assim como no caso execução seletiva de múltiplos comandos, há situações em que se sabe de antemão que as condições assumem o valor true de forma mutuamente exclusiva, isto é, apenas uma entre as condições sendo testadas assume o valor true num mesmo momento. Nesses casos, a linguagem Java (como também as linguagem C, C++ e Pascal) provê um comando de controle de fluxo bastante poderoso. 
	</p>
	<p>
		A [expressão] pode ser qualquer expressão válida. Esta é avaliada e o seu valor resultante é comparado com as constantes distintas [constante 1], [constante 2], ..., [constante n]. Caso esse valor seja igual a uma dessas constantes, o respectivo comando é executado (e todos os demais são saltados). Se o valor for diferente de todas essas constantes, então o comando presente sob o rótulo default: é executado (e todos os demais são saltados), caso este esteja presente.
	</p>
</body>

### Laço de iteração enquanto/faça

<body>
	<p>
		Frequentemente, desejamos que uma tarefa seja executada repetidamente por um programa enquanto uma dada condição seja verdadeira. Isso é possível pela utilização do comando while. Este comando avalia uma expressão condicional, que deve resultar no valor true ou false. Se o valor for true, então o comando subjacente é executado; se a expressão for false, então o comando é saltado e a execução prossegue adiante. A diferença é que após executar o comando subjacente, a expressão condicional é novamente avaliada e seu resultado novamente considerado. Desse modo a execução do comando subjacente se repetirá, até que o valor da expressão condicional seja false. Observe, porém, que a expressão é avaliada antes de uma possível execução do comando subjacente, o que significa que esse comando pode jamais ser executado. 
	</p>
	<p>
		Uma das observações importantes é sempre certificar que não ocorra o laço infinito (um laço que nunca para, pois a condição sempre é verdadeira). Caso tenha alguma chance de entrar no laço infinito, coloque um contador ou user o laço for. 
	</p>
</body>

### Laço de iteração faça/enquanto

<body>
	<p>
		Um outro tipo de laço de repetição, similar ao enquanto/faça, é o laço faça/enquanto, este é introduzido por um par de comandos do/while.
	</p>
	<p>
		Diferente do laço enquanto/faça, este tipo de laço de repetição executa o comando e em seguida avalia a expressão condicional. A repetição ocorre se o valor dessa expressão for true. Se esse valor for false, a execução prossegue adiante do while.
	</p>
</body>

### Laço de iteração com contagem

<body>
	<p>
		Em certas situações, precisamos de laços de repetições nos quais alguma variável é usada para contar o número de iterações. Para essa finalidade, temos o laço for. Este é o tipo de laço mais geral e mais complicado disponível na linguagem Java. 
	</p>
	<p>
		Isto que dizer que o laço for avalia inicialmente a expressão de inicialização. Em seguida, avalia a expressão condicional. Se o valor desta for true, então o comando é executado,  a segunda expressão é avaliada em seguida, e finalmente o laço volta a avaliar novamente a expressão condicional. Do contrário, se o valor da expressão for false, a execução prossegue adiante do laço for. Este arranjo é muito conveniente para manter variáveis de contagem.
	</p>
</body>

### Break e continue

<body>
	<p>
		O comando break é usado para interromper a execução de um dos laços de iteração vistos acima ou de um comando switch. Este comando é comumente utilizado para produzir a parada de um laço mediante a ocorrencia de alguma condição específica, antes da chegada do final natural do laço.
	</p>
	<p>
		O comando continue tem a função de pular direto para final do laço, mas em vez de interromper o laço como no break, ele continua executando o próximo passo do laço. Não vamos ficar estudando o uso de continue por ser puco usual na programação estruturada. 
	</p>
</body>
