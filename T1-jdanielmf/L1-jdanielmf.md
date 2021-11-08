# Javascript

  * [Apresentação e histórico](#apresenta--o-e-hist-rico)
  * [Características da Linguagem](#caracter-sticas-da-linguagem)
  * [Capacidades da Linguagem](#capacidades-da-linguagem)
  * [Produtividade do Desenvolvedor](#produtividade-do-desenvolvedor)
  * [Ecossistema](#ecossistema)
  * [Informações Adicionais](#informa--es-adicionais)
  * [Referências](#refer-ncias)

## Apresentação e histórico
O JavaScript foi primeiramente desenvolvido por Brendan Eich quando trabalhou na Netscape sob o nome de Moch, mas tarde teve seu nome alterado para LiveScript e por fim JavaScript. LiveScript foi o nome oficial da linguagem quando foi lançada pela primeira vez na versão beta do navegador Netscape 2.0 em setembro de 1995, mas teve seu nome mudado em um anúncio conjunto com a Sun Microsystems em dezembro de 1995 quando foi implementado no navegador Netscape versão 2.0B3.
A mudança de nome de LiveScript para JavaScript coincidiu com a época em que a Netscape adicionou suporte à tecnologia Java em seu navegador (Applets). A escolha final do nome causou confusão dando a impressão de que a linguagem foi baseada em java, sendo que tal escolha foi caracterizada por muitos como apenas uma estratégia de marketing da Netscape para aproveitar a fama do recém-lançado Java.

## Características da Linguagem
JavaScript é uma linguagem de programação interpretada. Foi originalmente implementada como parte dos navegadores web para que scripts pudessem ser executados do lado do cliente e interagissem com o usuário sem a necessidade deste script passar pelo servidor, controlando o navegador, realizando comunicação assíncrona e alterando o conteúdo do documento exibido.
É atualmente a principal linguagem para programação client-side em navegadores web. Começa também a ser bastante utilizada do lado do servidor através de ambientes como o node.js. Foi concebida para ser uma linguagem com orientação a objetos baseada em protótipos, tipagem fraca e dinâmica e funções de primeira classe. Possui suporte à programação funcional e apresenta recursos como fechamentos e funções de alta ordem comumente indisponíveis em linguagens populares como Java e C++. É a linguagem de programação mais utilizada do mundo. 

A última versão ECMAScript define seguintes tipos de dados:

+ primitives 
    * Boolean
    * Null
    * Undefined
    * Number
    * BigInt
    * String
    * Symbol
+ Object

##### Sintaxe da linguagem JavaScript
JavaScript foi criada com base na ECMAScript e sua sintaxe é bastante semelhante a linguagens de alto nível muito utilizadas como C e Java, como veremos a seguir.

##### Usando variáveis no JavaScript
Essa linguagem possui tipagem dinâmica, ou seja, não é necessário definir o tipo das variáveis ao declará-las, para isso basta usar a palavra reservada var. Na Listagem 3 temos alguns exemplos de utilização de variáveis.

```javascript
var nome;
nome = “Fulano de Tal”;
var idade = 30;
idade = 30 + 20 - 10*5;
```
Listagem 3. Utilizando variáveis


##### Trabalhando com funções
JavaScript fornece também suporte a funções, aliado às facilidades da tipagem dinâmica, o que torna a definição de métodos simples e prática. Para criar funções, utilizamos a palavra reservada function.

As funções podem receber parâmetros e retornar valores, mas o tipo de retorno e o tipo dos parâmetros não precisa ser previamente definido. Nas Listagens 4 e 5 temos exemplos de funções com e sem parâmetros e retorno.
```javascript
function exibirMensagem(){  
    alert(“Olá, seja bem vindo(a)!”);
}
```
Listagem 4. Função em JavaScript sem parâmetro e sem retorno

Observação: a função alert será apresentada posteriormente, mas serve para exibir uma mensagem popup para o usuário.
```javascript
function somar(A, B){
  return A + B;
}
```

Listagem 5. Função em JavaScript com parâmetro e com retorno

Para definir o valor de retorno da função, deve-se utilizar a palavra reservada return seguida do valor ou expressão do resultado.

##### Estruturas de controle de fluxo
Assim como a maioria das linguagens de alto nível, JavaScript possui estruturas condicionais e de repetição para controle de fluxo. Na Listagem 6 temos a sintaxe e um exemplo de uso de tais estruturas.

```javascript
if(condição 1){
  //ação se condição 1 verdadeira
}
else if (condição 2){
  //ação se condição 2 verdadeira
}else{
  //ação se nenhuma das condições for verdadeira
}
```

##### Escopo
Em JavaScript, o escopo é o conjunto de variáveis, objetos e funções que você tem acesso.
JavaScript tem escopo função: O escopo muda funções dentro.
##### Variáveis Locais
Variáveis declaradas dentro de uma função JavaScript, tornar-se local para a função.
As variáveis locais têm escopo local: Eles só podem ser acessados dentro da função.

Exemplo
```javascript
// code here can not use carName
function myFunction() {
    var carName = "Volvo";
    // code here can use carName
}
```
Uma vez que as variáveis ​​locais são reconhecidos apenas dentro de suas funções, variáveis ​​com o mesmo nome pode ser usado em diferentes funções.

As variáveis ​​locais são criadas quando uma função é iniciado e excluído quando a função é concluída.

##### Variáveis Globais
Uma variável declarada fora de uma função, torna-se global.
Uma variável global tem escopo global: Todos os scripts e funções em uma página web pode acessá-lo.
Exemplo
```javascript
var carName = " Volvo";
// code here can use carName
function myFunction() {
    // code here can use carName
}
```
###### Automaticamente Global
Se você atribuir um valor a uma variável que não tenha sido declarado, ele se tornará automaticamente uma variávelglobal.
Este exemplo de código irá declarar carName como uma variável global, mesmo se for executado dentro de uma função.

Exemplo
```javascript
// code here can use carName
function myFunction() {
    carName = "Volvo";
    // code here can use carName
} 
``` 
Não crie variáveis ​​globais, a menos que você pretende.
Em "Modo estrito" automaticamente variáveis ​​globais irá falhar.

##### Tempo de vida
O tempo de vida de uma variável JavaScript começa quando ela é declarada.
As variáveis locais são excluídos quando a função é concluída.
As variáveis globais são excluídos quando você fechar a página.

## Capacidades da Linguagem
  + Metaprogramação  + Gerenciamento de Ciclo de Vida
  + Segurança 
  + Performance
  + Escalabilidade
  + Confiabilidade
  + Concorrência e Threading 
  + Custos

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
2. https://developer.mozilla.org/pt-BR/docs/Web/JavaScript/Data_structures
Estrutura de dados do Javascript
3. https://www.devmedia.com.br/javascript-tutorial/37257
JavaScript Tutorial
4. https://www.w3bai.com/pt/js/js_scope.html
JavaScript Escopo


