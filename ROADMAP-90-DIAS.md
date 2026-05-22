# DIRECTORY FACTORY — ROADMAP 90 DIAS
## Plano de Execução Completo | TechSites.ai | Maio 2026

---

## 📋 VISÃO GERAL

**Data de Início:** 22 de Maio de 2026  
**Data de Conclusão:** 20 de Agosto de 2026  
**Objetivo:** Lançar a Directory Factory operacional com 5 directories LIVE e receita recorrente de $2.000-$5.000/mês

**Investimento Total Estimado:** $3.000-$5.000  
**ROI Esperado em 12 meses:** 300-500%  
**Break-even:** 4-6 meses

---

## 🎯 MARCOS PRINCIPAIS (MILESTONES)

| Marco | Data Alvo | Status |
|-------|-----------|--------|
| M1: Infraestrutura Completa | 05 Jun 2026 | 🔵 Pendente |
| M2: Directory Piloto LIVE | 19 Jun 2026 | 🔵 Pendente |
| M3: Primeira Receita | 03 Jul 2026 | 🔵 Pendente |
| M4: 5 Directories Operacionais | 31 Jul 2026 | 🔵 Pendente |
| M5: Sistema de Escala Ativo | 20 Ago 2026 | 🔵 Pendente |

---

# 📅 MÊS 1: FUNDAÇÃO (22 Mai - 21 Jun 2026)

## Semana 1-2: Setup de Infraestrutura (22 Mai - 04 Jun)

### 🔧 Tarefas Técnicas

**Dia 1-3: Configuração Inicial**
- [ ] Criar conta Cloudflare (se não tiver)
- [ ] Adicionar todos os domínios (ama.cafe, fond.coffee, places.guide, cwb.site, llc.reviews, hho.expert)
- [ ] Configurar DNS básico de todos os domínios
- [ ] Criar organização GitHub para os repositórios
- [ ] Configurar N8N na VPS (ou Hostinger)
- [ ] Testar conectividade N8N → GitHub API
- [ ] Testar conectividade N8N → Cloudflare API

**Dia 4-7: Implementação do Painel Metronic**
- [ ] Instalar Metronic no ambiente de desenvolvimento
- [ ] Criar página `/admin/directory-builder` conforme blueprint
- [ ] Implementar validação JavaScript dos formulários
- [ ] Implementar função de trigger do webhook N8N
- [ ] Implementar sistema de polling de status
- [ ] Testar toda a interface (mock webhook)

**Dia 8-14: Workflows N8N (MT-01 a MT-11)**
- [ ] WF-01: Criar Repositório GitHub (testar com repo fake)
- [ ] WF-02: Inicializar Estrutura (clonar template base)
- [ ] WF-03: Configurar Cloudflare DNS + Pages
- [ ] WF-04: Customizar ListingHub (branding, cores)
- [ ] WF-05: Gerar config.json validado
- [ ] WF-06: Importar Listings do CSV (integrar Scrape Genius)
- [ ] WF-07: Gerar páginas HTML estáticas dos listings
- [ ] WF-08: Gerar blog SEO (integrar OpenAI ou template)
- [ ] WF-09: Injetar scripts de monetização (AdSense, Amazon)
- [ ] WF-10: Deploy no Cloudflare Pages via GitHub Actions
- [ ] WF-11: Backup no Google Drive

**KPI Semana 1-2:**
- ✅ Todos os workflows N8N funcionando isoladamente
- ✅ Painel Metronic funcional
- ✅ Teste end-to-end com directory fake (`test.fond.coffee`)

---

## Semana 3-4: Directory Piloto (05 Jun - 19 Jun)

### 🚀 Lançamento: `curitiba.ama.cafe`

**Por quê Curitiba?**
- Você conhece o mercado local
- Fácil validar qualidade dos dados
- Network existente para vender listings premium

**Execução:**

**Dia 15-17: Coleta de Dados**
- [ ] Scrape Genius: coletar 200 cafés em Curitiba
- [ ] Validar manualmente os primeiros 20 listings
- [ ] Enriquecer dados: fotos, horários, descrições
- [ ] Criar 3 categorias: Specialty Coffee, Cafeteria, Coffee & Food

**Dia 18-20: Construção do Directory**
- [ ] Acessar Metronic Directory Builder
- [ ] Preencher formulário:
  - Nome: "Guia de Cafés de Curitiba"
  - Domínio: ama.cafe
  - Subdomínio: curitiba
  - Idioma: pt-BR
  - Listings: 200
  - Blog: 30 posts informativos + 10 reviews locais
- [ ] Clicar em "Construir Directory"
- [ ] Acompanhar execução (deve levar ~25 minutos)
- [ ] Verificar `curitiba.ama.cafe` LIVE

**Dia 21-24: Ajustes e Otimização**
- [ ] Revisar SEO on-page de 10 listings
- [ ] Submeter sitemap ao Google Search Console
- [ ] Configurar Google Analytics
- [ ] Adicionar Google AdSense (aprovação pode levar dias)
- [ ] Testar velocidade (PageSpeed Insights)
- [ ] Ajustar imagens (comprimir, lazy load)

**Dia 25-28: Primeira Monetização**
- [ ] Criar pacote "Listing Premium" (R$ 99/mês)
- [ ] Listar benefícios: destaque, badge, fotos extras, link direto
- [ ] Criar página de vendas `/premium`
- [ ] Contatar 20 cafés manualmente (cold outreach)
- [ ] Meta: 2-3 clientes pagantes

**KPI Semana 3-4:**
- ✅ `curitiba.ama.cafe` LIVE e indexado no Google
- ✅ 200 listings ativos
- ✅ 40 artigos de blog publicados
- ✅ Google Analytics instalado
- ✅ 1-3 clientes premium (R$ 99-297/mês)

**Receita Esperada:** R$ 200-500/mês

---

# 📅 MÊS 2: EXPANSÃO (22 Jun - 21 Jul 2026)

## Semana 5-6: Lançar 2 Novos Directories (22 Jun - 05 Jul)

### 🌍 Directory 2: `dubai.fond.coffee`

**Por quê Dubai?**
- Mercado de alto valor (turismo + expats)
- Inglês (amplia alcance)
- Dubai já tem dados do Scrape Genius (conforme projeto)

**Execução (Dia 29-35):**
- [ ] Scrape Genius: 150 coffee shops em Dubai
- [ ] Gerar 50 artigos SEO em inglês
- [ ] Construir via Metronic Builder
- [ ] Configurar monetização: Amazon Affiliates US + AdSense
- [ ] Launch `dubai.fond.coffee`

**KPI:**
- ✅ Directory LIVE em 2 dias
- ✅ 150 listings
- ✅ 50 artigos
- ✅ Configurado para afiliados Amazon

---

### 🇺🇸 Directory 3: `california.llc.reviews`

**Por quê California LLC?**
- Mercado B2B de altíssimo valor
- Dados públicos acessíveis (California Secretary of State)
- Monetização via lead generation

**Execução (Dia 36-42):**
- [ ] Scrape dados públicos de 500 LLCs em California (tech, legal, consulting)
- [ ] Criar 20 artigos review de empresas conhecidas
- [ ] Construir via Metronic Builder
- [ ] Configurar formulário de "Request Quote" (lead gen)
- [ ] Integrar com CRM (enviar leads via N8N)
- [ ] Launch `california.llc.reviews`

**KPI:**
- ✅ 500 listings de empresas
- ✅ 20 artigos
- ✅ Formulário de lead gen ativo
- ✅ Primeiros leads capturados

**Receita Esperada:** $50-$200/mês (venda de leads B2B)

---

## Semana 7-8: Otimização e Primeira Receita Consistente (06 Jul - 19 Jul)

### 💰 Foco: Monetização

**Tarefas:**
- [ ] Revisar performance dos 3 directories no Google Analytics
- [ ] Identificar top 10 páginas com tráfego
- [ ] Otimizar CTAs nessas páginas
- [ ] Implementar Amelia Booking em `curitiba.ama.cafe`
- [ ] Adicionar sistema de reviews (5 estrelas)
- [ ] Criar campanha de email marketing para comerciantes
- [ ] Fazer outreach em 50 estabelecimentos (20 por directory)
- [ ] Meta: 5-10 clientes premium no total

**KPI Semana 7-8:**
- ✅ 3 directories gerando tráfego orgânico (min 500 visitas/mês cada)
- ✅ 5-10 listings premium vendidos (R$ 99-199/mês cada)
- ✅ AdSense aprovado e gerando $10-50/mês
- ✅ Primeiros leads B2B de `llc.reviews`

**Receita Total Mês 2:** R$ 1.000-2.000 + $100-300

---

# 📅 MÊS 3: ESCALA (22 Jul - 20 Ago 2026)

## Semana 9-10: Lançar 2 Directories Finais (22 Jul - 04 Ago)

### 🏙️ Directory 4: `newyork.places.guide`

**Execução:**
- [ ] Scrape 1.000 businesses em NYC (Google Places API)
- [ ] Criar 10 categorias (Restaurants, Hotels, Services, etc)
- [ ] Gerar 100 artigos SEO
- [ ] Launch via Metronic Builder
- [ ] Monetização: AdSense + Booking.com affiliate

---

### ⚙️ Directory 5: `cwb.site` (Yellow Page Curitiba Completo)

**Execução:**
- [ ] Scrape 2.000 empresas em Curitiba (multi-nicho)
- [ ] 20 categorias: Dentistas, Advogados, Barbearias, Restaurantes, etc
- [ ] Gerar 80 artigos
- [ ] Integrar Orbit (sistema de agendamento)
- [ ] Launch `cwb.site`

**KPI:**
- ✅ 5 directories LIVE
- ✅ Total de 4.000+ listings
- ✅ 300+ artigos de blog

---

## Semana 11-12: Automação e Escala (05 Ago - 20 Ago)

### 🤖 Automatizar Operações

**Tarefas:**
- [ ] Criar workflow N8N de atualização automática de listings (weekly)
- [ ] Criar workflow de geração de novos artigos (10 por semana)
- [ ] Implementar sistema de notificações para comerciantes
- [ ] Configurar email marketing automático (welcome, upsell)
- [ ] Criar dashboard de analytics consolidado (todos os directories)
- [ ] Documentar processos para contratar VA (Virtual Assistant)

### 📈 Otimização SEO e Conversão

**Tarefas:**
- [ ] Auditoria SEO completa dos 5 directories
- [ ] Implementar schema markup em 100% das páginas
- [ ] Otimizar internal linking
- [ ] A/B test de CTAs (botões "Claim Listing", "Get Quote")
- [ ] Melhorar velocidade de carregamento (otimizar CSS/JS)
- [ ] Criar backlinks (guest posts, directory submissions)

### 💼 Vendas e Parcerias

**Tarefas:**
- [ ] Contatar 100 estabelecimentos (20 por directory)
- [ ] Criar partnership com agências de marketing local
- [ ] Oferecer pacote "Directory Whitelabel" para agências
- [ ] Lançar programa de afiliados (20% comissão)
- [ ] Meta: 20-30 clientes premium no total

**KPI Semana 11-12:**
- ✅ 20-30 listings premium ativos
- ✅ 2.000+ visitas orgânicas/mês (total)
- ✅ AdSense gerando $100-300/mês
- ✅ Leads B2B gerando $200-500/mês
- ✅ Sistema 80% automatizado

**Receita Total Mês 3:** R$ 3.000-5.000 + $500-1.000

---

# 📊 KPIs CONSOLIDADOS (Por Mês)

## Mês 1 (Fundação)
| Métrica | Meta | Real |
|---------|------|------|
| Directories LIVE | 1 | __ |
| Total Listings | 200 | __ |
| Total Artigos | 40 | __ |
| Tráfego Orgânico | 200-500 visitas | __ |
| Clientes Premium | 1-3 | __ |
| Receita Total | R$ 200-500 | R$ __ |

## Mês 2 (Expansão)
| Métrica | Meta | Real |
|---------|------|------|
| Directories LIVE | 3 | __ |
| Total Listings | 850 | __ |
| Total Artigos | 110 | __ |
| Tráfego Orgânico | 1.500+ visitas | __ |
| Clientes Premium | 5-10 | __ |
| Receita Total | R$ 1.000-2.000 | R$ __ |

## Mês 3 (Escala)
| Métrica | Meta | Real |
|---------|------|------|
| Directories LIVE | 5 | __ |
| Total Listings | 4.000+ | __ |
| Total Artigos | 300+ | __ |
| Tráfego Orgânico | 5.000+ visitas | __ |
| Clientes Premium | 20-30 | __ |
| Receita Total | R$ 3.000-5.000 | R$ __ |

---

# 💰 PROJEÇÃO FINANCEIRA 90 DIAS

## Investimento Inicial

| Item | Custo (USD) | Custo (BRL) |
|------|-------------|-------------|
| Metronic License | $49 | R$ 245 |
| ListingHub Template | $49 | R$ 245 |
| Amelia Booking | $59 | R$ 295 |
| Review System | $29 | R$ 145 |
| Domínios (6x $12/ano) | $72 | R$ 360 |
| Cloudflare Pro (3 meses) | $60 | R$ 300 |
| N8N Hosting (VPS) | $30 | R$ 150 |
| OpenAI API (conteúdo) | $200 | R$ 1.000 |
| Scrape Genius (licença) | $97 | R$ 485 |
| **TOTAL** | **$645** | **R$ 3.225** |

## Receita Projetada

| Fonte | Mês 1 | Mês 2 | Mês 3 | Total 90d |
|-------|-------|-------|-------|----------|
| Listings Premium (BRL) | R$ 300 | R$ 1.200 | R$ 3.000 | R$ 4.500 |
| Google AdSense (USD) | $20 | $100 | $250 | $370 |
| Amazon Affiliates (USD) | $10 | $50 | $150 | $210 |
| Lead Gen B2B (USD) | $0 | $100 | $300 | $400 |
| **TOTAL BRL** | R$ 450 | R$ 2.200 | R$ 6.500 | R$ 9.150 |
| **TOTAL USD** | $30 | $250 | $700 | $980 |

**Receita Total 90 dias:** R$ 9.150 + $980 (~R$ 14.050)  
**Investimento:** R$ 3.225  
**Lucro Líquido:** ~R$ 10.800  
**ROI:** 335%

---

# 🎯 PRIORIDADES SEMANAIS (Checklist)

## Semana 1: Setup
- [ ] Cloudflare configurado
- [ ] GitHub organizacional criado
- [ ] N8N instalado e testado
- [ ] Painel Metronic funcional

## Semana 2: Workflows
- [ ] Todos os 11 workflows N8N testados
- [ ] Teste end-to-end com directory fake

## Semana 3: Piloto
- [ ] `curitiba.ama.cafe` LIVE
- [ ] 200 listings ativos
- [ ] Google Analytics configurado

## Semana 4: Primeira Receita
- [ ] 1-3 clientes premium vendidos
- [ ] AdSense aplicado

## Semana 5-6: Expansão
- [ ] `dubai.fond.coffee` LIVE
- [ ] `california.llc.reviews` LIVE

## Semana 7-8: Monetização
- [ ] 5-10 clientes premium total
- [ ] AdSense aprovado
- [ ] Primeiros leads B2B

## Semana 9-10: Escala
- [ ] 5 directories LIVE
- [ ] 4.000+ listings

## Semana 11-12: Automação
- [ ] Workflows automáticos ativos
- [ ] 20-30 clientes premium
- [ ] R$ 3k-5k MRR

---

# 🚨 RISCOS E MITIGAÇÃO

| Risco | Probabilidade | Impacto | Mitigação |
|-------|--------------|---------|------------|
| N8N workflows falharem | Média | Alto | Sistema de retry + logs detalhados |
| Google não indexar rápido | Média | Médio | Submeter sitemap + criar backlinks |
| Comerciantes não pagarem | Alta | Médio | Trial gratuito 30 dias + cold outreach massivo |
| OpenAI API muito caro | Baixa | Médio | Usar templates + variáveis + caching |
| Cloudflare Pages ter limite | Baixa | Alto | Usar múltiplas contas ou migrar para Vercel |
| Scrape Genius ser bloqueado | Média | Alto | Ter backup manual + API alternativas |

---

# 📞 SUPORTE E REVISÃO

**Revisão Semanal (toda sexta 17h):**
- Revisar KPIs da semana
- Ajustar prioridades da próxima semana
- Resolver blockers técnicos

**Revisão Mensal (último dia do mês):**
- Balanço financeiro completo
- Análise de tráfego e conversão
- Planejamento do mês seguinte

**Contato para dúvidas técnicas:**
- Max Computer (Perplexity)
- Documentação: `github.com/reynaldodallin/directory-factory`

---

*Roadmap 90 Dias: Directory Factory | Versão: 1.0.0 | TechSites.ai | Maio 2026*
*Próxima Revisão: 22 de Agosto de 2026*
