# 📚 Aula 02 — Configuração do Ambiente de Desenvolvimento

> **Disciplina:** Frameworks Front-end  
> **Professor:** Prof. Me. Deivison S. Takatu

---

## 🎯 Objetivo da aula

Nesta aula, foram apresentados os principais conceitos e ferramentas utilizados para preparar um ambiente de desenvolvimento Front-end, passando por **versionamento, Git, VS Code, Node.js, NPM, React e deploy com Vercel**.

---

## 🔄 1. Versionamento

O **versionamento** é o processo de atribuir um identificador único para cada versão de um documento ou software. Ele permite registrar **o que mudou, quem realizou a alteração e quando ela aconteceu**.

### 🆚 Versionamento x Backup

| Versionamento 🔄 | Backup 💾 |
|---|---|
| Mantém o histórico das alterações | Mantém uma cópia pontual |
| Registra quem, quando e por quê | Não possui rastreio detalhado |
| Permite colaboração | Trabalha com uma cópia do estado atual |
| Possibilita reversões específicas | Geralmente restaura o estado completo |

### ⭐ Benefícios

- 👥 Trabalho simultâneo entre desenvolvedores
- ♻️ Menos retrabalho
- 🔎 Auditoria e rastreabilidade
- ⏪ Recuperação de versões anteriores
- 🤝 Colaboração mais segura
- 🧪 Possibilidade de testar versões antes da publicação

---

## 🔢 2. Versionamento Semântico (SemVer)

O **Versionamento Semântico** utiliza o padrão:

```text
MAJOR.MINOR.PATCH
```

### 📌 O que significa cada parte?

- 🔴 **MAJOR:** mudanças incompatíveis com versões anteriores.
- 🟡 **MINOR:** novas funcionalidades compatíveis com versões anteriores.
- 🟢 **PATCH:** correções de bugs sem alteração da API.

### 💡 Exemplos

```text
1.0.0 → Primeira versão estável
1.1.0 → Nova funcionalidade compatível
1.1.1 → Correção de bug
2.0.0 → Mudança incompatível
```

### 🛠️ Tipos de alterações

- 🐞 **Bug Fix:** correção de erros.
- ✨ **New Feature:** nova funcionalidade.
- 🔧 **Feature Enhancement:** melhoria de uma funcionalidade existente.
- ♻️ **Refactoring:** reorganização do código.
- ⚡ **Performance:** otimização de desempenho.
- 🔐 **Security Patch:** correção de vulnerabilidades.
- 📦 **Dependency Update:** atualização de dependências.
- 🧪 **Adding Tests:** inclusão de testes automatizados.

---

## 🐙 3. Git e Controle de Versão

O **Git** é um sistema de controle de versão utilizado para registrar e acompanhar alterações nos arquivos de um projeto.

Com ele é possível:

- 📜 Registrar versões do projeto.
- 🔎 Acompanhar alterações.
- ⏪ Restaurar versões anteriores.
- ☁️ Sincronizar o projeto com repositórios online.
- 👥 Facilitar o trabalho em equipe.

### ⚙️ Configuração inicial

Depois de instalar o Git, pode ser necessário configurar nome e e-mail:

```bash
git config --global user.name "<Nome>"
git config --global user.email "<Email>"
```

Para verificar se o Git foi instalado corretamente:

```bash
git --version
```

---

## 🏷️ 4. Tags no Git

As **tags** são marcadores utilizados para identificar pontos específicos do histórico do projeto, principalmente versões estáveis ou releases.

### 📌 Tipos

- **Lightweight:** apenas um nome associado a um commit.
- **Annotated:** armazena informações adicionais, como autor, data e mensagem.

### 💻 Comandos

Listar tags:

```bash
git tag
```

Criar uma tag:

```bash
git tag <nome-da-tag>
```

Exemplo:

```bash
git tag 1.0.0
```

Enviar a tag para o repositório remoto:

```bash
git push origin <nome-da-tag>
```

---

## 🌿 5. Boas Práticas com Git

Algumas boas práticas apresentadas:

- ✅ Fazer commits pequenos e frequentes.
- 📝 Utilizar mensagens de commit claras.
- 🌿 Utilizar branches para novas funcionalidades e correções.
- 🛡️ Manter a branch principal estável.
- 🧪 Realizar testes antes de fazer merge.

---

## 💻 6. IDE e Visual Studio Code

**IDE (Integrated Development Environment)** é um ambiente que reúne recursos para **desenvolver, testar, executar e depurar software**.

O **Visual Studio Code (VS Code)** é um editor de código que, com extensões e ferramentas integradas, oferece diversos recursos encontrados em uma IDE.

---

## 🟢 7. Node.js

O **Node.js** é um ambiente de execução JavaScript que permite executar código no **backend, no servidor**.

Uma das vantagens é poder utilizar **JavaScript tanto no navegador quanto no servidor**, facilitando a integração entre Front-end e Back-end.

Para verificar a instalação:

```bash
node --version
```

---

## 📦 8. NPM — Node Package Manager

O **NPM** é o gerenciador de pacotes do Node.js e é instalado automaticamente junto com ele.

Ele permite:

- 📥 Instalar bibliotecas e frameworks.
- 🔄 Atualizar dependências.
- 🗑️ Remover pacotes.
- 📦 Gerenciar dependências do projeto.
- 🤝 Facilitar a colaboração entre desenvolvedores.

### 📄 package.json

O `package.json` registra informações e dependências do projeto.

Ao executar:

```bash
npm install
```

o NPM instala automaticamente os pacotes necessários.

---

## ⚛️ 9. Criando um Projeto React

O comando apresentado para criar uma aplicação React é:

```bash
npx create-react-app meu-projeto-react
```

O `npx` é um executor de pacotes NPM que acompanha o Node.js, enquanto o `create-react-app` gera a estrutura inicial da aplicação.

### 🚀 Passo a passo

**1. Criar o projeto:**

```bash
npx create-react-app meu-projeto-react
```

**2. Entrar na pasta:**

```bash
cd meu-projeto-react
```

**3. Abrir no VS Code:**

```bash
code .
```

**4. Iniciar o servidor local:**

```bash
npm start
```

---

## 📁 10. Estrutura do Projeto React

### `node_modules`

📦 Contém os pacotes e bibliotecas instalados no projeto.

### `public`

🌐 Contém arquivos como HTML, JSON e imagens.

### `src`

⚛️ Contém os arquivos JavaScript/React da aplicação.

### `.gitignore`

🚫 Define arquivos e diretórios que devem ser ignorados pelo Git, como arquivos que não devem ser versionados.

### `package.json`

📄 Contém informações e dependências do projeto.

### `package-lock.json`

🔒 Contém informações relacionadas às dependências instaladas.

### Arquivos principais

- `index.js` → ponto de entrada do React.
- `App.js` → componente raiz da aplicação.
- `App.css` → estilos do componente `App`.
- `index.css` → estilos globais da aplicação.

---

## 🚀 11. Deploy

**Deploy** é o processo de colocar uma aplicação em produção, tornando-a acessível aos usuários finais.

### 🔄 Etapas comuns

1. 🏗️ Compilação do código
2. ⚙️ Configuração do ambiente
3. 🧪 Testes finais
4. 🌎 Publicação

---

## ▲ 12. Vercel

A **Vercel** é uma plataforma voltada para facilitar o deploy de sites estáticos e aplicações modernas.

### ⭐ Principais características

- ☁️ Hospedagem simplificada.
- 🔗 Integração com GitHub, GitLab e Bitbucket.
- ⚛️ Suporte a frameworks modernos.
- ⚡ Deploys rápidos.
- ⏪ Possibilidade de rollback.
- 🌍 CDN global.
- 📈 Escalabilidade automática.
- 🔐 Recursos voltados para segurança e performance.
- 🖥️ Serverless Functions.

---

## 📝 13. Atividade Prática

A atividade proposta consiste em:

1. ⚛️ Desenvolver uma aplicação React utilizando o VS Code.
2. 🐙 Utilizar o Git para versionar o projeto.
3. 📤 Realizar `commit` e `push` para um repositório no GitHub.
4. ▲ Fazer o deploy da aplicação na Vercel.
5. 🔗 Conectar o repositório à Vercel para publicação automática.
6. 🌎 Ao final, disponibilizar o projeto através de uma URL pública da Vercel.

---

## 📌 Resumo Geral

```text
VS Code
   ↓
Node.js + NPM
   ↓
React
   ↓
Git
   ↓
GitHub
   ↓
Vercel
   ↓
🌎 Aplicação Online
```

### 🧠 O que lembrar para a prova/aula?

- 🔄 **Versionamento** → histórico e controle das alterações.
- 🔢 **SemVer** → `MAJOR.MINOR.PATCH`.
- 🐙 **Git** → controle de versão.
- 🏷️ **Tags** → identificam versões importantes.
- 🌿 **Branches** → permitem desenvolver mudanças separadamente.
- 💻 **VS Code** → ambiente/editor para desenvolvimento.
- 🟢 **Node.js** → execução de JavaScript no servidor.
- 📦 **NPM** → gerenciamento de pacotes.
- ⚛️ **React** → criação de aplicações Front-end.
- 🚀 **Deploy** → publicação da aplicação.
- ▲ **Vercel** → plataforma para hospedagem e deploy.

---

> 📚 **Material baseado na Aula 02 — Configuração do Ambiente de Desenvolvimento, da disciplina Frameworks Front-end.**

### Link do projeto react 
https://github.com/Isabelly-Caroline/meu-projeto-react
   