# NLW Agents - Server

API RESTful desenvolvida durante o bootcamp **NLW Agents** da [Rocketseat](https://rocketseat.com.br), utilizando tecnologias modernas para construção de aplicações robustas e escaláveis.

## 🚀 Tecnologias Utilizadas

### Core

- **Node.js** - Runtime JavaScript
- **TypeScript** - Superset tipado do JavaScript
- **Fastify** - Framework web de alta performance
- **Zod** - Validação de esquemas e tipagem

### Banco de Dados

- **PostgreSQL** - Banco de dados relacional
- **pgvector** - Extensão para vetores no PostgreSQL
- **Drizzle ORM** - ORM type-safe para TypeScript
- **Drizzle Kit** - CLI para migrações

### Desenvolvimento

- **Biome** - Linter e formatter
- **Docker** - Containerização
- **Ultracite** - Regras de código

## 📁 Estrutura do Projeto

```
src/
├── db/
│   ├── schema/         # Esquemas do banco de dados
│   ├── migrations/     # Migrações do banco
│   ├── connection.ts   # Configuração da conexão
│   └── seed.ts         # Seeds do banco
├── http/
│   └── routes/         # Rotas da API
├── env.ts              # Validação de variáveis de ambiente
└── server.ts           # Configuração do servidor
```

## 🔧 Configuração e Setup

### Pré-requisitos

- Node.js (versão 18 ou superior)
- Docker e Docker Compose
- Git

### 1. Clone o repositório

```bash
git clone <url-do-repositorio>
cd server
```

### 2. Configure as variáveis de ambiente

Copie o arquivo de exemplo e configure suas variáveis:

```bash
cp .env.example .env
```

Edite o arquivo `.env` com suas configurações:

```env
PORT=3333
DATABASE_URL=postgresql://[usuario]:[senha]@localhost:5432/agents
```

> **Nota:** Para desenvolvimento local, use as credenciais configuradas no `docker-compose.yml`

### 3. Inicie o banco de dados

```bash
docker-compose up -d
```

### 4. Execute as migrações

```bash
npx drizzle-kit migrate
```

### 5. Execute o seed (opcional)

```bash
npm run db:seed
```

### 6. Inicie o servidor

**Desenvolvimento:**

```bash
npm run dev
```

**Produção:**

```bash
npm start
```

## 📡 API Endpoints

### Health Check

- `GET /health` - Verifica se a API está funcionando

### Rooms

- `GET /rooms` - Lista todas as salas

## 🔄 Scripts Disponíveis

- `npm run dev` - Inicia o servidor em modo de desenvolvimento com hot reload
- `npm start` - Inicia o servidor em modo produção
- `npm run db:seed` - Executa o seed do banco de dados

## 🐳 Docker

O projeto utiliza **pgvector/pgvector:pg17** como imagem base do PostgreSQL, que inclui a extensão `vector` para trabalhar com embeddings e busca semântica.

### Configuração do Banco:

- **Usuário:** docker
- **Senha:** docker
- **Database:** agents
- **Porta:** 5432

## 🎯 Padrões de Projeto

- **Type-safe API** com Fastify e Zod
- **Schema-first** com validação de entrada e saída
- **Repository Pattern** com Drizzle ORM
- **Environment validation** com Zod
- **Snake case** para nomenclatura do banco de dados
- **Modular routing** com plugins do Fastify

## 🔍 Recursos Especiais

- **Type Safety completo** em toda a aplicação
- **Validação automática** de requests e responses
- **Hot reload** para desenvolvimento
- **Migrações versionadas** com Drizzle Kit
- **CORS configurado** para desenvolvimento local

---

Desenvolvido durante o **NLW Agents** da **Rocketseat**
