# AdsPilot — Media Buyer Virtual para Instagram

> Ferramenta de IA que guia vendedores e influenciadores brasileiros no Instagram a encontrar clientes e melhorar o impacto dos seus anúncios.

---

## Visão do Produto

**O que é:** Um media buyer virtual — IA especializada em Meta Ads para o mercado brasileiro que orienta desde o primeiro anúncio até a otimização avançada.

**Para quem:**
- Vendedores no Instagram (MEIs, lojas, confeiteiras, artesãs)
- Influenciadores que vendem produtos/serviços
- Pequenas agências que gerenciam contas de clientes

**Proposta de valor:** O vendedor não precisa entender dashboards nem ser técnico. Ele conversa, recebe diagnósticos e ações claras — como ter um gestor de tráfego no bolso.

**Diferenciais:**
- Foco 100% no mercado brasileiro (PT-BR, PIX, WhatsApp, sazonalidade BR)
- Dois modos: Advisor (iniciantes, sem API) e Analyst (dados reais conectados)
- Custo acessível para quem não pode pagar um media buyer humano (R$2-5k/mês)

---

## Dois Modos de Operação

| Modo | Para quem | Fonte de dados | Exemplo |
|------|-----------|----------------|---------|
| **Advisor** | Iniciantes, quem nunca anunciou | Conversa + knowledge base | "Me ajuda a criar meu primeiro anúncio" |
| **Analyst** | Quem já anuncia e quer melhorar | Meta Ads API + knowledge base | "Por que meu custo por mensagem subiu?" |

---

## Roadmap de Fases

| Fase | Nome | Descrição | Dependência |
|------|------|-----------|-------------|
| **1** | Base de Conhecimento (Brain) | O que a IA sabe sobre ads | Nenhuma |
| **2** | Chat Interface (Boca) | Como o usuário conversa | Fase 1 |
| **3** | Controle de Usuários (Identidade) | Cadastro, login, perfil | Fase 2 |
| **4** | Cobrança e Pagamentos (Caixa) | Planos, créditos, billing | Fase 3 |
| **5** | Controle de Acesso (Porteiro) | Permissões, limites, tiers | Fase 4 |
| **6** | Painel Administrativo (Cockpit) | Métricas, gestão, controle | Fase 5 |
| **7** | APIs Externas (Olhos e Mãos) | Conexão Meta Ads, dados reais | Fase 6 |
| **8** | Evolução Contínua (Motor Vivo) | Updates, feedback, novos features | Permanente |

---

## Princípios de Engenharia

| Princípio | Aplicação |
|-----------|-----------|
| Nada escrito na pedra | Config > hardcode. Feature flags > deploys rígidos |
| Performance | Cache agressivo, modelo certo por tarefa, lazy loading |
| Manutenabilidade | Código limpo, separação de responsabilidades, docs |
| Conhecimento atualizado | Pipeline de atualização, alertas de staleness |
| Escalabilidade | Arquitetura que serve 10 e 10.000 usuários sem rewrite |
| Observabilidade | Logs, métricas, custos — tudo visível |

---

## Modelo de Negócio

### Custos (Claude API — Sonnet 5)

| Tipo de interação | Custo estimado |
|-------------------|----------------|
| Pergunta simples | ~R$0.07 |
| Análise de campanha | ~R$0.21 |
| Plano estratégico | ~R$0.35 |
| Sessão completa (5-10 msgs) | ~R$0.50-1.00 |

### Precificação (sugestão inicial)

| Plano | Preço | Inclui | Margem estimada |
|-------|-------|--------|-----------------|
| Básico | R$49/mês | 30 consultas, modo Advisor | ~85% |
| Pro | R$97/mês | Ilimitado, Meta Ads conectado | ~70% |
| Agência | R$297/mês | Múltiplas contas, relatórios | ~65% |
| Free trial | R$0 | 3 consultas para experimentar | — |

---

## Informações Coletadas do Usuário (7 categorias, ~50 campos)

### 1. Onboarding & Perfil (5 campos)
- Nome / nome do negócio
- Nível de experiência com ads
- Como vende hoje (DM, WhatsApp, site)
- Tempo de negócio
- Motivação para buscar ads

### 2. Produto & Oferta (8 campos)
- O que vende (produto/serviço)
- Categoria (moda, alimentos, beleza, educação, serviços)
- Faixa de preço
- Produto principal (best-seller)
- Diferencial
- Promoção ativa
- Tipo: físico / digital / serviço
- Região de entrega

### 3. Público & Mercado (9 campos)
- Cliente ideal (descrição)
- Cidade / estado / região
- Gênero foco
- Faixa etária
- Nível de renda do cliente
- Interesses do cliente
- Onde o cliente está online
- Concorrentes / inspirações
- Base de clientes existente (para lookalike)

### 4. Orçamento & Finanças (7 campos)
- Orçamento mensal para ads
- Primeiro investimento em ads?
- Ticket médio
- Margem de lucro estimada
- Meio de pagamento pronto (cartão no Meta)
- Sustentabilidade do orçamento (30+ dias?)
- Meta de faturamento com ads

### 5. Assets Criativos (9 campos)
- Tem fotos do produto?
- Qualidade (profissional / celular)
- Tem vídeos?
- Frequência de criação de conteúdo
- Tem depoimentos de clientes?
- Tem logo / identidade visual?
- Quem cria conteúdo (próprio / contratado)
- Conforto em aparecer na câmera
- Tem UGC (conteúdo de clientes)

### 6. Metas & Sucesso (7 campos)
- Objetivo principal (vendas / seguidores / DMs / awareness)
- Como mede sucesso hoje
- O que seria um bom resultado
- Expectativa de prazo
- Já tentou ads antes?
- Se sim, o que deu errado?
- Visão de longo prazo

### 7. Conta & Prontidão Técnica (10 campos)
- Conta Business ou Creator?
- Conectada a Facebook Page?
- Número de seguidores
- Taxa de engajamento (percepção)
- Meta Business Suite configurado?
- Conta de anúncios ativa ou restrita?
- Meta Pixel instalado?
- Destino atual do tráfego
- Tem site / landing page?
- Instagram ligado ao WhatsApp Business?

### Coleta conversacional (não é formulário)

```
"Me conta: o que você vende e onde?"          → Cobre categorias 1 + 2
"Pra quem você vende hoje?"                   → Cobre categoria 3
"Quanto pode investir em anúncios?"           → Cobre categoria 4
"Já tem fotos/vídeos bons do produto?"        → Cobre categoria 5
"O que seria um bom resultado pra você?"      → Cobre categoria 6
"Sua conta é comercial? Tá ligada ao Face?"   → Cobre categoria 7
```

---

## Plataformas & Integrações

### Core (obrigatório)

| Plataforma | Papel |
|------------|-------|
| Instagram | Canal principal dos sellers |
| Meta Ads Manager | Motor de anúncios |
| Facebook | Requisito técnico (Page) |
| WhatsApp Business | Destino de tráfego #1 no Brasil |

### APIs Meta (Fase 7)

| API | Função |
|-----|--------|
| Instagram Graph API | Perfil, métricas, conteúdo |
| Marketing API | Campanhas, ad sets, anúncios, insights |
| Conversions API (CAPI) | Tracking de conversões |
| WhatsApp Business API | Integração com mensagens |

### Integrações futuras

- Shopify / Nuvemshop / Mercado Shops (catálogo)
- Hotmart / Kiwify (infoprodutos)
- Google Sheets (relatórios)
- PIX / gateways de pagamento (conversão real)

---

## FASE 1 — Base de Conhecimento (ATIVA)

### Arquitetura: 3 Camadas

```
┌───────────────────────────────────────────────────────┐
│ CAMADA 3 — Contexto do Usuário (por sessão)           │
│ Perfil coletado na conversa, histórico de interações  │
├───────────────────────────────────────────────────────┤
│ CAMADA 2 — Conhecimento de Mercado (atualizado)       │
│ Mudanças Meta, benchmarks BR, tendências, bugs        │
├───────────────────────────────────────────────────────┤
│ CAMADA 1 — Conhecimento Fundacional (estável)         │
│ Conceitos, estrutura, boas práticas permanentes       │
└───────────────────────────────────────────────────────┘
```

### Camada 1 — Fundacional (estável)

| Tema | Conteúdo |
|------|----------|
| Leilão Meta Ads | Bid × relevance × estimated action rate |
| Objetivos de campanha | Awareness, Traffic, Engagement, Leads, Sales |
| Estrutura de conta | Campanha → Ad Set → Ad |
| Tipos de público | Broad, Interest, Custom, Lookalike |
| Funis de venda | Topo, meio, fundo |
| Métricas | CPM, CPC, CTR, CPA, ROAS, Frequência |
| Formatos de anúncio | Imagem, vídeo, carrossel, stories, reels |
| Regras de aprovação | O que reprova, o que toma ban |
| Copy para ads | Hook, corpo, CTA |
| Psicologia de vendas | Urgência, prova social, escassez |

**Formato:** Documentos markdown, 1 por tema
**Atualização:** Revisão manual a cada 3-6 meses

### Camada 2 — Mercado (dinâmica)

| Conteúdo | Frequência |
|----------|------------|
| Mudanças na plataforma Meta | A cada update |
| Benchmarks por nicho/região BR | Trimestral |
| Novas features Meta | Quando lança |
| Mudanças de política | Quando acontece |
| Tendências de criativo | Mensal |
| Datas sazonais BR | Anual |
| Bugs conhecidos | Tempo real |

**Formato:** Documentos markdown versionados com metadata (data, fonte, confiança)
**Atualização:** Pipeline semi-automático (fontes → IA classifica → curadoria → publica)

### Camada 3 — Contexto do Usuário (por sessão)

- Perfil do negócio (coletado no onboarding)
- Histórico de conversas
- Recomendações anteriores
- Dados reais (quando conectado — Fase 7)

### Pipeline de Atualização

```
FONTES                          PROCESSAMENTO                    DESTINO
─────                           ─────────────                    ───────
Meta Blog oficial          ─┐
Meta API Changelog         ─┤   Coleta (RSS/scraping/webhooks)
Comunidades BR ads         ─┼─→ IA classifica relevância       ─→ Knowledge Base
Referências BR (Sobral...) ─┤   IA resume e formata               (Vector DB)
Benchmarks (Revealbot...)  ─┤   Revisão humana (se necessário)  ─→ Re-indexação
Dados internos agregados   ─┘   Publica + versiona                 (embeddings)
```

### Fontes de Informação

| Fonte | Tipo | Captura |
|-------|------|---------|
| Meta for Business Blog | Oficial | RSS semanal |
| Meta Marketing API Changelog | Oficial | Polling diário |
| Meta Business Help Center | Oficial | Scraping mensal |
| Comunidades BR gestores de tráfego | Informal | Curadoria manual |
| Referências internacionais (Jon Loomer) | Expert | RSS |
| Referências BR (Sobral, Tessmann) | Expert | YouTube summaries |
| Dados agregados dos nossos usuários | Proprietário | Analytics interno |
| Benchmarks (Revealbot, Databox) | Dados | Scraping trimestral |

### Stack Técnica da Knowledge Base

| Componente | Escolha | Motivo |
|------------|---------|--------|
| Vector DB | Supabase pgvector | Simples, barato, unifica auth+db+vectors |
| Embeddings | OpenAI text-embedding-3-small | $0.02/1M tokens, qualidade suficiente |
| Chunking | Por seção temática | Cada chunk = unidade de conhecimento completa |
| Atualização | Streaming (crítico) + batch semanal (resto) | Frescor sem custo excessivo |
| Versionamento | Git (docs) + timestamp (vector DB) | Rollback, histórico |
| Staleness | 90 dias → flag automático | Garante revisão periódica |

### Ciclo de Vida de Documentos

```
CRIAÇÃO → REVISÃO → PUBLICAÇÃO → USO → ENVELHECIMENTO → ATUALIZAÇÃO ou REMOÇÃO

Metadata por documento:
- id, título, tema, camada (1 ou 2)
- data_criação, data_última_revisão
- fonte (URL ou "interno")
- confiança (alta/média/baixa)
- expira_em (data para flag de revisão)
- versão
```

### Plano de Execução — Fase 1

| Passo | Ação | Tempo |
|-------|------|-------|
| 1.1 | Escrever 20-30 docs da Camada 1 (fundamentos) | 1-2 semanas |
| 1.2 | Configurar Supabase + pgvector | 1 dia |
| 1.3 | Criar pipeline de embedding (docs → chunks → vectors) | 2-3 dias |
| 1.4 | Escrever system prompt do agent | 1-2 dias |
| 1.5 | Testar RAG: pergunta → retrieval → resposta qualificada | 1 semana |
| 1.6 | Adicionar 10-15 docs da Camada 2 (mercado atual) | 1 semana |
| 1.7 | Montar pipeline de ingestão semi-automático | 2 semanas |
| 1.8 | QA: testar com perguntas reais de vendedores BR | 1 semana |

**Tempo total estimado Fase 1: 6-8 semanas**

---

## Ciclo de Valor: Análise → Ação

| A IA descobre... | Então ela pode criar... |
|------------------|------------------------|
| Top ad target mulheres 25-34 em SP | Sugestão de lookalike audience |
| CTR alto mas conversão baixa | Recomendação de mudar destino/oferta |
| Criativo com hook de pergunta performa melhor | Draft de novo ad com mesmo padrão |
| 70% do budget num ad com ROAS 0.3x | Recomendação de pausar e realocar |
| Audiência engaja mais terça 19-21h | Scheduling recommendation |

### Ciclo completo:
```
Analisar → Recomendar → Gerar (copy/brief/plano) → Publicar (com aprovação)
```

---

## Próximos Passos Imediatos

- [ ] Definir estrutura dos documentos da Camada 1 (template)
- [ ] Listar os 20-30 temas prioritários
- [ ] Escrever os primeiros 5 docs como piloto
- [ ] Setup Supabase + pgvector
- [ ] Prototipar RAG básico com Claude API
- [ ] Testar qualidade das respostas

---

## Referências de Mercado

- **Inflowave** — MCP com 266 tools, CRM completo, foco em agencies. Nosso diferencial: foco no vendedor pequeno BR.
- **ManyChat** — DM automation limitada. Não faz ads.
- **Meta Ads Manager** — Dashboard complexo. Nosso diferencial: simplificar em conversa.

---

*Documento vivo. Atualizar conforme decisões são tomadas em cada fase.*
*Criado em: 07/07/2026*
