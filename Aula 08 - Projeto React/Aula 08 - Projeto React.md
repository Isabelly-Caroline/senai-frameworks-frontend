# Aula 08 --- Projeto React

## 1. Revisão de JavaScript

A aula começa revisando conceitos de JavaScript que serão utilizados no
desenvolvimento com React.

### Inserção do JavaScript no HTML

O JavaScript pode ser incluído: - Diretamente no HTML, utilizando a tag
`<script>`. - Em um arquivo externo, conectado pelo atributo `src` da
tag `<script>`. Essa opção facilita a organização e manutenção em
projetos maiores. - Em atributos de eventos, como `onclick` e `onblur`,
para responder às ações do usuário.

JavaScript permite criar interatividade, manipular o DOM, desenvolver
animações, aplicar efeitos e consumir dados de servidores.

### Variáveis

As variáveis armazenam informações. Em JavaScript, os nomes são **case
sensitive**, ou seja, `nome`, `Nome` e `NOME` são identificadores
diferentes.

-   `var`: possui escopo de função; quando declarada fora de uma função,
    tem escopo global.
-   `let`: possui escopo de bloco, ficando disponível dentro do bloco
    `{ }` em que foi declarada.
-   `const`: aparece nos exemplos da aula para declarar valores que não
    serão reatribuídos.

### Tipos de dados

  Tipo        Exemplo ou significado
  ----------- ---------------------------------
  String      `"Olá"` --- texto.
  Number      `10`, `3.14` --- números.
  Boolean     `true` ou `false`.
  Undefined   Valor ainda não definido.
  Null        Ausência intencional de valor.
  Object      `{ nome: "Ana", idade: 20 }`.
  Array       `[10, 20, 30]`.
  Symbol      Identificador único.
  BigInt      Números inteiros muito grandes.

O operador `typeof` permite verificar o tipo de um valor.

### Operadores

**Aritméticos:** `+` soma, `-` subtrai, `*` multiplica, `/` divide, `%`
retorna o resto, `**` realiza exponenciação, `++` incrementa e `--`
decrementa.

**Comparação:** - `==`: compara valores, permitindo conversão de tipo. -
`===`: compara valor e tipo. - `!=` e `!==`: verificam diferenças. -
`>`, `<` e `>=`: fazem comparações numéricas.

**Lógicos:** - `&&`: E --- todas as condições devem ser verdadeiras. -
`||`: OU --- pelo menos uma condição deve ser verdadeira. - `!`: NÃO ---
inverte o resultado lógico.

**Atribuição:** `=`, `+=`, `-=`, `*=`, `/=` e `%=` atribuem valores ou
executam uma operação e atribuem o resultado.

### Condicionais

As condicionais permitem executar blocos diferentes conforme uma
condição:

-   `if`: executa um bloco se a condição for verdadeira.
-   `else if`: testa outra condição.
-   `else`: executa quando as condições anteriores não são atendidas.
-   Operador ternário: forma compacta de escolher entre dois resultados:
    `condicao ? valorSeVerdadeiro : valorSeFalso`.

### Estruturas de repetição

-   `for`: utilizado quando a quantidade de repetições é conhecida ou
    controlada.
-   `while`: repete enquanto uma condição for verdadeira.
-   `do...while`: executa pelo menos uma vez e depois verifica a
    condição.
-   `break`: interrompe a repetição.
-   `continue`: encerra a iteração atual e passa para a próxima.

### Funções

Funções são blocos de código que executam tarefas específicas. Podem
receber parâmetros e retornar resultados com `return`. A aula apresenta
duas formas:

``` javascript
function somar(a, b) {
  return a + b;
}

const multiplicar = (a, b) => a * b;
```

Também são citadas funções e recursos como `console.log()`, `alert()`,
`prompt()`, `confirm()`, `getElementById()`, `querySelector()`,
`addEventListener()`, `innerHTML` e `textContent`.

### Arrays

Arrays armazenam vários valores em uma única variável, organizados em
sequência e acessados por índices.

Métodos trabalhados: - `length`: informa a quantidade de elementos. -
`forEach()`: executa uma função para cada item. - `filter()`: seleciona
itens que atendem a uma condição.

### Objetos

Objetos agrupam informações relacionadas em propriedades e
comportamentos em métodos.

-   **Propriedades:** armazenam os dados.
-   **Métodos:** funções associadas ao objeto.
-   **Acesso:** permite consultar ou alterar propriedades.
-   **`this`:** referencia o próprio objeto dentro de seus métodos.

## 2. DOM (Document Object Model)

O DOM é a representação estruturada, em forma de árvore, da página HTML.
O JavaScript pode localizar elementos e modificar textos, valores,
classes e outros aspectos da página.

Métodos e propriedades apresentados:

  -----------------------------------------------------------------------
  Recurso                             Função
  ----------------------------------- -----------------------------------
  `getElementById()`                  Seleciona um elemento pelo ID.

  `querySelector()`                   Seleciona o primeiro elemento que
                                      corresponde a um seletor CSS.

  `querySelectorAll()`                Seleciona todos os elementos
                                      correspondentes.

  `textContent`                       Altera ou consulta o texto de um
                                      elemento.

  `value`                             Acessa ou altera o valor de um
                                      campo.

  `classList`                         Adiciona, remove ou alterna classes
                                      CSS.

  `createElement()`                   Cria um elemento HTML.

  `appendChild()`                     Adiciona um elemento ao documento.

  `addEventListener()`                Registra eventos, como cliques.
  -----------------------------------------------------------------------

## 3. JSX

JSX é uma extensão de sintaxe do JavaScript que permite escrever
estruturas semelhantes ao HTML dentro do código JavaScript. É utilizado
para descrever a interface dos componentes React.

Exemplo:

``` jsx
const titulo = <h1>Olá, React!</h1>;
```

É possível inserir expressões JavaScript entre chaves `{ }`:

``` jsx
const nome = "João";
const saudacao = <h1>Olá, {nome}!</h1>;
```

### Diferenças entre JSX e HTML

-   Utiliza `className` no lugar de `class`.
-   Utiliza `htmlFor` no lugar de `for`.
-   Elementos sem conteúdo devem ser fechados, como `<img />`.
-   Componentes devem retornar um elemento raiz ou utilizar Fragment.
-   Expressões JavaScript são inseridas entre `{ }`.

O JSX facilita a leitura e a organização da interface e é transformado
em JavaScript antes da execução.

## 4. Componentes

Componentes são unidades independentes e reutilizáveis da interface. Em
React, normalmente são funções JavaScript que retornam elementos React,
frequentemente escritos em JSX.

Exemplo:

``` jsx
function Cabecalho() {
  return <h1>Catálogo React</h1>;
}

function App() {
  return (
    <main>
      <Cabecalho />
      <p>Explore os principais conceitos.</p>
    </main>
  );
}
```

Para criar e utilizar um componente: 1. Crie uma função com nome
iniciado em letra maiúscula. 2. Utilize `return` para definir o que será
exibido. 3. Insira o componente com `<NomeDoComponente />`. 4. Combine
componentes para montar a página.

Dividir uma interface em componentes menores facilita a leitura, a
manutenção e a reutilização. A aula também apresenta a **árvore de
componentes**, estrutura hierárquica em que um componente principal
contém componentes filhos, que podem conter outros componentes.

## 5. Props

Props (properties) são dados recebidos por um componente. Em uma
estrutura comum, o componente pai envia informações para o componente
filho.

Exemplo:

``` jsx
function Saudacao({ nome }) {
  return <h1>Olá, {nome}!</h1>;
}

<Saudacao nome="João" />
<Saudacao nome="Maria" />
```

O mesmo componente pode apresentar conteúdos diferentes conforme as
props recebidas.

Tipos de valores que podem ser passados por props: - Strings. -
Números. - Booleanos. - Arrays e objetos. - Funções. - Elementos React.

As props permitem personalizar componentes, evitar duplicação de
estruturas e deixar explícitos os dados utilizados por cada componente.

## 6. DOM, Virtual DOM e atualização da interface

-   **DOM:** representa a estrutura do documento HTML no navegador e
    pode ser consultado ou modificado por JavaScript.
-   **Virtual DOM:** termo utilizado para descrever uma representação da
    interface em memória. O React utiliza descrições de elementos para
    coordenar a atualização da interface.

O fluxo conceitual de atualização apresentado é:

1.  **Mudança:** ocorre uma interação ou atualização de dados.
2.  **Renderização:** o React executa novamente os componentes
    relevantes para calcular a nova descrição da interface.
3.  **Reconciliação:** o React compara a nova descrição com a anterior.
4.  **Atualização:** as alterações necessárias são aplicadas ao ambiente
    de renderização, como o DOM do navegador.

Nem toda nova renderização exige alterações no DOM. A reconciliação
considera a estrutura e a identidade dos elementos para determinar o que
precisa ser atualizado.

## 7. Listas e Keys

Aplicações frequentemente exibem listas de alunos, produtos, tarefas e
conceitos. Esses dados costumam ser armazenados em arrays.

O método `map()` percorre os itens de um array e gera um novo array com
os resultados da função. No React, ele pode transformar cada item em um
elemento JSX.

``` jsx
const alunos = [
  { id: 101, nome: "Ana" },
  { id: 102, nome: "Bruno" }
];

{alunos.map((aluno) => (
  <li key={aluno.id}>{aluno.nome}</li>
))}
```

A propriedade `key` identifica elementos entre irmãos em uma lista. Ela
ajuda o React a reconhecer itens mantidos, adicionados, removidos ou
reordenados. O ideal é utilizar um identificador associado a cada item.

A aula também relaciona: - `filter()`: seleciona os itens que atendem a
uma condição. - `map()`: transforma os itens selecionados em elementos
JSX.

Quando uma lista está em estado, a orientação apresentada é produzir
novos arrays em vez de modificar diretamente o array existente.

## 8. Renderização condicional

Renderização condicional permite mostrar, ocultar ou alterar partes da
interface conforme uma condição. Pode depender de props, estado ou dados
recebidos pela aplicação.

Formas apresentadas:

-   **`if` e `return`:** úteis quando cada condição exige uma interface
    diferente.
-   **Operador ternário:** alterna entre dois conteúdos dentro do JSX.
-   **Condições com dados:** podem exibir resultados, mensagens para
    listas vazias, carregamento ou erro.

Exemplo com ternário:

``` jsx
function ResultadoBusca({ carregando }) {
  return (
    <div>
      {carregando
        ? <p>Buscando...</p>
        : <p>Busca finalizada.</p>}
    </div>
  );
}
```

## 9. Atividade proposta

Desenvolver uma aplicação React utilizando os conceitos estudados: JSX,
componentes, props, Virtual DOM, listas e renderização condicional. A
entrega deve incluir um repositório público no GitHub e um README com a
descrição, as funcionalidades e os conceitos utilizados.

## Para memorizar

-   **JSX:** permite descrever interfaces com sintaxe semelhante ao HTML
    dentro do JavaScript.
-   **Componente:** parte reutilizável da interface.
-   **Props:** dados enviados de um componente pai para um filho.
-   **DOM:** representação estruturada do HTML no navegador.
-   **Virtual DOM:** representação utilizada pelo React para coordenar
    atualizações.
-   **`map()`:** transforma itens de um array em elementos.
-   **`key`:** identifica cada item de uma lista.
-   **Renderização condicional:** mostra conteúdos diferentes conforme
    uma condição.
