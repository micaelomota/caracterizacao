# Rust

O [Rust](https://www.rust-lang.org/) é uma linguagem de programação multi-paradigma, focada em a performance, o seu desempenho é considerado um dos melhores entre as outras linguagens de programação. Iniciada como projeto interno da Mozilla para resolver problemas vindo do C e C++ hoje é utilizada para diversas aplicações seja em partes do kernel do sistema operacional Linux ou para servidores web, qualquer coisa que precise de velocidade e confiabilidade.

Com o conceito inovador de ownership evita a poluição de memória, ou seja, o uso de memória que não é necessário, poís como uma variável só pode ter um dono ela é desalocada quando não é utilizada. Além de evitar bugs de acesso em memoria ilegal com ponteiros, ou seja, evita erros de segurança.

Tudo isso checado pelo seu compilador que tem a característica de ser bem conservador e exaustivo logo é bem comum erros de compilação assim evitando erros no Runtime.

Caso o programador queira ele pode usar a flag unsafe para relaxar o compilador, mas isso pode levar ao risco de bugs no Runtime.

O Rust tem sido votada a linguagem mais amada na pesquisa do stack overflow desde 2016 mesmo sendo não tão mainstream ainda.
