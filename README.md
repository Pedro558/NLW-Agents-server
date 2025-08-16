## 📝 Sobre o Projeto

O NLW Agents é uma API desenvolvida para gerenciar salas de aula virtuais e interativas, permitindo a criação de perguntas e respostas baseadas em transcrições de áudio. O principal objetivo do projeto é facilitar a organização e o acesso a conteúdos educacionais, utilizando tecnologias modernas como processamento de linguagem natural e vetores para busca semântica.

## 🛠️ Funcionalidades Principais:

- Gerenciamento de Salas: Criação e listagem de salas com descrições personalizadas.
- Envio de Áudios: Upload de áudios para uma sala específica, com transcrição automática e geração de embeddings para busca semântica.
- Criação de Perguntas: Envio de perguntas relacionadas ao conteúdo da sala, com respostas automáticas baseadas nas transcrições dos áudios enviados.
- Busca Semântica: Utilização de vetores para encontrar trechos relevantes dos áudios e gerar respostas precisas.
- API Simples e Intuitiva: Endpoints organizados para facilitar a integração com aplicações externas.

Este projeto é ideal para instituições de ensino, plataformas de e-learning ou qualquer cenário que exija organização e interação com conteúdos educacionais de forma eficiente e moderna.

## 🚀 Tecnologias

- **Node.js** com TypeScript nativo (experimental strip types)
- **Fastify** - Framework web rápido e eficiente
- **PostgreSQL** com extensão **pgvector** para vetores
- **Drizzle ORM** - Type-safe database operations
- **Zod** - Schema validation
- **Docker** - Containerização do banco de dados

## 🏗️ Arquitetura

O projeto segue uma arquitetura modular com:

- **Separação de responsabilidades** entre rotas, schemas e conexão com banco
- **Validação de schemas** com Zod para type safety
- **ORM type-safe** com Drizzle para operações de banco de dados
- **Validação de variáveis de ambiente** centralizadas

## ⚙️ Setup e Configuração

### Pré-requisitos

- Node.js (versão com suporte a `--experimental-strip-types`)
- Docker e Docker Compose

### 1. Clone o repositório
```bash
git clone <url-do-repositorio>
cd server
```

### 2. Configure o banco de dados
```bash
docker-compose up -d
```

### 3. Configure as variáveis de ambiente

Crie um arquivo `.env` na raiz do projeto:

```env
PORT=3333
DATABASE_URL=postgresql://docker:docker@localhost:5432/agents
```

### 4. Instale as dependências
```bash
npm install
```

### 5. Execute as migrações do banco
```bash
npx drizzle-kit migrate
```

### 6. (Opcional) Popule o banco com dados de exemplo
```bash
npm run db:seed
```

### 7. Execute o projeto

**Desenvolvimento:**
```bash
npm run dev
```

**Produção:**
```bash
npm start
```

## 📚 Scripts Disponíveis

- `npm run dev` - Executa o servidor em modo de desenvolvimento com hot reload
- `npm start` - Executa o servidor em modo de produção
- `npm run db:seed` - Popula o banco de dados com dados de exemplo

## 🌐 Endpoints

A API estará disponível em `http://localhost:3333`

- `GET /health` - Health check da aplicação
- `GET /rooms` - Lista as salas disponíveis

---

Desenvolvido com ❤️ durante o NLW da Rocketseat.
