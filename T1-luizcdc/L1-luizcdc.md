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

Python é uma linguagem de programação multiparadigma de alto nível. Foi publicada em 1991 pelo seu criador Guido van Rossum. Seu nome é inspirado no programa de televisão britânico _Monty Python's Flying Circus_. A linguagem está atualmente na versão 3.10 e seu desenvolvimento está ativo, sendo atualizada constantemente com novos recursos e otimizações. É atualmente uma das linguagens de programação mais populares no mundo, figurando em alguns rankings em primeiro lugar. Atualmente é muito usada para projetos de inteligência artificial, visualização e ciência de dados, scripting para automação de tarefas e desenvolvimento web back-end.

_Comentar sobre perspectivas / papéis._


![image](./res/python-tree.png)


## Características da Linguagem

+ Paradigma
  : Python é uma linguagem multiparadigma que suporta POO, funcional, procedural e imperativa. Seu suporte a programação funcional não é ideal, porém, pois alguns constructos importantes para programação funcional não são simples de se fazer nela, tal qual estruturas de dados imutáveis por exemplo, e não há [(nem provavelmente será adicionada)](http://neopythonic.blogspot.com/2009/04/final-words-on-tail-calls.html) optimização de chamada de cauda. Embora não suporte nativamente a programação lógica, esse paradigma pode ser explorado através de módulos/extensões como o PySwip, interfaceando entre Python e SWI-Prolog.
+ Propósito
  : Guido van Rossum, o criador da linguagem, começou a construí-la no seu tempo livre como um projeto para ser utilizado no seu trabalho, que envolvia administração de sistemas no sistema operacional [Amoeba](https://en.wikipedia.org/wiki/Amoeba_(operating_system)). Guido buscava criar uma linguagem para escrever scripts com maior capacidade de interação com as chamadas de sistema do que bsh, porém muito mais redigível que C. Para isso, se inspirou majoritariamente linguagens ABC e Modula. Com a continuação do seu desenvolvimento, Python
+ Sistema de Tipagem
+ Ambiente de Execução
  : A linguagem é interpretada, e há diversos interpretadores implementados diferentemente para executá-la. Cada um desses oferece um ambiente de execução diferente com acesso a ferramentas distintas, mas o interpretador original da linguagem, CPython, oferece uma API para programas em C que implementa toda a comunicação necessária entre o Python e o C.
+ Implementação
  : A implementação original é chamada CPython, escrita em C. O CPython compila o código em Python para seu bytecode próprio e o interpreta. Outras implementações famosas são PyPy, que implementa um compilador para código de máquina nativo JIT que oferece um desempenho muito maior sem sacrificar o dinamismo da linguagem, Jython que compila para bytecode da JVM - Java Virtual Machine, permitindo interfaceamento e inserção dentro de programas Java e vice-versa e Cython, que é uma versão compilada do Python com ferramentas adicionais.
+ Custos
 _Custos aqui ..._

## Capacidades da Linguagem

+ Metaprogramação
+ Gerenciamento de Ciclo de Vida
+ Segurança
+ Performance
+ Escalabilidade
+ Confiabilidade
+ Concorrência e Threading
+ Custos
  _Custos aqui ..._

## Produtividade do Desenvolvedor

+ Frameworks e Contâiners
+ Ferramentas Disponíveis
+ Sintaxe, Semântica e Operações Predefinidas
  + Legibilidade
  + Redigibilidade
+ Custos

## Ecossistema

+ Maturidade
+ Comunidade
+ Governança
+ Fragmentação

---

## Informações Adicionais

## Referências

1. https://www.gartner.com/en/documents/2071615/programming-languages
framework for assessing and characterizing programming languages and assessing their applicability to specific projects
2. https://docs.python.org/3/howto/functional.html
Functional Programming HOWTO - Python 3 Manual
3. https://github.com/yuce/pyswip
PySwip
4. https://docs.python.org/3/faq/general.html#what-is-python
   General Python FAQ — Python 3.10.0 documentation - What is Python?