# 🚀 ROADMAP FLET + API + BANCO DE DADOS (Do Zero ao App Rodando no Celular)

## 1️⃣ Fundamentos do Flet

Aprenda o básico para criar apps simples.

## 🎯 O que estudar:
 * Instalação do Flet
 * Estrutura básica (`main(page)`)
 * Controles essenciais:
   * `TextField`, `ElevatedButton`, `Dropdown`, `Column`, `Row`
 * Eventos (`on_click`, `on_submit`)
 * Navegação entre páginas (`page.go`)

### ✔ Tarefas práticas:
 * Criar uma tela simples com botão + texto.
 * Criar 2 páginas navegáveis no app.

## 2️⃣ Layouts e Páginas Profissionais

Prepare-se para apps reais.

## 🎯 Estude:
 * `ResponsiveRow` e `Container`
 * Design com `padding`, `margin`, `alignment`
 * Criar componentes reaproveitáveis (classes)

### ✔ Tarefas práticas:
 * Criar uma NavBar lateral (como você já pediu)
 * Criar página Home, Login, Dashboard

## 3️⃣ Rodando o Flet no Celular

Importante para seus testes.

## 🎯 Você precisa aprender:
## 📱 Rodar via navegador do celular

1. Rodar com:
```sh
flet run --web --port 8550 main.py
```

2.Acessar no celular:
```cpp

http://SEU-IP:8550
```

## 📱 Transformar em APK (Android)

Hoje existem 2 caminhos:

### Caminho 1 — Puro WebApp (mais fácil)
 * Hospedar app como Web App (Netlify, Vercel)
 * Criar APK com Ionic Capacitor ou Android WebView

### Caminho 2 — Empacotamento com Flet (mais complexo)
 * Usar Flet + Buildozer (Linux) para gerar APK
(é possível, mas dá trabalho).

## 4️⃣ Criar Endpoints (API)

Use **FastAPI** (ideal com Flet).

### 🎯 Conceitos:

 * O que é uma API
 * Rotas GET, POST, PUT, DELETE
 * Pydantic models
 * Status codes (200, 201, 400, 401, 500)

### ✔ Tarefas práticas:

Criar rotas:
 * `POST /register` (cadastro)
 * `POST /login` (gera token)
 * `GET /user/me` (retorna dados do usuário)

## 5️⃣ JWT – Autenticação com Token

Login real para proteger páginas.

### 🎯 Aprender:
 * Criar token com validade
 * Middleware para verificar token
 * Proteger endpoints

### ✔ Tarefas práticas:
 * Após login, receber token
 * Enviar token em todas requisições privadas

## 6️⃣ Usando Banco de Dados

Use um banco simples e rápido.

### 🔥 Recomendado:
 * **SQLite** (mais fácil)
 * **PostgreSQL** (produtivo)

## 🎯 Conceitos:
 * Tabelas
 * CRUD
 * ORM (SQLAlchemy)

### ✔ Tarefas práticas:

Criar tabelas:
 * Users
 * Products (opcional)
 * Logs (opcional)

## 7️⃣ Integrando FLET com sua API

Aqui o app ganha vida real.

## 🎯 O que aprender:
 * Usar `httpx` ou `requests` dentro do Flet
 * Criar login consumindo API externa
 * Redirecionar usuário ao dashboard após login

### ✔ Tarefa:

Criar formulário usando:
```python
async def login():
    response = await client.post("/login", json=data)
```

## 8️⃣ Salvando Sessão no FLET

Depois do login, armazenar token.

**Métodos**:
 * `page.client_storage`
 * Variáveis globais
 * Arquivo local (opção)

## 9️⃣ Deploy

Para publicar seu app:

## 📌 API:
 * Render
 * Railway
 * Deta

## 📌 Flet Web:
 * Netlify
 * Vercel

## 🎯 Resumo do Roadmap (com ordem e foco)
## ✔ Etapa 1 — Básico do Flet
## ✔ Etapa 2 — Layout + Navegação
## ✔ Etapa 3 — Rodar no celular (via Web)
## ✔ Etapa 4 — Criar API com FastAPI
## ✔ Etapa 5 — Autenticação JWT
## ✔ Etapa 6 — Banco de dados com SQLAlchemy
## ✔ Etapa 7 — Integração Flet ↔ API
## ✔ Etapa 8 — Sessão e Token
## ✔ Etapa 9 — Deploy Web + Android
