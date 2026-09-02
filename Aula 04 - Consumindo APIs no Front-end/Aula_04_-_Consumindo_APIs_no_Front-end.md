# Aula 04 — Consumindo APIs no Front-end 🔌

## 📚 Conteúdo da aula

- API (Application Programming Interface)
- Protocolo HTTP
- EndPoint
- JSON
- Servidor Backend e Web Service
- Criando uma API REST com Express
- Deploy de uma API
- Consumo da API pelo Front-end

---

# 1. 🔌 O que é uma API?

**API** significa **Application Programming Interface** (Interface de Programação de Aplicações).

É um conjunto de protocolos, rotinas e ferramentas que define como diferentes componentes de software podem se comunicar.

De forma simples, uma API funciona como uma ponte entre sistemas.

### Exemplo

```text
Front-end
   ↓
Requisição HTTP
   ↓
API / Backend
   ↓
Banco de dados
   ↓
Resposta JSON
   ↓
Front-end
```

---

# 2. 🌐 REST

**REST (Representational State Transfer)** é um estilo arquitetural utilizado principalmente no desenvolvimento de sistemas distribuídos na Web.

Entre seus princípios estão:

- Comunicação cliente-servidor;
- Comunicação stateless;
- Uso dos métodos HTTP;
- Recursos identificados por URIs;
- Representação de dados, como JSON.

---

# 3. 📡 HTTP

**HTTP (Hypertext Transfer Protocol)** é o protocolo utilizado para comunicação na Web.

Ele define as regras para que clientes e servidores troquem informações.

### Modelo cliente-servidor

```text
Cliente
   ↓
Requisição HTTP
   ↓
Servidor
   ↓
Processamento
   ↓
Resposta HTTP
   ↓
Cliente
```

### Stateless

Cada requisição HTTP é independente.

O servidor não precisa manter informações sobre requisições anteriores para processar uma nova requisição.

---

# 4. 📋 Métodos HTTP

## GET

Utilizado para recuperar informações.

```http
GET /users
```

Normalmente utilizado para consultar dados.

## POST

Utilizado para criar novos recursos.

```http
POST /users
```

## PUT

Utilizado para substituir completamente um recurso existente.

```http
PUT /users/1
```

## PATCH

Utilizado para atualizar parcialmente um recurso.

```http
PATCH /users/1
```

## DELETE

Utilizado para remover um recurso.

```http
DELETE /users/1
```

### Resumo

| Método | Função |
|---|---|
| GET | Consultar |
| POST | Criar |
| PUT | Substituir |
| PATCH | Atualizar parcialmente |
| DELETE | Remover |

---

# 5. 🎯 Endpoint

Um **endpoint** é uma URL específica utilizada para acessar um recurso ou funcionalidade de uma API.

Ele representa um ponto de comunicação entre cliente e servidor.

Exemplo:

```text
/users
```

Podemos ter diferentes operações para um mesmo endpoint:

```text
GET    /users
POST   /users
GET    /users/1
PUT    /users/1
DELETE /users/1
```

Cada combinação de método + endpoint representa uma operação diferente.

---

# 6. 📦 JSON

**JSON (JavaScript Object Notation)** é um formato leve para troca de dados.

É fácil para pessoas lerem e escreverem e também é fácil para máquinas processarem.

### Objeto

```json
{
  "nome": "Maria",
  "idade": 20
}
```

### Array

```json
[
  {
    "nome": "Maria"
  },
  {
    "nome": "João"
  }
]
```

As principais estruturas utilizadas são:

- Objetos: pares `nome/valor`;
- Arrays: listas ordenadas de valores.

---

# 7. 🔄 Como funciona uma requisição?

Um fluxo básico pode ser representado assim:

### 1. Front-end

O usuário acessa a página ou realiza alguma ação.

### 2. Requisição HTTP

O front-end envia uma requisição utilizando um método HTTP.

### 3. Backend

O servidor recebe a requisição, identifica a rota e executa a lógica necessária.

### 4. Banco de dados ou API externa

O servidor pode buscar, armazenar ou atualizar informações.

### 5. Resposta

O servidor retorna os dados, frequentemente em formato JSON.

### 6. Interface

O front-end recebe os dados e atualiza a tela.

---

# 8. 🖥️ Backend

O **servidor backend** é responsável por processar requisições, gerenciar dados e fornecer respostas aos clientes.

Entre suas funções estão:

- Armazenar e recuperar dados;
- Acessar bancos de dados;
- Executar regras de negócio;
- Fornecer APIs;
- Processar requisições.

---

# 9. 🌍 Web Service

Um **Web Service** é um serviço acessível pela Web que permite a comunicação entre sistemas utilizando HTTP/HTTPS.

Ele permite que sistemas diferentes, inclusive desenvolvidos com linguagens e tecnologias distintas, possam se comunicar de forma padronizada.

---

# 10. 🚂 Express.js

**Express.js** é um framework para Node.js utilizado para facilitar a criação de servidores web e APIs.

Ele é:
- Minimalista;
- Flexível;
- Popular no ecossistema JavaScript;
- Adequado para criação de APIs.

### Vantagens

O Express simplifica tarefas que seriam mais trabalhosas utilizando apenas o módulo HTTP do Node.js.

Ele facilita:

- Criação de rotas;
- Uso de middlewares;
- Tratamento de requisições;
- Criação de APIs.

---

# 11. 🧩 Middlewares

Middlewares são funções utilizadas para processar requisições e respostas.

Podem ser utilizados, por exemplo, para:

- Autenticação;
- Logs;
- Tratamento de requisições;
- Tratamento de erros.

---

# 12. 🛠️ Criando uma API REST com Express

## Passo 1 — Criar o projeto

Crie uma pasta para o projeto e abra no VS Code.

## Passo 2 — Instalar o Express

```bash
npm install express
```

## Passo 3 — Instalar o CORS

```bash
npm install cors express
```

## Passo 4 — Criar `api.js`

Nesse arquivo será implementado o servidor e suas rotas.

## Passo 5 — Executar

```bash
node api.js
```

---

# 13. 🔐 CORS

**CORS** é um mecanismo de segurança que controla o acesso entre diferentes domínios no navegador.

Ele é importante quando o front-end e o backend estão sendo executados em origens diferentes.

Exemplo:

```text
Front-end → Vercel
Backend   → Render
```

Nesse cenário, a configuração adequada do CORS permite a comunicação entre as aplicações.

---

# 14. ☁️ Render

O **Render** pode ser utilizado para hospedar serviços web e APIs.

Entre os recursos apresentados na aula estão:

- Integração com Git;
- Deploy automático;
- Suporte a Node.js;
- Certificado SSL;
- Escalabilidade;
- Interface simplificada.

---

# 15. 🚀 Deploy da API

Fluxo apresentado na aula:

### 1. GitHub

Primeiro, o projeto deve estar disponível em um repositório do GitHub.

### 2. Render

Criar uma conta e acessar o dashboard.

### 3. Criar Web Service

Conectar o repositório do GitHub ao Render.

### 4. Configurar comandos

**Build Command:**

```text
node
```

**Start Command:**

```text
node api.js
```

### 5. Deploy

Após o deploy, a API poderá ser acessada através do endereço disponibilizado pelo Render.

---

# 16. 🔗 Front-end consumindo a API

Depois que a API estiver online, o front-end pode realizar uma requisição para seu endpoint.

Exemplo conceitual:

```text
Front-end
   ↓
GET /data-hora
   ↓
API Express
   ↓
Resposta JSON
   ↓
Front-end
   ↓
Exibe data e hora
```

---

# 17. 📝 Atividade 01

Pesquisar **10 projetos no GitHub** que utilizem algum tipo de API.

Para cada projeto, identificar:

- Projeto;
- Framework utilizado;
- API consumida;
- Outras informações relevantes.

Depois, criar um arquivo Markdown com uma tabela contendo os projetos escolhidos e suas informações.

---

# 18. 📝 Atividade 02

Criar uma API utilizando Express com uma rota responsável por consultar **data e hora**.

Depois:

1. Fazer o deploy da API no Render;
2. Conectar o projeto ao GitHub;
3. Desenvolver um front-end;
4. Fazer o front-end consumir a API;
5. Exibir a data e hora na tela.

Também deve ser utilizado outro repositório para separar a API do Front-end.

### Documentação da atividade

O documento deve conter:

- Prints do código;
- Print da aplicação funcionando;
- Prints dos painéis do Render e Vercel;
- Links dos repositórios no GitHub.

---

# 🎯 Resumo da aula

APIs permitem que diferentes sistemas se comuniquem.

No desenvolvimento front-end, é comum o navegador realizar requisições HTTP para um backend, que processa a solicitação e retorna informações, geralmente em JSON.

Nesta aula foram estudados:

- APIs;
- REST;
- HTTP;
- Métodos HTTP;
- Endpoints;
- JSON;
- Backend;
- Web Services;
- Express.js;
- CORS;
- Render;
- Consumo de APIs pelo Front-end.

O principal fluxo aprendido foi:

```text
FRONT-END
    ↓
REQUISIÇÃO HTTP
    ↓
API / BACKEND
    ↓
PROCESSAMENTO
    ↓
JSON
    ↓
FRONT-END
    ↓
INTERFACE ATUALIZADA
```
# Links Projetos das aulas 

### Projeto express (apenas criação da api): https://github.com/Isabelly-Caroline/meu-projeto-express
### Projeto front and que consome da api: https://github.com/Isabelly-Caroline/projeto-api-data
