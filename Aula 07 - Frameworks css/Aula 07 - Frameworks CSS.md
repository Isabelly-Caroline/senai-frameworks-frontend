# Aula 07 --- Frameworks CSS

## 1. O que é CSS?

CSS (Cascading Style Sheets) é a linguagem utilizada para definir a
apresentação visual de páginas HTML. Com ela, é possível configurar
cores, fontes, margens, alinhamentos, larguras, alturas e posicionamento
dos elementos, criando páginas organizadas e responsivas.

A estrutura básica de uma regra CSS é:

``` css
seletor {
  propriedade: valor;
}
```

-   **Seletor:** indica o elemento HTML que receberá o estilo.
-   **Propriedade:** define o que será alterado, como `color` ou
    `background-color`.
-   **Valor:** determina a configuração aplicada, como `red` ou
    `#FF0000`.

## 2. Formas de aplicar CSS

Existem três maneiras principais de inserir CSS em uma página:

### CSS inline

É aplicado diretamente no elemento HTML pelo atributo `style`. É útil
para testes ou ajustes pontuais.

``` html
<p style="color: red; font-size: 20px;">Texto</p>
```

### CSS interno

É escrito dentro da tag `<style>`, geralmente no cabeçalho do HTML. É
indicado quando os estilos serão utilizados em uma única página.

``` html
<style>
  p {
    color: blue;
    font-size: 18px;
  }
</style>
```

### CSS externo

Fica em um arquivo separado com extensão `.css`, conectado ao HTML pela
tag `<link>`. É a forma recomendada para projetos maiores, pois facilita
a organização, manutenção e reutilização dos estilos.

``` html
<link rel="stylesheet" href="estilos.css">
```

## 3. Principais propriedades CSS

  -----------------------------------------------------------------------
  Propriedade                         Função
  ----------------------------------- -----------------------------------
  `color`                             Define a cor do texto.

  `background-color`                  Define a cor de fundo.

  `font-family`                       Define a família da fonte.

  `font-size`                         Controla o tamanho do texto.

  `margin`                            Define o espaço externo ao
                                      elemento.

  `padding`                           Define o espaço interno entre o
                                      conteúdo e a borda.

  `border`                            Configura a borda do elemento.

  `width` e `height`                  Definem largura e altura.

  `display`                           Define como o elemento será
                                      exibido, por exemplo `block`,
                                      `inline` ou `flex`.

  `position`                          Define o tipo de posicionamento do
                                      elemento.

  `top`, `right`, `bottom`, `left`    Ajustam a posição de elementos
                                      posicionados.

  `text-align`                        Define o alinhamento horizontal do
                                      texto.
  -----------------------------------------------------------------------

## 4. Classes e IDs

-   **Classe (`.nome-da-classe`):** pode ser aplicada a vários elementos
    que compartilham o mesmo estilo.
-   **ID (`#nome-do-id`):** identifica um elemento específico da página.
    Também pode ser utilizado em âncoras e na manipulação por
    JavaScript.

Exemplos:

``` css
.botao-primario {
  background: blue;
  color: white;
  padding: 10px;
}

#cabecalho-principal {
  height: 80px;
  background: #333;
}
```

## 5. Box Model

O Box Model (modelo de caixas) descreve como cada elemento HTML é
representado e dimensionado na página. Ele é formado por quatro partes:

1.  **Content:** área onde ficam o texto, imagens ou outros conteúdos.
2.  **Padding:** espaço interno entre o conteúdo e a borda.
3.  **Border:** borda que envolve o conteúdo e o padding.
4.  **Margin:** espaço externo entre a borda e os demais elementos.

O Box Model ajuda a controlar dimensões, organizar espaçamentos, evitar
sobreposições e criar layouts previsíveis.

## 6. Flexbox

Flexbox (Flexible Box Layout) é um modelo de layout unidimensional
utilizado para organizar elementos em linhas ou colunas e distribuir o
espaço entre eles.

Principais propriedades apresentadas:

-   `flex-direction`: define a direção dos itens, como `row` ou
    `column`.
-   `justify-content`: distribui os itens no eixo principal. Exemplos:
    `flex-start`, `center`, `space-between` e `space-around`.
-   `align-items`: alinha os itens no eixo transversal. Exemplos:
    `flex-start`, `center` e `flex-end`.
-   `flex-wrap`: permite que os itens quebrem para outra linha.
-   `gap`: define o espaço entre os itens.

## 7. Layouts responsivos

Um layout responsivo adapta o conteúdo a diferentes tamanhos de tela,
como celulares, tablets e desktops. Isso melhora a usabilidade e a
experiência do usuário, sem exigir uma versão totalmente separada do
site para cada dispositivo.

## 8. O que é um framework CSS?

Um framework CSS reúne recursos, padrões, classes e componentes que
facilitam a criação e a padronização de interfaces web.

Seus recursos podem incluir:

-   **Layout:** Grid, Flexbox e responsividade.
-   **Estilos:** cores, espaçamentos e tipografia.
-   **Componentes:** botões, cards e barras de navegação.

A proposta é reduzir o trabalho repetitivo de estilizar manualmente cada
parte da interface.

## 9. Tailwind CSS

Tailwind CSS é um framework baseado principalmente no conceito
**Utility-First**. Em vez de depender apenas de componentes prontos, ele
oferece pequenas classes utilitárias, cada uma responsável por uma regra
ou característica de estilo. Essas classes são combinadas diretamente no
atributo `class` do HTML.

Exemplos de classes citadas na aula:

  Classe          Função
  --------------- ------------------------------------
  `p-6`           Define padding.
  `text-xl`       Define o tamanho do texto.
  `font-bold`     Aplica peso maior à fonte.
  `bg-blue-600`   Define a cor de fundo.
  `rounded-lg`    Arredonda as bordas.
  `text-white`    Define a cor do texto como branca.
  `px-6`          Define padding horizontal.
  `py-3`          Define padding vertical.

Exemplo:

``` html
<button class="bg-blue-600 text-white px-6 py-3 rounded-lg">
  Enviar
</button>
```

**Ideia principal:** uma utility tem uma responsabilidade específica;
várias utilities combinadas formam o estilo de um componente.

### Objetivos do Tailwind CSS

-   Reduzir o tempo de desenvolvimento.
-   Aumentar a flexibilidade na criação das interfaces.
-   Facilitar a personalização de cores, espaçamentos e tipografia.
-   Promover reutilização e consistência visual.
-   Simplificar o desenvolvimento responsivo com uma abordagem Mobile
    First.

### Formas de utilização e ferramentas

-   **Play CDN:** opção indicada nos slides para testes rápidos,
    adicionada no `<head>` do HTML.
-   **Tailwind CLI:** instalação e integração do Tailwind ao processo de
    desenvolvimento e transformação do CSS.
-   **Integração com frameworks:** Next.js, Laravel, Angular e Ruby on
    Rails possuem procedimentos próprios de configuração.
-   **Tailwind IntelliSense:** extensão para editores de código que
    oferece sugestões de classes, autocompletar e visualização de
    estilos.

## 10. Atividades propostas na aula

### Atividade 01 --- CSS e Flexbox

Criar um projeto com `index.html` e `style.css`, aplicando CSS externo.
A atividade solicita adicionar 20 elementos, trabalhar com Content,
Padding, Border e Margin e utilizar propriedades de Flexbox para
organizar os elementos de forma responsiva.

### Atividade 02 --- Tailwind CSS

Criar um projeto utilizando pelo menos 30 classes diferentes do
Tailwind, abrangendo cores, tipografia, espaçamentos, dimensões, bordas,
posicionamento, Flexbox, Grid e responsividade. A entrega deve conter um
repositório, documentação em Markdown, prints do código e da aplicação,
lista das classes utilizadas com suas funções e link do projeto.

## Para memorizar

-   **CSS:** controla a aparência dos elementos HTML.
-   **Margin:** espaço externo.
-   **Padding:** espaço interno.
-   **Border:** borda do elemento.
-   **Flexbox:** organiza elementos em linhas ou colunas.
-   **Responsividade:** adapta o layout a diferentes telas.
-   **Framework CSS:** reúne recursos para agilizar e padronizar a
    criação de interfaces.
-   **Tailwind:** utiliza classes utilitárias combináveis diretamente no
    HTML.

> Observação: o sumário inicial do PDF menciona API, HTTP, JSON e
> Express, mas o conteúdo desenvolvido nos slides desta aula aborda CSS,
> Box Model, Flexbox, responsividade e Tailwind CSS.
