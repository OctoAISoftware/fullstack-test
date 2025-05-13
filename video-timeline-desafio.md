# Desafio Técnico Full-Stack: Plataforma de Linha do Tempo de Vídeos

## Visão Geral

Crie uma plataforma moderna de linha do tempo de vídeos que permita aos usuários enviar, gerenciar e visualizar vídeos em formato cronológico. Este desafio avalia suas habilidades com streaming de vídeo, atualizações em tempo real e tecnologias web modernas.

---

## Requisitos Técnicos

### Frontend (Next.js 14)
- Utilizar Next.js 14 com App Router
- Implementar com TypeScript
- Utilizar Shadcn/UI como design system
- Implementar TailwindCSS para estilização
- Criar UI moderna e responsiva
- Implementar tratamento de erros e estados de carregamento
- Usar React Query para gerenciamento de estado
- Implementar fluxo de autenticação adequado

### Backend (Nest.js)
- Criar API RESTful com Nest.js
- Implementar autenticação e autorização adequadas
- Utilizar PostgreSQL como banco de dados
- Tratar erros e validar entradas corretamente
- Criar documentação com Swagger
- Implementar sistema de logs

### Infraestrutura
- Usar PM2 para gerenciamento de processos
- Configurar corretamente variáveis de ambiente
- Implementar medidas de segurança

---

## Funcionalidades Principais

### Sistema de Autenticação
- Registro e login de usuários
- Autenticação via JWT
- Controle de acesso baseado em papéis (Admin/Usuário)
- Recuperação de senha

### Gerenciamento de Vídeos
- Upload com indicação de progresso
- Acompanhamento do status de processamento
- Gerenciamento de metadados básicos
- Atualização e remoção de vídeos

### Implementação da Linha do Tempo
- Exibição cronológica de vídeos
- Atualizações em tempo real via WebSocket
- Scroll infinito
- Busca e filtros

### Reprodução de Vídeos
- Player customizado com controles básicos
- Suporte a streaming adaptativo
- Memória de posição de reprodução
- Suporte a Picture-in-Picture

---

## Especificações Técnicas

### Frontend

#### Configuração do Next.js
- Configuração com TypeScript
- TailwindCSS
- Integração com Shadcn/UI
- Variáveis de ambiente

#### Autenticação
- Rotas protegidas
- Contexto de autenticação
- Gestão de tokens
- Manutenção de sessão

#### Componente da Linha do Tempo
- Lista virtualizada para performance
- Suporte a drag and drop
- Atualizações em tempo real
- Design responsivo

---

### Backend

#### Schema do Banco

```sql
CREATE TABLE users (
  id SERIAL PRIMARY KEY,
  email VARCHAR(255) UNIQUE NOT NULL,
  password_hash VARCHAR(255) NOT NULL,
  role VARCHAR(50) NOT NULL,
  created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);

CREATE TABLE videos (
  id SERIAL PRIMARY KEY,
  title VARCHAR(255) NOT NULL,
  description TEXT,
  url VARCHAR(255) NOT NULL,
  thumbnail_url VARCHAR(255),
  duration INTEGER,
  user_id INTEGER REFERENCES users(id),
  created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);
```

#### Endpoints da API
- `POST /api/auth/login`
- `POST /api/auth/register`
- `POST /api/videos`
- `GET /api/videos`
- `GET /api/videos/:id`
- `PUT /api/videos/:id`
- `DELETE /api/videos/:id`

#### Processamento de Vídeo
- Validação de formato
- Geração de thumbnail
- Transcodificação
- Rastreamento de progresso

---

## Pontos Extras

### Melhorias Técnicas
- Capítulos no vídeo
- Anotações em vídeo
- Colaboração em tempo real
- Análises de vídeo

### Infraestrutura
- Containerização com Docker
- Pipeline de CI/CD
- Testes unitários e de integração
- Otimização de performance

### Banco de Dados
- PostgreSQL com migrações
- Indexação
- Cache

---

## Critérios de Avaliação

### Qualidade do Código
- Código limpo e manutenível
- Uso adequado de TypeScript
- Tratamento de erros
- Organização

### Implementação Técnica
- Uso correto de recursos do Next.js e Nest.js
- Design e queries do banco
- Implementação de APIs

### UI/UX
- Design responsivo
- Estados de carregamento e erro
- Feedback ao usuário

### Performance
- Otimização de frontend, backend e banco
- Tempo de resposta das APIs

---

## Entregáveis

### Repositório
- Histórico limpo de commits
- README com instruções
- Exemplo de variáveis de ambiente
- Documentação da API

### Documentação Técnica
- Visão geral da arquitetura
- Decisões técnicas
- Limitações conhecidas
- Melhorias futuras

### Deploy
- Link da demo online
- Instruções de deploy
- Configuração do PM2
- Guia de setup do ambiente

---

Este desafio avalia sua capacidade de:
- Trabalhar com frameworks modernos (Next.js, Nest.js)
- Lidar com vídeos e atualizações em tempo real
- Escrever código limpo e documentado
- Fazer deploy e gerenciar uma aplicação completa