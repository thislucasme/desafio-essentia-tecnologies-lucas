```md
# Desafio Técnico | Essentia Technologies

> **Nota:** O projeto teve maior foco na arquitetura, backend, segurança e integração da aplicação. O frontend foi desenvolvido priorizando funcionalidade e responsividade, sem um foco aprofundado em UI/UX.

## Aplicação de Gerenciamento de Tarefas

O projeto consiste em um sistema de gerenciamento de tarefas com autenticação de usuários, permitindo que cada usuário cadastre, visualize, edite e exclua suas próprias tarefas.

## Tecnologias utilizadas

### Frontend

- Angular
- TypeScript
- Cloudflare Turnstile

### Backend

- NestJS
- TypeScript
- TypeORM
- MySQL
- JWT
- Swagger

### Infraestrutura

- Docker
- Nginx
- PM2
- Vercel
- VPS
- HTTPS / Let's Encrypt

## Funcionalidades implementadas

- Cadastro de usuários
- Login e autenticação com JWT
- Proteção de rotas autenticadas
- Isolamento das tarefas por usuário
- Criação de tarefas
- Edição de tarefas
- Exclusão de tarefas
- Alteração do status das tarefas
- Paginação
- Validação dos dados da API
- Proteção contra requisições automatizadas com Cloudflare Turnstile
- Documentação da API com Swagger

## Aplicação publicada

O frontend e o backend foram disponibilizados publicamente para facilitar a avaliação do projeto.

**Aplicação**

https://desafio-essentia-tecnologies-front.vercel.app/

**Documentação da API**

https://desafioessentiatecnologies.duckdns.org:4178/api/docs

## Arquitetura

O frontend desenvolvido em Angular se comunica com uma API REST desenvolvida em NestJS.

A autenticação é realizada através de JWT e as rotas protegidas permitem acesso somente aos dados pertencentes ao usuário autenticado.

A persistência dos dados utiliza MySQL através do TypeORM.

Em produção, o frontend está hospedado na Vercel e o backend em uma VPS, utilizando Nginx como reverse proxy, PM2 para gerenciamento do processo Node.js e HTTPS com certificado Let's Encrypt.

## Executando localmente

### Pré-requisitos

- Node.js 20+
- npm
- Docker e Docker Compose
- Git

### 1. Clone o projeto

```bash
git clone https://github.com/thislucasme/desafio-essentia-tecnologies-lucas.git
cd desafio-essentia-tecnologies-lucas
```

### 2. Instale as dependências

Na raiz do projeto:

```bash
npm install
```

Instale também as dependências do backend:

```bash
cd backend
npm install
```

### 3. Configure o backend

Na pasta `backend`, crie um arquivo `.env`:

```env
NODE_ENV=development
PORT=3008

FRONTEND_URL=http://localhost:4200

DB_HOST=localhost
DB_PORT=3309
DB_USERNAME=todo_user
DB_PASSWORD=todolist1234_
DB_DATABASE=todo_list
DB_SYNCHRONIZE=true

JWT_SECRET=uma-chave-local
JWT_EXPIRES_IN=1d

TURNSTILE_SECRET_KEY=SUA_SECRET_KEY
```

### 4. Configure o frontend

No arquivo:

```text
src/environments/environment.development.ts
```

Configure:

```typescript
export const environment = {
  production: false,
  apiUrl: 'http://localhost:3008/api',
  turnstileSiteKey: 'SUA_SITE_KEY'
};
```

Para utilizar o Cloudflare Turnstile localmente, configure uma chave válida para `localhost` ou utilize as chaves de teste disponibilizadas pela Cloudflare.

### 5. Inicie o banco de dados

Na pasta `backend`:

```bash
docker compose up -d
```

### 6. Inicie o backend

Ainda na pasta `backend`:

```bash
npm run start:dev
```

A API estará disponível em:

```text
http://localhost:3008/api
```

A documentação Swagger estará disponível em:

```text
http://localhost:3008/api/docs
```

### 7. Inicie o frontend

Em outro terminal, na raiz do projeto:

```bash
npm start
```

A aplicação estará disponível em:

```text
http://localhost:4200
```

## Código-fonte

https://github.com/thislucasme/desafio-essentia-tecnologies-lucas
```

Mantive a apresentação, tecnologias, funcionalidades, deploy e arquitetura que você queria, mas reduzi a execução local ao fluxo necessário. Isso elimina boa parte do excesso do README anterior, que chegava a ter seções separadas para testes, logs, portas, CORS, 401, Swagger etc.
