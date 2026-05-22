# DIRECTORY FACTORY — PROJETO TÉCNICO COMPLETO
## TechSites.ai | Versão 1.0.0 | Maio 2026

---

## 1. VISÃO GERAL

A Directory Factory é uma plataforma de produção em escala de sites Directory/Yellow Pages 100% automatizada, orquestrada pelo painel Metronic, com execução via workflows N8N, hospedagem estática em Cloudflare Pages, versionamento em GitHub e backup em Google Drive.

**Stack Principal (obrigatório):**
- Cloudflare Pages (hosting estático + CDN global)
- GitHub (versionamento, CI/CD via Actions)
- Google Drive (backup de assets, configs, exports)
- N8N (orquestração de workflows, motor de automação)
- Metronic (painel admin — cockpit de controle)
- ListingHub (template matriz dos directories)

**Stack Secundário (somente quando stack principal não atender):**
- HostGator VPS + WHM/cPanel (legacy, scraping pesado, exceções)

---

## 2. ARQUITETURA DA FÁBRICA

```
[Metronic Builder Page]
        |
        | POST JSON payload
        v
[N8N Webhook Master]
        |
        |--- [WF-01] Criar Repositório GitHub
        |--- [WF-02] Inicializar Estrutura Padrão
        |--- [WF-03] Configurar Cloudflare (DNS + Pages)
        |--- [WF-04] Customizar ListingHub (branding, nicho)
        |--- [WF-05] Preparar Config JSON do Directory
        |--- [WF-06] Importar Listings (via Scrape Genius CSV)
        |--- [WF-07] Gerar Páginas Estáticas de Listings
        |--- [WF-08] Gerar Blog SEO (SeoContent Engine)
        |--- [WF-09] Injetar Monetização (Ads, Afiliados, Premium)
        |--- [WF-10] Publicar (GitHub Actions → Cloudflare Pages)
        |--- [WF-11] Arquivar no Google Drive
        |
        v
[Directory LIVE em subdomínio]
```

---

## 3. DOMÍNIOS E LINHAS COMERCIAIS

| Domínio | Mercado | Idioma | Modelo |
|---------|---------|--------|--------|
| ama.cafe | Rede de cafés - países lusófonos | PT | Directory de cafés por cidade |
| fond.coffee | Rede de cafés - global | EN/Multi | Directory de cafés global |
| places.guide | Yellow Pages global | EN/Multi | Directory cidades do mundo |
| cwb.site | Curitiba verticalizada | PT | Directory local por nicho |
| llc.reviews | Empresas LLC - mercado americano B2B | EN | Directory corporativo USA |
| hho.expert | Produtos tech/saúde (HHO, hidrogênio) | PT/EN | Portal reviews + afiliados |

**Padrão de subdomínios:**
- `cidade.dominio.tld` → ex: `curitiba.ama.cafe`, `london.places.guide`
- `nicho.dominio.tld` → ex: `cafes.cwb.site`, `dentists.llc.reviews`
- `estado.nicho.dominio.tld` → ex: `california.dentists.llc.reviews`

**Hub Global:** Cada rede de domínio terá um hub global (ex: `global.fond.coffee`)

---

## 4. ESTRUTURA DE REPOSITÓRIOS GITHUB

```
github.com/[user]/directory-factory          ← REPOSITÓRIO MASTER DA FÁBRICA
├── _shared/                                  ← Componentes reutilizáveis
│   ├── templates/listinghub/                 ← Template ListingHub base
│   ├── templates/metronic/                   ← Componentes Metronic
│   ├── workflows/n8n/                        ← Todos os workflows N8N (JSON)
│   ├── scripts/                              ← Scripts de build e deploy
│   └── schemas/                              ← Schemas JSON de configuração
├── docs/                                     ← Documentação técnica
├── prompts/                                  ← Prompts de execução padrão
├── DIRECTORY-FACTORY-PROJETO-TECNICO.md
├── DIRECTORY-FACTORY-SYSTEM-PROMPT.md
├── DIRECTORY-FACTORY-CONTINUIDADE.md
└── README.md

github.com/[user]/df-ama-cafe                ← Repositório por domínio-raiz
github.com/[user]/df-fond-coffee
github.com/[user]/df-places-guide
github.com/[user]/df-cwb-site
github.com/[user]/df-llc-reviews
github.com/[user]/df-hho-expert
```

---

## 5. ESTRUTURA PADRÃO DE CADA DIRECTORY

```
df-[dominio]/
├── src/
│   ├── index.html                    ← Homepage do directory
│   ├── listings/                     ← Páginas individuais de listings
│   │   └── [slug]/index.html
│   ├── blog/                         ← Blog SEO
│   │   ├── index.html
│   │   └── [slug]/index.html
│   ├── categories/                   ← Páginas de categoria
│   ├── cities/                       ← Páginas de cidade (se aplicável)
│   ├── assets/
│   │   ├── css/
│   │   ├── js/
│   │   └── img/
│   └── data/
│       ├── listings.json             ← Base de dados dos listings
│       ├── config.json               ← Config do directory
│       └── articles.json             ← Artigos do blog
├── _worker.js                        ← Cloudflare Worker (rotas dinâmicas)
├── wrangler.toml                     ← Config Cloudflare Pages
├── .github/workflows/deploy.yml      ← CI/CD GitHub Actions
└── sitemap.xml
```

---

## 6. MONETIZAÇÃO PADRÃO

Cada directory é configurado com múltiplas camadas de monetização:

1. **Listings Premium** — comerciantes pagam para aparecer em destaque
2. **Google AdSense / Display Ads** — banner ads por tráfego
3. **Afiliados Amazon** — artigos review com links de afiliado
4. **Afiliados Locais** — parcerias com negócios locais
5. **Posts Patrocinados** — reviews pagas de estabelecimentos
6. **SaaS Whitelabel** — venda de directories personalizados a clientes
7. **Restro SaaS** — integração de pedidos via WhatsApp para restaurantes/cafés
8. **Lead Generation** — venda de leads coletados pelo Scrape Genius

---

## 7. SEO CONTENT ENGINE

Cada directory terá blog estruturado com 3 tipos de conteúdo:

| Tipo | Objetivo | Frequência |
|------|----------|------------|
| Posts Informativos | Tráfego orgânico long-tail | Diário (N8N auto) |
| Reviews Amazon | Afiliados + tráfego comprador | Semanal |
| Reviews Locais Premium | Monetização B2B + tráfego local | Sob demanda |

**Schema obrigatório em todos os posts:** Article, BreadcrumbList, FAQPage
**Internal linking:** automático via N8N ao gerar cada post
**Sitemap:** gerado e submetido automaticamente após cada deploy

---

## 8. MICRO TAREFAS END-TO-END

| ID | Tarefa | Workflow N8N | Input | Output |
|----|--------|-------------|-------|--------|
| MT-01 | Criar repo GitHub | WF-01 | payload JSON | repo_url |
| MT-02 | Inicializar estrutura | WF-02 | repo_url | branch main pronto |
| MT-03 | Configurar Cloudflare | WF-03 | domain, zone_id | DNS + Pages ativo |
| MT-04 | Customizar ListingHub | WF-04 | config.json | template customizado |
| MT-05 | Preparar config JSON | WF-05 | form payload | config.json no repo |
| MT-06 | Importar Listings | WF-06 | CSV Scrape Genius | listings.json |
| MT-07 | Gerar páginas listings | WF-07 | listings.json | HTML pages |
| MT-08 | Gerar blog SEO | WF-08 | keywords, nicho | artigos HTML |
| MT-09 | Injetar monetização | WF-09 | affiliate_id, ads_id | scripts injetados |
| MT-10 | Publicar | WF-10 | repo_url | URL live |
| MT-11 | Arquivar GDrive | WF-11 | assets | backup confirmado |

---

## 9. PAINEL METRONIC — DIRECTORY BUILDER

**URL:** `/admin/directory-builder`

**Blocos da página:**
1. Identidade do Directory (nome, domínio, subdomínio, nicho, idioma, logo)
2. Listings (quantidade, CSV upload, categorias, fonte de scraping)
3. Conteúdo/Blog (nº artigos informativos, nº reviews Amazon, nº reviews locais)
4. Monetização (ID afiliado Amazon, Google Ads ID, premium pricing)
5. Infraestrutura (GitHub repo, Cloudflare Zone ID, GDrive folder ID)
6. Progresso (barra de progresso por micro tarefa, log em tempo real)

**Fluxo:** Preencher formulário → Validar → Clicar "Construir Directory" → Webhook N8N → Polling de status → Directory LIVE

---

## 10. SEGURANÇA E BACKUP

- Todo asset gerado é commitado no GitHub (histórico completo)
- Após cada build, N8N arquiva configs, workflows e dados no GDrive
- Backups automáticos semanais de todos os `listings.json` e `config.json`
- Variáveis sensíveis (API keys, tokens) armazenadas em GitHub Secrets + Cloudflare Environment Variables
- HostGator VPS usada apenas para: scraping pesado, aplicações que exigem PHP/MySQL, casos legacy

---

*Projeto: Directory Factory | Versão: 1.0.0 | Data: Maio 2026 | TechSites.ai*
