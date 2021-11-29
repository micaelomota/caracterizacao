<!--
Recomendações:
1. A
2. B

Contribuidores:
+ Kenia e Luiz
+ Mauricio Santiago, Gustavo Santos, Matheus Novais, Ivens Joris, Matheus Silva
+ Álvaro Souza Oliveira; Carlos Mosselman Cabral Neto; Thiago Vieira Souza Andrade; Caio Nery Matos Santos; Vanessa Machado Araújo
+ Daniel

Fontes:
+ Criação do TOC
  + [Table of contents generated with markdown-toc](http://ecotrust-canada.github.io/markdown-toc/)
---

-->

# Guia para Caracterização de Linguagens de Programação

+ Linguagem de Programação: **Python**

  + [Apresentação e histórico](#apresenta--o-e-hist-rico)
  + [Características da Linguagem](#caracter-sticas-da-linguagem)
  + [Capacidades da Linguagem](#capacidades-da-linguagem)
  + [Produtividade do Desenvolvedor](#produtividade-do-desenvolvedor)
  + [Ecossistema](#ecossistema)
  + [Informações Adicionais](#informa--es-adicionais)
  + [Referências](#refer-ncias)

## Apresentação e histórico

Python é uma linguagem de programação multiparadigma de alto nível. Foi publicada em 1991 pelo seu criador Guido van Rossum. Seu nome é inspirado no programa de televisão britânico _Monty Python's Flying Circus_. Com a continuação do seu desenvolvimento, Python foi aos poucos ganhando popularidade devido à sua sintaxe simples, e alta legibilidade e redigibilidade, facilidade de extensão e flexibilidade. A linguagem está atualmente na versão 3.10 e seu desenvolvimento está ativo, sendo atualizada constantemente com novos recursos e otimizações. É atualmente uma das linguagens de programação mais populares no mundo, figurando em [alguns rankings](https://www.tiobe.com/tiobe-index/) em primeiro lugar. Atualmente é muito usada para projetos de inteligência artificial, visualização e ciência de dados, scripting para automação de tarefas e desenvolvimento web back-end.

##### Árvore genealógica do Python:

![image](./res/python-tree.png)

## Características da Linguagem

+ Paradigma
  : Python é uma linguagem multiparadigma que suporta POO, funcional, procedural e imperativa. Seu suporte a programação funcional não é ideal, porém, pois alguns constructos importantes para programação funcional não são simples de se fazer nela, tal qual estruturas de dados imutáveis por exemplo, e não há [(nem provavelmente será adicionada)](http://neopythonic.blogspot.com/2009/04/final-words-on-tail-calls.html) optimização de chamada de cauda. Embora não suporte nativamente a programação lógica, esse paradigma pode ser explorado através de módulos/extensões como o PySwip, interfaceando entre Python e SWI-Prolog. Python não obriga a orientação a objetos, mas a linguagem é implementada de forma que tudo é objeto, até mesmo as classes em si, tipos básicos e funções.
+ Propósito
  : Guido van Rossum, o criador da linguagem, começou a construí-la no seu tempo livre como um projeto para ser utilizado no seu trabalho, que envolvia administração de sistemas no sistema operacional [Amoeba](https://en.wikipedia.org/wiki/Amoeba_(operating_system)). Guido buscava criar uma linguagem para escrever scripts com maior capacidade de interação com as chamadas de sistema do que bsh, porém muito mais redigível que C. Para isso, se inspirou majoritariamente linguagens ABC e Modula.  
+ Sistema de Tipagem
  : Python é dinamicamente tipada, segue a ideia de "duck typing" e não requer declarações de tipos de variáveis antes de sua utilização, usando inferência de tipo ao atribuir um valor a um nome previamente inexistente no ambiente de referência atual. Apesar disso, Python é type-safe pois checa os tipos antes de realizar qualquer operação, resultando em exceção se as variáveis e valores envolvidos são de tipos inadequados, e também não permite cópia direta de uma região de memória inicializada com um tipo diferente do tipo do destino. A linguagem também oferece anotação opcional de tipos sem nenhuma consequência em tempo de compilação ou de execução (apenas aumenta legibilidade e auxilia o funcionamento de linters e utilitários checadores de tipos).
  A linguagem oferece os tipos escalares int, float, complex, bool e None. O tipo int tem precisão arbitrária nativamente, crescendo de acordo com a necessidade. Também oferece os tipos estruturados embutidos list, tuple, range, set, dict, str, bytearray e bytes, e para criar dados estruturados arbitrários há a declaração de classes.
  Em relação à orientação a objetos, Python oferece uma abordagem incompleta mas flexível. Métodos e atributos nunca são verdadeiramente privados, mas há uma convenção de que atributos cujo nome começa com dois underlines (__varname) devem ser tratados como privados. Pode-se oferecer acesso indireto a esses atributos através de getters e setters (anotação @property). Python suporta herança múltipla, embora seu algoritmo de ordem de resolução de métodos seja um pouco complicado. Não há suporte para declaração de interfaces. Polimorfismo é obtido através do uso de herança (polimorfismo de subtipo) e de "duck typing", não existindo polimorfismo paramétrico.
  Há apenas equivalência de tipos por nome. Há conversão implícita em certas operações se suportado. Sobrecarga de tipos é possível através de herança (declarar uma classe que heda de um certo tipo sem nenhuma modificação).
+ Ambiente de Execução
  : A linguagem é interpretada, e há diversos interpretadores implementados diferentemente para executá-la. Cada um desses oferece um ambiente de execução diferente com acesso a ferramentas distintas, mas o interpretador original da linguagem (CPython) oferece uma API para programas em C que implementa toda a comunicação necessária entre o Python e o C.
+ Implementação
  : A implementação original é chamada CPython, escrita em C. O CPython compila o código em Python para seu bytecode próprio e o interpreta. Outras implementações famosas são PyPy, que implementa um compilador para código de máquina nativo JIT que oferece um desempenho muito maior sem sacrificar o dinamismo da linguagem, Jython que compila para bytecode da JVM - Java Virtual Machine, permitindo interfaceamento e inserção dentro de programas Java e vice-versa e Cython, que é uma versão compilada do Python com ferramentas adicionais.
+ Custos
  : Embora a compatibilidade do Python com módulos escritos em C seja muito boa, os mecanismos de garbage collection e falta de mecanismos de gerencialmento de memória thread-safe têm um grande custo de performance devido principalmente ao mecanismo chamado Global Interpreter Lock (GIL). O GIL impede que uma seção de bytecode ou uma região de memória do Python seja executada por múltiplas threads ao mesmo tempo. Dessa forma, multithreading no Python traz muitas vezes ganhos de performance muito aquém do esperado. Sua tipagem dinâmica extremamente flexível também causa grandes perdas de performance, assim como a falta de compilação JIT na sua implementação de referência. Quando considerada como um todo entre as linguagens de programação mais populares, Python é sem dúvida a que tem a pior performance em geral. Isso é parcialmente contornado, entretanto, ao utilizar bibliotecas implementadas em C (amplamente disponíveis através do gerenciador de pacotes [pip](https://pip.pypa.io/en/stable/)) como o NumPy ou TensorFlow ao invés de implementar tudo em Python puro.

## Capacidades da Linguagem

+ Metaprogramação

  : Há três mecanismos que facilitam a metaprogramação em Python: metaclasses, decoradores e o uso de builtins redefiníveis ao invés de keywords ([via de regra](https://docs.python.org/3/reference/lexical_analysis.html#keywords)).
  Metaclasses herdam da classe _type_ e permitem adicionar regras e procedimentos arbitrários ao
  processo de declaração de uma nova classe. Com esse mecanismo, é possível verificar se uma classe foi definida de acordo com uma certa interface esperada, assegurar a obediência a uma certa convenção de nomenclatura dos métodos e atributos, executar operações sempre que uma classe é herdada por uma subclasse, etc.
  Decoradores são funções que tomam uma outra função como argumento (e quantos outros parâmetros sejam necessários) e "envelopam" essa função de alguma forma, estabelecendo alguma ação a ser executada antes e/ou depois de invocar essa função. Um exemplo é o decorador @functools.lru_cache, que estabelece um cache armazenando os últimos valores computados de qualquer função, evitando necessidade de recalcular valores previamente solicitados. Embora sejam declarados como funções quaisquer (que apenas retornam uma outra função), têm uma sintaxe própria ao serem utilizados: uma anotação na linha anterior à declaração da função, do tipo:

    ````Python
    @functools.lru_cache
    def fibonacci(x):
        if (x < 3):
            return 1
        return fibonacci(x-1) + fibonacci(x-2)
    ````

  : É notável que Python tem poucas palavras reservadas, a maioria dos nomes de funcionalidades embutidas da linguagem pode ser redefinido. Isso é muito útil para extender a linguagem. Abaixo, um exemplo onde a função embutida _len()_ (que retorna o tamanho de um objeto, ou o número de elementos se for uma coleção) é redefinida para, no caso de listas, não contar elementos _None_ (nulos) no total de elementos:
  
      ````Python
    def len(obj):
        if (type(obj) == list):
          return obj.__len__() - obj.count(None)
        
        return obj.__len__()
    ````
  
  : A redefinição de builtins como feito no exemplo só tem efeito no escopo local e não prejudica o funcionamento da linguagem em escopo global.

+ Gerenciamento de Ciclo de Vida
  : Python conta com um garbage collector que conta as referências a um objeto e libera a memória ocupada por esse objeto assim que o número de referências a ela chegue a zero. Uma referência pode ser removida com redefinição do um nome (para então guardar a referência para um outro objeto), manualmente com a keyword _del_, ou pela a destruição do seu ambiente de referência (ao finalizar a execução da função, por exemplo).
+ Segurança
  : Python é memory-safe, type-safe e thread-safe (de forma limitada). Aliasing é permitido. Não há manipulação de ponteiros, não se pode atribuir uma região de memória de um tipo para outro tipo sem realizar a conversão, e a Global Interpreter Lock impede múltiplas threads acessando a mesma região de memória ao mesmo tempo. O que pode acontecer, entretanto, é a troca do controle do processador entre threads no meio de uma operação significativa não atômica (que não é apenas uma instrução do  bytecode do Python). Para executar tais operações com segurança, é necessário temporariamente ativar uma _lock_ para impedir que o controle seja passado para outra thread.
+ Performance
  : Python é uma linguagem de alto nível com performance relativamente lenta, porém muitas bibliotecas e subrotinas da linguagem são implementadas e executadas em C ao invés de código nativo Python, portanto para certas aplicações o Python pode igualar ou superar outras linguagens normalmente mais rápidas.
  ![image](res/speed-graph.png)
+ Escalabilidade
  : Aplicações complexas e intensivas em requisitos de performance não são muito adequadas para desenvolvimento em Python. Python é muito utilizada para prototipar aplicações, com o desenvolvimento subsequente sendo reiniciado utilizando outra linguagem. Mesmo assim, Python é muito utilizada como uma linguagem de "cola", isto é, para intermediar comunicação entre módulos de um sistema de software escritos em várias linguagens diferentes.
+ Confiabilidade
  : Python é uma linguagem estável e amplamente adotada, tal como uma das mais populares. Portanto, é altamente estável e confiável, bugs são raros e são detectados e corrigidos muito rapidamente.
+ Concorrência e Threading
  : Python oferece funcionalidade de Threading, porém muito limitada em ganho de performance devido ao GIL explicado no item "custos" da seção "Características da Linguagem". O GIL, por outro lado, garante a thread-safety da linguagem, portanto se performance não é a preocupação principal pode ser uma boa escolha.  

## Produtividade do Desenvolvedor

+ **Frameworks e Contâiners**
  + [Django](https://www.djangoproject.com/)
    : Django é provavelmente o framework web mais popular em Python. É um framework "full stack". Tem grande flexibilidade e permite a construção de aplicações complexas e escaláveis.
  + [Flask](https://flask.palletsprojects.com/en/2.0.x/)
    :  Flask é um framework web também muito popular que compete com o Django, porém com uma filosofia diferente: é um microframework, isto é, não implementa funções que podem ser facilmente acessadas através de bibliotecas de terceiros.
  + [Bottle](https://bottlepy.org/docs/dev/)
    : O framework Bottle inclui roteamento, templates e um servidor HTTP embutido, dentre outras utilidades. É mais recomendado para aplicações não muito grandes que cabem num só arquivo (a ideia é que cada arquivos seja uma "garrafa"), tais como APIs não muito complexas.
  + [Web2py](http://www.web2py.com/)
    : Inspirado no Django, esse framework full stack é repleto de funcionalidades e oferece uma [IDE própria](https://wingware.com/doc/howtos/web2py). Foi originalmente criado como ferramenta educacional.
  + [FastAPI](https://fastapi.tiangolo.com/)
    : FastAPI acelera e aprimora o desenvolvimento de APIs em Python.  
  + [Kivy](https://kivy.org/)
    : Framework multiplataforma para interfaces gráficas em Python. Permite o desenvolvimento de aplicativos para dispositivos móveis Android e iOS, tal como desktop (Linux, MacOS e Windows).
  + [Jupyter](https://jupyter.org/)
    : Por alguns considerado uma IDE, de certo modo, Jupyter é uma aplicação que permite gerar documentos com fórmulas, ilustrações e exemplos de código Python (que são executados no próprio Jupyter) mostrando a sua saída.
+ **Ferramentas Disponíveis**
  + [Pycharm](https://www.jetbrains.com/pycharm/)
    : A IDE mais popular para Python construída pela [JetBrains](https://www.jetbrains.com/), criadora do IntelliJ IDEA e Android Studio.
  + [Pydev](https://www.pydev.org/)
    : Um plugin incluso na IDE [LiClipse](https://www.liclipse.com/) (um fork do Eclipse) oferecendo suporte ao desenvolvimento de aplicações Python.
  + [Pandas](https://pandas.pydata.org/)
    :  Uma biblioteca de código aberto do Python que oferece análise e manipulação de dados e estatística.
  + [Matplotlib](https://matplotlib.org/)
    :  Matplotlib é uma bliblioteca Python que disponibiliza ferramentas para visualização de dados e outras demonstrações visuais, incluindo animações e visualizações interativas.
  + [NumPy](https://numpy.org/)
    :  A biblioteca NumPy utiliza de funções e estruturas de dados implementadas em C para acelerar computações em Python, oferecendo fórmulas e computações predefinidas úteis para fins científicos e matemáticos.
  + [ScyPy](https://scipy.org/)
    : SciPy é uma biblioteca similar ao NumPy, mas mais focada no aspecto científico. SciPy usa as ferramentas disponibilizadas pelo NumPy para oferecer mais funcionalidades em alto nível e com maior nível de precisão.  
  + [TensorFlow](https://www.tensorflow.org/) e [PyTorch](https://pytorch.org/)
    :  Ambas as bibliotecas proporcionam a criação e execução de algoritmos de machine learning e redes neurais no estado da arte. São as bibliotecas mais populares para esses fins considerando todas as linguagens de programação.  
  
+ **Sintaxe, Semântica e Operações Predefinidas**
  + **Estruturas de Controle**
    + Seleção
      : Há if, elif (equivalente a else if) e else. If e else também podem ser usados numa única linha, similar ao operador ternário do C.

        ```Python
        x = 'Olá!' if y == '' else 'Olá, ' + y + '!'
        ```

      : Recentemente na versão 3.10, o Python ganhou o statement "match-case", similar a um statement "switch" mas com pattern matching (portanto mais "poderoso"). O exemplo abaixo foi retirado da [documentação do Python 3.10](https://docs.python.org/3/whatsnew/3.10.html):

        ```Python
        # point is an (x, y) tuple
        match point:
            case (0, 0):
                print("Origin")
            case (0, y):
                print(f"Y={y}")
            case (x, 0):
                print(f"X={x}")
            case (x, y):
                print(f"X={x}, Y={y}")
            case _:
                raise ValueError("Not a point")
        ```

      : Não há branching incondicional em Python.

    + Repetição
      : Existem dois tipos de loops em Python, _for_ e _while_. _While_ é controlado por condição (checagem de condição verdadeira ou falsa) e o _for_ através de iteração (necessariamente percorre um objeto iterável). Para realizar repetição por contagem, há o construtor _range_ que gera uma estrutura iterável dinâmica (em Python chamada de _generator_) que percorre a sequência numérica especificada.
    + Exceções:
      : As keywords de exceções no python são raise, try, except, else e finally.

        ```Python
        def foo(bar):
          if type(bar) == str:
            raise ValueError
        
        try:
          foo("uma string")
        except ValueError:
          print("Será executada se a exceção ValueError acontecer.")
        except OutraExcecao:
          print("Será executada se a exceção OutraExcecao acontecer.")
        else:
          print("Será executado se a exceção não acontecer.")
        finally:
          print("Sempre será executada ao fim do bloco de exceções.")
        ```

  + Legibilidade e Redigibilidade
    : Python tem no centro de sua filosofia a legibilidade. Existe um poema incluso com a linguagem (acessível através do statement "import this") chamado "Zen of Python" que representa essa filosofia. Nele há trechos que dizem: "Belo é melhor que feio", "Explícito é melhor que implícito", "Simples é preferível a complexo", "Deve haver uma maneira óbvia – e preferivelmente única – de fazer algo" e "Legibilidade importa". Essas orientações demonstram a preocupação dos desenvolvedores da linguagem e os desenvolvedores que utilizam a linguagem a aderir à maneira "pythônica" de escrever código. Além disso, consistência é igualmente valorizada. A sintaxe e semântica do Python foi construída justamente para se assemelhar a pseudocódigo escrito baseado na lingua inglesa, portanto ser fácil de ler.
    As operações/constructos predefinidas e as maneiras simples oferecidas de realizar procedimentos às vezes complexos em outras linguagens tornam Python também altamente redigível. Um exemplo são as comprehensions, que iteram sobre os elementos de uma coleção para gerar uma nova coleção de acordo com regras especificadas, tudo numa única linha de código com uma sintaxe simples:
          
      ```Python
      # cria uma nova lista elevando ao quadrado apenas os elementos
      # da lista antiga que eram inteiros
      new_list = [x ** 2 for x in old_list if isinstance(x,int)]
      ```
     : Existem críticas que podem ser feitas a às decisões de design do Python, porém. O uso de indentação para definir escopos pode resultar em pouco espaço para escrever o código em níveis de identação mais profundos, também causando perda de flexibilidade. A ausência de declaração de tipos pode dificultar a compreensão da natureza dos argumentos de uma função, por exemplo, mas isso é mitigado com as anotações de tipos opcionais.

## Ecossistema

+ Maturidade
  : Python é uma linguagem com uma visão de projeto clara e muito bem estabelecida, um sistema de governança codificado na documentação do projeto e uma enorme comunidade de usuários. Durante 30 anos de existência em contínuo desenvolvimento, documentação, pacotes, bibliotecas e frameworks de alta qualidade e confiabilidade foram sendo acumulados. Python é, portanto, uma das linguagens de programação mais maduras dentre as mais utilizadas na atualidade.
+ Comunidade
  : Devido ao seu uso difundido, a comunidade de usuários e desenvolvedores da linguagem é vasta e seus membros são notavelmente tolerantes, respeitosos, acolhedores e muito amigável com iniciantes, sendo Python uma escolha comum na atualidade de primeira linguagem de programação também devido à sua forma de escrever que se aproxima em muitos aspectos da língua inglesa. Dezenas de conferências sobre a linguagem são organizadas independentemente todos os anos por todos os continentes, tendo uma conferência oficial reaizada nos Estados Unidos, a PyCon.
+ Governança
  : Atualmente o projeto Python (que é de código aberto e de licença GNU General Public License) é governado pela Python Software Foundation, uma organização sem fins lucrativos. Um conselho de cinco membros é eleito pela equipe oficial de desenvolvedores do núcleo da linguagem (Python core team) a cada lançamento de uma nova grande versão (aproximadamente uma vez ao ano). Não mais que dois membros do conselho podem ser empregados de uma mesma empresa para evitar conflitos de interesse.
  O _Python core team_ é uma lista de desenvolvedores com um histórico notável de contribuições (não somente em código) para o projeto da linguagem, cujo ingresso na lista foi votado por dois terços dos membros ativos da lista e não foi vetado pelo conselho. Já o conselho tem, através de votação por todos seus membros ,poderes de decisão e veto sobre as propostas de melhoramento da linguagem e gerenciar os canais e plataformas associadas à Python Software Foundation. O estatuto de governança da linguagem recomenda que o conselho "use seus poderes o mínimo possível, buscando procurar consenso e estabelecer regras ao invés de apenas decidir as situações caso a caso".
  Mudanças na linguagem são propostas através de PEPs (Python Enhancement Proposals), que são aceitas ou não pelo conselhos e então aplicadas na implementação de referência (CPython).
  Em geral, é fácil concluir que o Python tem um dos sistemas de governança mais robustos entre as linguagens de programação FOSS utilizadas na atualidade, o que sugere estabilidade e sucesso de longo prazo ao projeto.
+ Fragmentação
  : Embora haja múltiplas implementações da linguagem, não há em geral "forks" causados por discordâncias nas decisões de governância. Embora cada implementação alternativa tenha seu papel e usos mais apropriados que a implementação de referência, todas procuram seguir implementando as novas funcionalidades trazidas pela implementação principal exceto quando imprático ou impossível, mesmo se um pouco atrasadas na entrega. As comunidades de desenvolvedores das principais implementações alternativas têm um bom relacionamento com a comunidade que participa do desenvolvimento da principal, participando das decisões e muitas vezes contribuindo para ambos os projetos.

---

## Referências

1. https://www.gartner.com/en/documents/2071615/programming-languages
framework for assessing and characterizing programming languages and assessing their applicability to specific projects
2. https://docs.python.org/3/howto/functional.html
Functional Programming HOWTO – Python 3 Manual
3. https://github.com/yuce/pyswip
PySwip
4. https://docs.python.org/3/faq/general.html#what-is-python
General Python FAQ — Python 3.10.0 documentation – What is Python?
5. https://www.python.org/community/workshops/
Conferences and Workshops | Python.org
6. https://www.python.org/dev/peps/pep-0013/
PEP 13 -- Python Language Governance | Python.org
7. https://stackoverflow.com/a/36826546/11541975
oop – "public" or "private" attribute in Python ? What is the best way? – Stack Overflow
8. https://docs.python.org/3/library/stdtypes.html
Built-in Types – Python 3 Manual
9. https://docs.python.org/3/tutorial/classes.html
Classes – Python 3 Manual
10. https://www.python.org/download/alternatives/
Alternative Python Implementations | Python.org
11. https://medium.com/fintechexplained/advanced-python-metaprogramming-980da1be0c7d
Advanced Python: Metaprogramming – Explaining what, why and how Metaprogramming works in Python – Farhad Malik – Medium
12. https://towardsdatascience.com/memory-management-and-garbage-collection-in-python-c1cb51d1612c#:~:text=Garbage%20collection%20is%20implemented%20in,cleans%20up%20the%20object%20immediately.
Memory Management And Garbage Collection In Python | by Seyma Tas
13. https://realpython.com/python-gil/
What Is the Python Global Interpreter Lock (GIL)? – Real Python
14. https://opensource.com/article/17/4/grok-gil
Grok the GIL: How to write fast and thread-safe Python
15. https://github.com/niklas-heer/speed-comparison
niklas-heer/speed-comparison: A repo which compares the speed of different programming languages.
16. https://docs.python.org/3/tutorial/controlflow.html
More Control Flow Tools — Python 3.10.0 documentation
17. https://docs.python.org/3/tutorial/errors.html
Errors and Exceptions — Python 3.10.0 documentation
18. https://www.python.org/dev/peps/pep-0020/
PEP 20 -- The Zen of Python | Python.org


