# Karoline Silva

**Backend Developer** · Go e Node.js

Construo APIs e serviços de produção: modelagem de domínio, transação e
concorrência corretas, mensageria assíncrona e testes que rodam em CI contra
banco de verdade.

Também entrego a interface quando o produto pede. Já fiz frontend, mobile e
design system, e isso me deixa mais rápida no que interessa aqui: eu desenho API
sabendo como ela vai ser consumida, porque já estive do outro lado dela.

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=flat-square&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/karoline-silva-8070a634b/)
[![Email](https://img.shields.io/badge/Email-EA4335?style=flat-square&logo=gmail&logoColor=white)](mailto:karoline.sln22@gmail.com)

---

## Backend

### [Jungle Apostas](https://github.com/KarolineCodes/Jungle-API-) · Go

API de apostas com **transação e concorrência levadas a sério**: o débito da
carteira e a criação da aposta acontecem no mesmo commit, e `SELECT ... FOR
UPDATE` impede que duas requisições simultâneas do mesmo jogador gastem o mesmo
saldo duas vezes.

Dinheiro em inteiro de centavos, DDD em três camadas com o domínio sem
dependência de infraestrutura, WebSocket para o resultado da rodada em tempo
real, e eventos publicados só depois do commit.

`Go` · `Uber Fx` · `PostgreSQL` · `WebSocket` · `AWS (SNS, SQS, S3, Secrets Manager)` · `Docker`

### [E-mail Dispatch](https://github.com/KarolineCodes/emaildispatch) · Go

Disparo de e-mail em massa com IP e DKIM próprios. Arquitetura hexagonal e
**núcleo sem dependência externa**, multi-cliente, com aquecimento de IP.

`Go` · `SMTP` · `DKIM`

### [Cadência](https://github.com/KarolineCodes/cadencia) · API + monorepo TypeScript

Plataforma para escolas de idiomas. A parte que vale olhar é a **segurança e a
suíte de testes**: renovação de token rotativa com detecção de reúso (token
reaproveitado derruba a família inteira), autorização por recurso filtrando pelo
id do token, e recurso alheio respondendo 404 em vez de 403 para não confirmar
que o registro existe.

356 testes unitários e 138 de integração contra Postgres real, com CI que barra o
merge por tipo quebrado, segredo no histórico ou vulnerabilidade alta.

`Fastify` · `PostgreSQL` · `JWT` · `Zod` · `Vitest` · `React`

### [Copiloto de Atendimento](https://github.com/KarolineCodes/copiloto-atendimento) · IA + engenharia

O modelo **nunca vê os dados brutos e nunca calcula**. Ele chama ferramentas
tipadas, o código computa, o modelo narra — o que elimina a classe de erro mais
comum em produto com LLM: número inventado com confiança.

Provedores Anthropic, OpenAI e simulado; roda por completo sem chave de API.

`TypeScript` · `Fastify` · `SSE` · `Tool calling`

---

## Mobile e frontend

### [Caderneta](https://github.com/KarolineCodes/Caderneta-Flutter) · Flutter offline-first

Controle de fiado para pequeno comércio. SQLite é a fonte da verdade, não um
cache: escrita local e fila de envio na **mesma transação**, e lançamento é fato
imutável — o que torna a sincronização entre aparelhos uma união de conjuntos em
vez de um merge de dinheiro.

`Flutter` · `Dart` · `SQLite` · `Riverpod`

### [Maré UI](https://github.com/KarolineCodes/Mare-UI-Storybook) · design system

15 componentes acessíveis, arquitetura de tokens em duas camadas, 73 testes e
Storybook publicado.

`React` · `TypeScript` · `Storybook`

---

## Stack

**Backend** — Go, Node.js (NestJS, Fastify), Python (FastAPI), Kotlin

**Dados** — PostgreSQL, MySQL, MongoDB, Redis, SQLite, Supabase

**Infra e mensageria** — AWS (SNS, SQS, S3, Secrets Manager), Docker, CI/CD,
Google Cloud, Azure

**IA** — LangChain, LangGraph, LlamaIndex, RAG, tool calling, agentes autônomos

**Também trabalho com** — Next.js, React, TypeScript, Flutter, React Native,
Kotlin Multiplatform

---

## Onde estou hoje

**Software Engineer** no Estúdio Oggi. Backend em Python e Node, **sistema
próprio de disparo de e-mail em Golang**, integração de fluxos e agentes com
LangChain e LangGraph, e as interfaces em Next.js quando o produto precisa.

Antes, **AI Engineer** no Studio Beyond — agentes autônomos para qualificação de
leads, com pipelines assíncronos integrando LLMs a bancos de dados e tratamento
de falhas em conversas de múltiplos turnos.

---

![Estatísticas](https://github-readme-stats.vercel.app/api?username=KarolineCodes&show_icons=true&theme=dark&hide_border=true&bg_color=0D1117&title_color=9D7BEA&icon_color=B794F6&text_color=A0AEC0)
