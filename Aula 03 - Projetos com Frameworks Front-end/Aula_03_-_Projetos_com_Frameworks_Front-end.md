# Aula 03 — Projetos com Frameworks Front-end 🚀

## 📚 Conteúdo da aula

- Introdução aos Frameworks Front-end
- Framework × Biblioteca
- React, Vue, Angular e Next.js
- Comparação entre frameworks
- Criação e estrutura de projetos
- Git e versionamento
- Atividade prática

---

## 1. 🌐 O que é um Framework Front-end?

Um framework front-end é um conjunto de ferramentas, bibliotecas e convenções que ajuda a padronizar o desenvolvimento de interfaces web.

Ele fornece uma estrutura para desenvolver aplicações de forma mais organizada, facilitando a criação e manutenção de projetos complexos.

### Vanilla JavaScript × Framework

**Sem framework:**
- Código desenvolvido manualmente;
- Maior possibilidade de repetição;
- Manutenção mais difícil em projetos grandes.

**Com framework:**
- Componentes reutilizáveis;
- Gerenciamento de estado;
- Atualizações mais eficientes da interface;
- Estrutura mais organizada.

---

## 2. 🧩 Framework × Biblioteca

### Framework

Um framework possui uma estrutura mais definida e pode controlar o fluxo da aplicação.

Características:
- Inversão de controle;
- Estrutura definida;
- Pode oferecer diversas funcionalidades integradas.

Exemplos:
- Angular
- Vue

### Biblioteca

Uma biblioteca é mais flexível: o desenvolvedor decide quando e como utilizá-la.

Exemplos:
- React
- jQuery

> **Resumo:** em uma biblioteca, você chama o código quando precisa. Em um framework, o framework participa mais ativamente do fluxo da aplicação.

---

## 3. 💡 Por que utilizar frameworks?

Os frameworks oferecem recursos que tornam o desenvolvimento mais produtivo:

- **Produtividade:** soluções prontas para tarefas como roteamento, estado e renderização.
- **Boas práticas:** organização através de componentes e padrões.
- **Manutenção:** mecanismos internos que tornam as atualizações da interface mais eficientes.
- **Comunidade:** documentação, plugins e soluções para problemas comuns.
- **Testes:** suporte a testes unitários e de integração.
- **Acessibilidade:** componentes e padrões que podem facilitar a criação de interfaces acessíveis.

---

## 4. 🧱 Principais características

### Componentização

A aplicação é dividida em componentes independentes e reutilizáveis.

Um componente pode encapsular:
- Estrutura;
- Estilos;
- Lógica;
- Comportamentos.

Isso facilita a manutenção e permite reutilizar partes da interface.

### Programação reativa

Frameworks como React, Vue e Angular permitem que a interface seja atualizada de acordo com alterações no estado da aplicação.

### Build e Bundling

Ferramentas de build podem:
- Minificar arquivos;
- Transpilar código;
- Combinar arquivos;
- Melhorar desempenho e compatibilidade.

### Rotas

Permitem criar aplicações com diferentes páginas e views, incluindo SPAs (Single Page Applications).

### Integração com APIs

Frameworks facilitam chamadas assíncronas e a integração entre a interface e serviços externos.

---

# 5. ⚛️ React

O React foi desenvolvido pelo Facebook e é uma biblioteca JavaScript voltada para a criação de interfaces de usuário.

Apesar de ser frequentemente chamado de framework, tecnicamente é uma **biblioteca**.

Ele trabalha com componentes reutilizáveis e utiliza o Virtual DOM.

### Conceitos importantes

#### `useState`

Hook utilizado para gerenciar o estado de um componente funcional.

#### `useEffect`

Hook utilizado para lidar com efeitos colaterais, como chamadas de API.

#### JSX

Permite escrever uma estrutura semelhante ao HTML dentro do JavaScript.

Algumas diferenças:
- Expressões JavaScript utilizam `{}`;
- Atributos utilizam camelCase;
- `class` é escrito como `className`;
- Tags precisam ser fechadas.

### Gerenciamento de estado

O React possui diferentes possibilidades para gerenciamento de estado.

**Context API**
- Simples;
- Útil para estados menores ou compartilhados.

**Redux**
- Mais indicado para estados complexos e globalmente compartilhados.

---

## 6. 🖥️ DOM e Virtual DOM

O **DOM (Document Object Model)** representa a estrutura de uma página web em forma de árvore.

O JavaScript pode utilizar o DOM para alterar o conteúdo da página.

O React utiliza o **Virtual DOM**, uma representação que permite comparar alterações antes de aplicá-las ao DOM real.

De forma simplificada:

```text
Estado muda
   ↓
Virtual DOM é atualizado
   ↓
React compara as alterações
   ↓
Somente as diferenças necessárias são aplicadas
   ↓
DOM real é atualizado
```

---

# 7. 🅰️ Angular

Angular é um framework desenvolvido pelo Google para criação de aplicações web.

Ele oferece uma estrutura completa para desenvolvimento.

### Destaques

- Framework completo;
- Roteamento;
- HTTP Client;
- Injeção de dependências;
- TypeScript;
- Arquitetura organizada;
- CLI;
- Change Detection.

### Conceitos fundamentais

**Componentes**
- Estruturados com HTML, CSS e TypeScript;
- Utilizam `@Component`.

**Serviços**
- Permitem organizar lógica reutilizável;
- Utilizam `@Injectable`.

**Data Binding**
- Interpolação: `{{ }}`
- Two-way binding: `[(ngModel)]`

**Roteamento**
- Permite navegar entre diferentes views da aplicação.

---

## Criando um projeto Angular

### 1. Instalar o Angular CLI

```bash
npm install -g @angular/cli
```

### 2. Criar o projeto

```bash
ng new meu-app-angular
```

### 3. Entrar na pasta

```bash
cd meu-app-angular
```

### 4. Abrir no VS Code

```bash
code .
```

### 5. Iniciar o servidor

```bash
ng serve
```

### Angular CLI

O Angular CLI é uma ferramenta de linha de comando utilizada para criar, gerenciar e construir projetos Angular.

---

# 8. 🟢 Vue.js

Vue.js é um framework progressivo que pode ser adotado gradualmente, desde pequenos projetos até aplicações mais complexas.

### Características

- Progressivo;
- Reatividade eficiente;
- Componentes;
- Single-File Components (SFC);
- Curva de aprendizado acessível;
- Virtual DOM;
- Performance otimizada.

Nos **Single-File Components**, HTML, CSS e JavaScript podem ficar organizados em um único arquivo `.vue`.

## Criando um projeto Vue

```bash
npm create vue@latest
```

Depois:

```bash
cd meu-projeto-vue
npm install
code .
npm run dev
```

### Estrutura

- `node_modules`: dependências;
- `public`: arquivos estáticos;
- `src`: código-fonte;
- `assets`: imagens, fontes e CSS;
- `components`: componentes reutilizáveis;
- `App.vue`: componente raiz;
- `main.js`: ponto de entrada;
- `index.html`: HTML da SPA;
- `vite.config.js`: configurações do Vite.

---

# 9. ▲ Next.js

Next.js é um framework baseado em React para desenvolvimento de aplicações web modernas e full-stack.

Ele adiciona recursos ao React, como:

- Roteamento baseado em arquivos;
- Renderização no servidor;
- Server Components;
- Otimização de imagens e fontes;
- Páginas e layouts;
- Recursos de backend;
- Otimizações de desempenho e SEO.

## Criando um projeto Next.js

```bash
npx create-next-app@latest meu-projeto
```

Depois:

```bash
cd meu-projeto
code .
npm run dev
```

### App Router

No App Router, a pasta `app` é utilizada para organizar a aplicação.

Arquivos `page.js` definem páginas, enquanto a organização das pastas determina as rotas.

---

# 10. 📊 Comparação entre as tecnologias

| Tecnologia | Tipo | Característica principal |
|---|---|---|
| React | Biblioteca | Componentização e flexibilidade |
| Angular | Framework | Solução completa e estruturada |
| Vue | Framework | Progressivo e acessível |
| Next.js | Framework baseado em React | Recursos avançados para aplicações web |

A escolha deve considerar:
- Complexidade do projeto;
- Curva de aprendizado;
- Desempenho;
- Escalabilidade;
- Manutenção;
- Comunidade.

---

# 11. 📁 Buscando projetos prontos

Não é necessário começar todos os projetos do zero.

A comunidade open source disponibiliza projetos que podem servir como modelos.

### Onde pesquisar?

- GitHub;
- Vercel Templates;
- CodeSandbox.

No GitHub, um projeto pode ser clonado utilizando:

```bash
git clone <url>
```

---

# 12. 🔀 Git e versionamento

Durante o desenvolvimento, os projetos devem ser versionados utilizando Git.

O histórico de commits permite acompanhar a evolução da aplicação.

Os projetos devem ser organizados em seus respectivos repositórios no GitHub.

---

# 13. 📝 Atividade

Desenvolver, em grupo, quatro projetos Web sobre o mesmo tema utilizando:

1. React;
2. Vue;
3. Angular;
4. Next.js.

Os projetos devem ser:
- Funcionais;
- Responsivos;
- Organizados;
- Baseados em componentes;
- Utilizando recursos básicos da tecnologia escolhida.

Também deve ser criada uma cópia de um projeto a partir de um repositório.

Ao final, deve ser feita uma comparação entre as quatro tecnologias, destacando as diferenças encontradas durante o desenvolvimento.

---

## 🎯 Resumo da aula

Frameworks front-end ajudam a organizar e acelerar o desenvolvimento de aplicações web. A aula apresentou React, Angular, Vue e Next.js, mostrando suas características, estruturas e formas de criação de projetos.

A principal ideia é entender que cada tecnologia possui uma proposta diferente e que a escolha depende das necessidades do projeto.

# Links dos Projetos

### React: https://github.com/Isabelly-Caroline/meu-projeto-react
### Vue: https://github.com/Isabelly-Caroline/meu-projeto-vue
### Angular: https://github.com/Isabelly-Caroline/meu-app-angular
### Next: https://github.com/Isabelly-Caroline/meu-projeto-next


