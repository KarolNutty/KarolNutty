# Karoline Silva

**Backend Developer** · Go e Node.js

APIs e serviços de produção: modelagem de domínio, transação e concorrência
corretas, comunicação entre serviços e testes que rodam em CI contra banco de
verdade.

Também entrego a interface quando o produto pede. Já fiz frontend, mobile e
design system, e isso me ajuda no que interessa aqui: desenho API sabendo como
ela vai ser consumida, porque já estive do outro lado dela.

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=flat-square&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/karolinencs)
[![Email](https://img.shields.io/badge/Email-EA4335?style=flat-square&logo=gmail&logoColor=white)](mailto:karoline.ncs22@gmail.com)

---

## Backend

### [Jungle Apostas](https://github.com/KarolineCodes/Jungle-API-) + [Jungle Limites](https://github.com/KarolineCodes/jungle-limites) · Go

Dois serviços conversando por gRPC. O de apostas expõe REST e WebSocket; o de
limites responde uma pergunta só, **esse jogador pode fazer essa aposta agora**,
verificando limite diário, velocidade e autoexclusão.

Débito da carteira e criação da aposta acontecem no mesmo commit, e
`SELECT ... FOR UPDATE` impede que duas requisições simultâneas do mesmo jogador
gastem o mesmo saldo duas vezes. A verificação de limites roda **fora da
transação**: chamada de rede com transação aberta segura conexão do pool e lock
de linha, e um serviço lento vira banco travado.

A decisão que vale discutir é o ***fail closed***: com o serviço de limites fora
do ar, a aposta é **recusada**. O reflexo normal seria seguir em frente para não
derrubar o produto, mas entre as regras verificadas está a autoexclusão —
aceitar aposta de quem se autoexcluiu é falha regulatória, não degradação
aceitável. Tem teste provando o comportamento.

Domínio sem dependência de infraestrutura, dinheiro em inteiro de centavos,
eventos publicados só depois do commit, e um documento explicando o porquê de
cada decisão.

`Go` · `gRPC` · `Protocol Buffers` · `Uber Fx` · `PostgreSQL` · `WebSocket` · `AWS (SNS, SQS, S3, Secrets Manager)` · `Docker`

### [Cadência](https://github.com/KarolineCodes/cadencia) · API + monorepo TypeScript

Plataforma de estudo para escolas de idiomas, com área do aluno e painel do
professor. O mesmo módulo de agendamento roda no navegador e no servidor, então
a tela responde na hora e os dois não têm como divergir.

Do lado do servidor: **renovação de token rotativa com detecção de reúso** (um
token reaproveitado derruba a família inteira, o que transforma um roubo
silencioso de trinta dias num logout que a pessoa percebe), autorização por
recurso filtrando pelo id do token, e recurso alheio respondendo **404 em vez de
403** — um 403 confirmaria que o registro existe e permitiria mapear a base
variando o id.

Repetição espaçada adaptada ao calendário da escola, nivelamento que converge em
oito perguntas, correção de redação e conversação com IA que cita o trecho exato
e é verificada contra o texto. 356 testes unitários e 138 de integração contra
Postgres real, com CI que barra o merge por tipo quebrado, segredo no histórico
ou vulnerabilidade alta.

`Fastify` · `PostgreSQL` · `JWT` · `Zod` · `Vitest` · `React`

### [E-mail Dispatch](https://github.com/KarolineCodes/emaildispatch) · Go

Disparo de e-mail em massa com IP e DKIM próprios. Arquitetura hexagonal com
**núcleo sem nenhuma dependência externa**, multi-cliente, com aquecimento de IP
conduzido por IA.

`Go` · `SMTP` · `DKIM`

### [Copiloto de Atendimento](https://github.com/KarolineCodes/copiloto-atendimento) · IA + engenharia

Painel de analytics onde o modelo **nunca vê os dados brutos e nunca calcula**.
Ele chama ferramentas tipadas, o código computa, o modelo narra — o que elimina
a classe de erro mais comum em produto com LLM: número inventado com confiança.

Provedores Anthropic, OpenAI e simulado; roda por completo sem chave de API.

`TypeScript` · `Fastify` · `SSE` · `Tool calling`

---

## Mobile e frontend

### [Caderneta](https://github.com/KarolineCodes/Caderneta-Flutter) · Flutter offline-first

Controle de fiado para pequeno comércio. SQLite é a fonte da verdade, não um
cache: escrita local e fila de envio na **mesma transação**, e lançamento é fato
imutável — o que torna a sincronização entre aparelhos uma união de conjuntos em
vez de um merge de dinheiro. Domínio em Dart puro, 123 testes sem emulador.

`Flutter` · `Dart` · `SQLite` · `Riverpod`

### [Painel MF](https://github.com/KarolineCodes/painel-mf) · micro frontends

Painel montado por três aplicações independentes com Module Federation. Quatro
barreiras de isolamento garantem que um módulo remoto fora do ar não derrube o
resto, e a comunicação passa só por um barramento de eventos tipado.

`Vite` · `Module Federation` · `React` · `TypeScript`

### [Maré UI](https://github.com/KarolineCodes/Mare-UI-Storybook) · design system

Biblioteca de componentes com arquitetura de tokens em duas camadas, tema claro
e escuro, 15 componentes acessíveis verificados por teste e Storybook publicado.

`React` · `TypeScript` · `Storybook` · `Testing Library`

---

## Stack

**Backend** — Go, Node.js (NestJS, Fastify e Express), Python (FastAPI).

**Comunicação** — REST, gRPC e Protocol Buffers, WebSocket, SSE, mensageria
assíncrona

**Dados** — PostgreSQL, MySQL, MongoDB, Redis, SQLite, Supabase

**Infra** — AWS (SNS, SQS, S3, Secrets Manager), Google Cloud, Docker,
CI/CD

**IA** — LangChain, LangGraph, LlamaIndex, arquitetura RAG, agentes autônomos,
tool calling

**Também trabalho com** — Next.js, React, TypeScript, Tailwind, Flutter (BLoC,
Riverpod, GoRouter), React Native.

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
