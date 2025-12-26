# 🧩 Open Posts - Backend

Servidor básico em **Node.js + Express** para fornecer persistência de dados ao front-end do projeto *Open Posts*.
Seu objetivo é simular uma API real, permitindo que o front-end busque e envie postagens (posts) dinamicamente.

---

## 🚀 Tecnologias utilizadas

- **Node.js** — Ambiente de execução JavaScript no servidor
- **Express** — Framework minimalista para criação de APIs REST
- **Body-parser** — Middleware para interpretar JSON no corpo das requisições
- **File System (fs/promises)** — Para leitura e escrita dos dados localmente em um arquivo JSON

---

## 📁 Estrutura do projeto

```plaintext
open-posts-backend/
│
├── app.js                # Arquivo principal do servidor Express
├── package.json          # Configurações do projeto e dependências
├── data/
│   └── posts.js          # Funções utilitárias para leitura e escrita dos posts
└── posts.json            # "Banco de dados" local para armazenar as postagens
```

---

## ⚙️ Instalação e execução

1. **Clonar o repositório:**

```bash
git clone https://github.com/leandro-courses/open-posts-backend.git
cd open-posts-backend
```

2. **Instalar as dependências:**

```bash
npm install
```

3. **Executar o servidor:**

```bash
npm start
```

4. O servidor será iniciado em:

```bash
http://localhost:8080
```

---

## 🧭 Rotas disponíveis

### `GET /posts`

Retorna todas as postagens armazenadas no arquivo `posts.json`.

**Exemplo de resposta:**

```json
{
  "posts": [
    { "body": "React is awesome!", "author": "Deacon", "id": "0.3798321547132723" }
  ]
}
```

---

### `GET /posts/:id`

Retorna uma única postagem com base no `id` informado.

**Exemplo:**

```json
GET /posts/0.3798321547132723
```

**Resposta:**

```json
{
  "post": { "body": "React is awesome!", "author": "Deacon", "id": "0.3798321547132723" }
}
```

---

### `POST /posts`

Cria uma nova postagem e a adiciona ao arquivo `posts.json`.

**Exemplo de requisição:**

```json
{
  "author": "Alice",
  "body": "Next.js is awesome!"
}
```

**Resposta:**

```json
{
  "message": "Stored new post.",
  "post": {
    "author": "Alice",
    "body": "Next.js is awesome!",
    "id": "0.123456789"
  }
}
```

---

## 🔄 Persistência dos dados

As postagens são salvas no arquivo **`posts.json`**, dentro da raiz do projeto.
Isso permite simular uma API com armazenamento local, sem a necessidade de um banco de dados real.

---

## 🔐 CORS

O servidor está configurado para aceitar requisições de **qualquer origem (`*`)**,
permitindo que o front-end e o back-end rodem em domínios diferentes durante o desenvolvimento.

---

## 🧠 Objetivo educacional

Este projeto faz parte de um **curso introdutório de React**, e serve como um back-end mínimo para:

* Demonstrar requisições HTTP (GET e POST);
* Simular operações CRUD básicas;
* Trabalhar com estado e efeitos no front-end;
* Tornar o aprendizado mais prático e próximo de um ambiente real.

---

👨‍💻 **Autor:** *Leandro Medvedev*
