# Aula 09 --- Projeto React 02

## 1. State e useState

**State** é uma informação que o componente React guarda, como um
contador ou uma mensagem. Ele permite atualizar a interface conforme as
ações do usuário. Quando o estado muda, o React renderiza novamente o
componente para atualizar a tela.

### Por que uma variável comum não basta?

Uma variável comum pode guardar um valor, mas alterá-la não faz o React
renderizar novamente o componente. Além disso, variáveis locais são
recriadas quando o componente é executado novamente.

O state permite manter valores entre renderizações e solicitar a
atualização da interface quando eles mudam.

### O que são Hooks?

Hooks são funções especiais que permitem utilizar recursos do React em
componentes funcionais. Seus nomes começam com `use`, como `useState` e
`useEffect`. Devem ser utilizados no início do componente ou de outros
Hooks, seguindo as regras do React.

### Hook useState

`useState` guarda informações que podem mudar durante o uso do
componente. Ele retorna dois elementos: 1. O valor atual do estado. 2. A
função utilizada para atualizá-lo.

Recebe um valor inicial e deve ser importado do React.

``` jsx
import { useState } from "react";

function Contador() {
  const [contador, setContador] = useState(0);

  return (
    <section>
      <p>Valor: {contador}</p>
      <button onClick={() => setContador(contador + 1)}>
        Incrementar
      </button>
    </section>
  );
}
```

Nesse exemplo, o estado começa em zero. Ao clicar no botão,
`setContador` atualiza o valor e o React apresenta o novo número na
interface.

## 2. Formulários

Formulários permitem que o usuário informe dados para a aplicação. Em
React, utilizam campos HTML, eventos e estado. Podem ser usados em
cadastros, buscas, login e preferências.

O envio pode validar os dados e apresentar uma mensagem de confirmação.

### Campos controlados

São campos cujo valor é controlado pelo estado do React: - A propriedade
`value` define o valor exibido. - O evento `onChange` detecta a
digitação e atualiza o estado. - `e.target.value` obtém o texto
digitado.

Exemplo:

``` jsx
import { useState } from "react";

function CampoNome() {
  const [nome, setNome] = useState("");

  return (
    <label>
      Nome
      <input
        value={nome}
        onChange={(evento) => setNome(evento.target.value)}
      />
    </label>
  );
}
```

O fluxo é: **digitação → evento `onChange` → atualização do estado**.

### Envio do formulário

O evento `onSubmit` executa uma função quando o formulário é enviado.
Essa função pode validar os dados ou exibir uma mensagem.

`preventDefault()` impede a ação padrão do navegador. Em formulários,
evita o recarregamento automático da página e permite que o React
controle o que acontece após o envio.

``` jsx
function enviar(e) {
  e.preventDefault();
  alert("Formulário enviado!");
}

<form onSubmit={enviar}>
  <button type="submit">Enviar</button>
</form>
```

## 3. useEffect

Efeitos permitem executar ações fora da renderização da interface,
especialmente quando o componente precisa interagir com recursos
externos. Exemplos apresentados: alterar o título da aba, utilizar
temporizadores e buscar dados de APIs.

`useEffect` é um Hook utilizado para sincronizar um componente com
sistemas externos. Recebe: - Uma função que contém o efeito. -
Opcionalmente, uma lista de dependências que controla quando o efeito
deve ser executado novamente.

Exemplo para definir o título da aba:

``` jsx
useEffect(() => {
  document.title = "Aula React";
}, []);
```

O array vazio `[]` indica, no exemplo apresentado, que o efeito será
executado na montagem do componente.

Se o efeito utiliza uma prop chamada `titulo`, ela deve aparecer nas
dependências para que o título da aba seja atualizado quando esse valor
mudar:

``` jsx
useEffect(() => {
  document.title = titulo;
}, [titulo]);
```

### Limpeza de um efeito

Alguns efeitos criam recursos que precisam ser liberados, como eventos e
temporizadores. Para isso, o `useEffect` pode retornar uma função de
limpeza.

A limpeza ocorre antes de uma nova configuração do efeito quando suas
dependências mudam e quando o componente deixa de ser utilizado.

``` jsx
useEffect(() => {
  window.addEventListener("resize", atualizar);

  return () => {
    window.removeEventListener("resize", atualizar);
  };
}, []);
```

A ideia principal é encerrar ou liberar corretamente aquilo que foi
configurado pelo efeito.

## 4. Consumo de APIs

API (Application Programming Interface) permite a comunicação entre
sistemas. Em aplicações React, possibilita buscar e enviar dados para
serviços externos, como produtos, usuários, publicações e indicadores.

### Buscando dados com fetch

`fetch()` realiza requisições HTTP. Como a resposta é assíncrona, é
necessário aguardar seu retorno.

-   `response.ok`: permite verificar se a resposta HTTP foi
    bem-sucedida.
-   `response.json()`: interpreta o conteúdo da resposta como JSON.
-   `await`: aguarda a conclusão de uma operação assíncrona.

Exemplo:

``` javascript
const response = await fetch(url);

if (!response.ok) {
  throw new Error("Erro");
}

const dados = await response.json();
```

### O papel do useEffect e do useState

O `useEffect` pode iniciar uma busca quando o componente é exibido. O
array vazio `[]` indica que o efeito será executado na montagem do
componente. O `useState` armazena os dados recebidos e atualiza a
interface quando eles mudam.

Exemplo de organização da busca:

``` jsx
useEffect(() => {
  async function carregar() {
    const resposta = await fetch(url);
    const dados = await resposta.json();
    setPublicacoes(dados);
  }

  carregar();
}, []);
```

### Enviando dados com POST

O método `POST` permite enviar informações para uma API.

-   `method` define o método HTTP.
-   `headers` informa o formato do conteúdo.
-   `JSON.stringify()` transforma um objeto JavaScript em JSON.
-   É importante verificar se a resposta foi bem-sucedida.

``` javascript
await fetch("/api/publicacoes", {
  method: "POST",
  headers: { "Content-Type": "application/json" },
  body: JSON.stringify({ title: "Aprendendo React" })
});
```

### Erros e cuidados importantes

-   Tratar erros de rede e verificar o status HTTP.
-   Considerar estados de carregamento, lista vazia e indisponibilidade
    do serviço.
-   Evitar requisições repetidas causadas por dependências incorretas no
    `useEffect`.
-   Não expor chaves secretas no código executado no navegador.
-   Respeitar autenticação, limites de uso e políticas de CORS.

A aula apresenta o uso de `try/catch` para tratar erros durante uma
requisição.

## 5. React Router

Uma aplicação React pode ter várias telas, como início, catálogo,
detalhes e sobre. O roteamento associa caminhos da URL aos componentes
que devem ser exibidos.

**React Router** é uma biblioteca utilizada para organizar a navegação
em aplicações React. Ela permite navegar entre páginas sem recarregar
todo o documento a cada clique.

### Conceitos fundamentais

-   **Rota:** regra que associa um caminho a uma interface.
-   **URL:** endereço da página atual.
-   **Link:** elemento utilizado para navegar entre rotas.
-   **Parâmetro:** parte variável do caminho.
-   **Rota aninhada:** rota organizada dentro de uma estrutura pai.

### Configurando as rotas

-   `BrowserRouter`: envolve a aplicação.
-   `Routes`: agrupa as rotas disponíveis.
-   `Route`: define o caminho e o componente correspondente.

``` jsx
import {
  BrowserRouter,
  Routes,
  Route
} from "react-router-dom";

<BrowserRouter>
  <Routes>
    <Route path="/" element={<Inicio />} />
    <Route path="/sobre" element={<Sobre />} />
  </Routes>
</BrowserRouter>
```

### Navegação com Link

O componente `Link` permite navegar entre rotas. A propriedade `to`
define o destino. Para navegação dentro da aplicação React, a aula
apresenta `Link` como alternativa preferível a um link tradicional.

``` jsx
import { Link } from "react-router-dom";

<nav>
  <Link to="/">Início</Link>
  <Link to="/sobre">Sobre</Link>
</nav>
```

### Parâmetros de rota

Parâmetros representam partes variáveis de uma URL e são úteis, por
exemplo, em páginas de detalhes. O Hook `useParams()` permite acessar
esses valores.

``` jsx
// Rota: /conceitos/:id
const { id } = useParams();

return <h1>Conceito: {id}</h1>;
```

## 6. Atividade proposta

Desenvolver uma aplicação React que utilize todos os conceitos da
aula: - State e `useState`. - Formulários. - `useEffect`. - Consumo de
APIs. - React Router.

A entrega deve incluir um repositório público no GitHub e um README
contendo a descrição, as funcionalidades e os conceitos utilizados.

## Links complementares indicados nos slides

-   **Conceitos:** https://github.com/deivisontakatu/aula-react
-   **Exemplo:** https://github.com/deivisontakatu/projeto-react
-   **Aplicação:** https://projeto-react-five-swart.vercel.app/

## Para memorizar

-   **State:** informação guardada pelo componente.
-   **useState:** cria um estado e fornece uma função para atualizá-lo.
-   **Campo controlado:** tem seu valor controlado pelo estado do React.
-   **onChange:** detecta alterações no campo.
-   **onSubmit:** trata o envio do formulário.
-   **preventDefault():** impede o comportamento padrão, como recarregar
    a página ao enviar um formulário.
-   **useEffect:** sincroniza o componente com sistemas externos.
-   **Limpeza do efeito:** libera recursos ou desfaz configurações.
-   **fetch():** realiza requisições HTTP.
-   **POST:** envia dados para uma API.
-   **React Router:** organiza a navegação entre telas por URLs.
-   **Link:** permite navegar entre rotas.
-   **useParams():** acessa parâmetros da URL.
