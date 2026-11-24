# Aula 05 — Criando APIs para o Front-end

**Disciplina:** Frameworks Front-end  
**Professor:** Prof. Me. Deivison S. Takatu

## 1. Objetivo da aula

A aula apresentou os conceitos fundamentais de APIs e comunicação entre Front-end e Back-end. Na parte prática, foi desenvolvido o planejamento de uma API REST com Express.js para gerenciar notas, aplicando as operações CRUD. Também foram abordados o deploy da aplicação e a documentação e os testes de APIs com Postman.

## 2. Conceitos fundamentais

### API (Application Programming Interface)

Uma API é uma interface que permite a comunicação entre diferentes aplicações. No contexto da aula, ela funciona como um meio para o Front-end solicitar informações ou operações ao Back-end.

### Protocolo HTTP e métodos

O HTTP é utilizado na comunicação entre cliente e servidor. A aula apresentou os principais métodos:

| Método | Finalidade |
|---|---|
| **GET** | Recuperar informações do servidor. É seguro e idempotente: chamadas repetidas não alteram os dados. |
| **POST** | Criar novos recursos. Não é idempotente: chamadas repetidas podem criar vários recursos. |
| **PUT** | Substituir completamente um recurso existente. |
| **PATCH** | Atualizar parcialmente um recurso. |
| **DELETE** | Remover um recurso específico. É idempotente: repetir a exclusão não altera o resultado final. |

### Endpoint

Um endpoint é uma URL específica que dá acesso a um recurso ou funcionalidade de uma API. É o ponto de comunicação entre o cliente e o servidor.

Exemplo apresentado: uma API pode disponibilizar uma rota para listar usuários por GET e outra para adicionar um usuário por POST.

### JSON (JavaScript Object Notation)

JSON é um formato leve de troca de dados, fácil de ler e escrever por pessoas e também de interpretar e gerar por máquinas.

Suas estruturas principais são:
- **Objetos:** conjuntos de pares nome/valor.
- **Arrays:** listas ordenadas de valores.

É utilizado na aula para representar e armazenar os dados das notas.

## 3. Back-end e Web Service

### Servidor Back-end

É o sistema responsável por processar requisições, gerenciar dados e fornecer respostas para clientes, como navegadores e aplicativos.

Suas funções principais incluem:
- Armazenar e recuperar dados em um banco de dados ou outra forma de armazenamento.
- Executar regras de negócio.
- Disponibilizar APIs para a comunicação com outros sistemas.

### Web Service

É um serviço acessível pela web que permite a comunicação entre sistemas por meio de HTTP/HTTPS. Possibilita que aplicações com linguagens, plataformas ou tecnologias diferentes se comuniquem de forma padronizada.

## 4. Criando uma API REST com Express.js

### O que é Express.js?

Express.js é um framework para Node.js que facilita a criação de servidores web e APIs. É apresentado como uma ferramenta minimalista, flexível e popular no ecossistema JavaScript.

Principais características:
- **Simplificação:** reduz a quantidade de código necessária em comparação com o uso direto do módulo HTTP do Node.js.
- **Roteamento:** facilita a criação de rotas, como `/users` e `/products`.
- **Middlewares:** funções que processam requisições e respostas, podendo ser usadas para autenticação e registros de logs.
- **Agilidade:** permite criar APIs e servidores web de maneira leve e rápida.

A aula também comparou um servidor feito com Node.js puro e outro feito com Express.js, mostrando como o Express simplifica a definição de rotas.

### Quando utilizar Express.js?

O material indica o Express.js para:
- Criar APIs REST e integrar aplicações com bancos de dados.
- Desenvolver back-ends para aplicações web e mobile.
- Servir páginas com templates.
- Utilizar middlewares para autenticação, logs e tratamento de erros.
- Fazer protótipos rapidamente.

O material recomenda considerar WebSockets para aplicações em tempo real e Workers para processamento pesado.

### Primeira configuração

A sequência apresentada para iniciar uma API simples foi:

1. Criar uma pasta para o projeto e abri-la no VS Code.
2. Instalar o Express:
   ```bash
   npm install express
   ```
3. Instalar o CORS:
   ```bash
   npm install cors express
   ```
4. Criar o arquivo `api.js`, configurar a aplicação e definir uma rota.
5. Executar o servidor:
   ```bash
   node api.js
   ```

**CORS** é um mecanismo de segurança que controla o acesso entre domínios diferentes no navegador.

## 5. Publicação do Back-end com Render

O Render foi apresentado como uma plataforma de hospedagem em nuvem que suporta Node.js, Python e outras linguagens, além de integração com repositórios Git.

Entre os benefícios citados estão:
- Deploy simplificado e atualizações automáticas via GitHub.
- Planos gratuitos para projetos pequenos.
- Escalabilidade e monitoramento de desempenho.
- Certificado SSL.

### Etapas de publicação apresentadas

1. Enviar o projeto para um repositório no GitHub.
2. Criar uma conta no Render.
3. Criar um novo **Web Service** e conectar o repositório.
4. Configurar os comandos de build e inicialização indicados nos slides:
   - Build Command: `node`
   - Start Command: `node api.js`
5. Realizar o deploy e acessar a aplicação pela URL fornecida pelo Render, no formato `seu-projeto.onrender.com`.

## 6. Projeto prático: API de notas com CRUD

Na segunda parte prática, o projeto inicial foi ampliado. Em vez de apenas exibir data e hora, a proposta passou a ser uma aplicação para criar, visualizar, editar e excluir notas.

O projeto utiliza:
- **Express.js:** configuração do servidor e criação das rotas da API.
- **JSON (`data.json`):** armazenamento das notas.
- **`server.js`:** arquivo responsável por configurar e executar o servidor.
- **Body-Parser:** leitura de dados enviados no corpo das requisições HTTP, como JSON em requisições POST e PUT.
- **FS:** módulo utilizado no exemplo para ler e gravar o arquivo de dados.

### Operações CRUD

CRUD representa as quatro operações básicas de manipulação de dados:

| Operação | Método e endpoint | O que faz |
|---|---|---|
| **Create** | `POST /api/notes` | Cria uma nota com título e texto. A nota recebe um ID gerado com `Date.now().toString()`. |
| **Read** | `GET /api/notes` | Retorna todas as notas armazenadas. |
| **Read por ID** | `GET /api/notes/:id` | Retorna uma nota específica pelo identificador. |
| **Update** | `PUT /api/notes/:id` | Atualiza o título e o texto de uma nota existente. |
| **Delete** | `DELETE /api/notes/:id` | Remove uma nota pelo identificador. |

No exemplo de atualização, caso a nota não seja encontrada, a API retorna o status HTTP **404** e uma mensagem de erro. Na exclusão, o exemplo retorna uma mensagem confirmando a remoção.

### Organização e funcionamento dos arquivos

O material demonstra funções para:
- **Ler as notas:** acessar `data.json` e converter o conteúdo JSON em dados utilizáveis pelo JavaScript. Se ocorrer erro na leitura, o exemplo retorna uma lista vazia.
- **Salvar as notas:** converter a lista para JSON e gravá-la no arquivo.
- **Executar as rotas:** cada método HTTP chama a operação correspondente e devolve uma resposta ao cliente.

O arquivo `data.json` contém uma lista de objetos. Cada nota do exemplo possui campos como `id`, `titulo`, `texto` e `criadoEm`.

### Etapas para executar e conectar o projeto

1. Criar a pasta `projeto-notas` e abri-la no VS Code.
2. Instalar o Express:
   ```bash
   npm install express
   ```
3. Instalar o Body-Parser:
   ```bash
   npm install body-parser
   ```
4. Criar o arquivo `server.js` com a configuração do servidor e as rotas CRUD.
5. Criar o arquivo `data.json` com os dados das notas.
6. Executar o servidor:
   ```bash
   node server.js
   ```
7. Criar o Front-end em React para listar, cadastrar, editar e excluir notas, consumindo a API.
8. Enviar o Back-end ao GitHub e publicá-lo no Render.
9. No React, substituir o endereço local `http://localhost:3000/api/notes` pelo endpoint disponibilizado pelo Render.
10. Enviar o Front-end ao GitHub e publicá-lo na Vercel.

## 7. Atividades propostas

### Atividade 01

- Atualizar o repositório da disciplina com todos os arquivos e alterações, garantindo que ele contenha a versão final da atividade.
- Conferir se os arquivos foram enviados corretamente.
- Copiar o link do repositório atualizado e enviá-lo pelo formulário indicado nos slides.

### Atividade 02 — Aplicação de notas

- Desenvolver a API com Express.js e publicá-la no Render.
- Construir um Front-end que consuma as rotas da API e permita criar, visualizar, editar e excluir notas.
- Fazer a aplicação interagir com os dados armazenados no arquivo JSON.
- Preparar um documento com prints do código e da aplicação em funcionamento, além dos links do repositório no GitHub e do deploy na Vercel.

O material também apresenta duas referências de código para consulta:
- `https://github.com/deivisontakatu/exemplo-api-backend`
- `https://github.com/deivisontakatu/exemplo-api-frontend`

### Questões para refletir

A atividade propõe analisar:
- Quais são os riscos de segurança do projeto e como poderiam ser reduzidos.
- Se armazenar dados em um arquivo JSON é adequado para produção, considerando vantagens e desvantagens.
- Quais seriam as limitações dessa abordagem com 10.000 notas.
- Por que concentrar todo o código em `server.js` pode ser um problema e como organizar melhor a lógica.

## 8. Documentação e testes de APIs com Postman

### Documentação de uma API

Uma API normalmente é acompanhada de documentação técnica para explicar como utilizá-la. Essa documentação deve apresentar:
- Endpoints disponíveis.
- Métodos HTTP suportados.
- Parâmetros exigidos.
- Formatos das respostas.
- Exemplos de requisições.

### Postman

Postman é uma ferramenta para criar, testar, documentar e monitorar requisições HTTP.

Com ele, é possível:
- Enviar requisições GET, POST, PUT e DELETE.
- Analisar as respostas da API.
- Criar coleções para organizar e compartilhar endpoints.
- Utilizar variáveis de ambiente.
- Criar scripts pré-request e testes automatizados.
- Gerar documentação.
- Utilizar recursos como Mock Servers e monitoramento.

O material também menciona suporte a GraphQL, WebSockets e autenticação OAuth 2.0, além da integração com pipelines CI/CD por meio do Newman (interface de linha de comando do Postman).

### Atividade de documentação no Postman

- Criar uma coleção no Postman documentando as quatro operações CRUD da API.
- Configurar as requisições HTTP e os parâmetros necessários para cada endpoint.
- Descrever claramente os códigos de resposta.
- Organizar um documento com prints do código e da aplicação em funcionamento e o link da coleção do Postman.
- Enviar o documento pela plataforma CANVA, conforme orientado nos slides.

## 9. Resumo geral

A aula mostrou como o Front-end pode se comunicar com um Back-end por meio de APIs. Foram estudados os métodos HTTP, endpoints e o formato JSON, além do papel de servidores Back-end e Web Services.

Na prática, o foco foi criar uma API REST usando Node.js e Express.js, implementar operações CRUD para uma aplicação de notas e armazenar os dados em um arquivo JSON. Também foram apresentados o processo de publicação do Back-end no Render, a conexão com um Front-end desenvolvido em React e a publicação do Front-end na Vercel. Por fim, a aula abordou a importância de documentar e testar APIs utilizando o Postman.

**Principal aprendizado:** uma aplicação Front-end pode utilizar uma API para solicitar e manipular dados mantidos no Back-end. O Express.js facilita a criação dessa API, enquanto o Postman auxilia na validação e na documentação dos endpoints.
