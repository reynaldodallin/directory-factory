# Directory Factory
### Fábrica Automatizada de Sites Directory | TechSites.ai

![Version](https://img.shields.io/badge/vers%C3%A3o-1.0.0-blue)
![Stack](https://img.shields.io/badge/stack-Cloudflare%20%2B%20GitHub%20%2B%20N8N-orange)
![Status](https://img.shields.io/badge/status-em%20desenvolvimento-yellow)

---

## O que é a Directory Factory?

A **Directory Factory** é um sistema de produção em escala de sites Directory/Yellow Pages 100% automatizado. Com um único formulário no painel Metronic, você configura e dispara a construção completa de um novo directory em minutos.

**De 0 a directory LIVE em menos de 30 minutos, sem intervenção manual.**

---

## Repositórios do Projeto

| Repositório | Função |
|------------|--------|
| `directory-factory` | Master: documentação, templates, workflows, schemas |
| `df-ama-cafe` | Rede ama.cafe (cafés lusófonos) |
| `df-fond-coffee` | Rede fond.coffee (cafés global) |
| `df-places-guide` | Rede places.guide (yellow pages mundial) |
| `df-cwb-site` | Rede cwb.site (Curitiba verticalizada) |
| `df-llc-reviews` | Rede llc.reviews (empresas LLC USA) |
| `df-hho-expert` | Portal hho.expert (tech/saúde) |

---

## Estrutura deste Repositório

```
directory-factory/
├── DIRECTORY-FACTORY-PROJETO-TECNICO.md   # Arquitetura completa
├── DIRECTORY-FACTORY-SYSTEM-PROMPT.md     # Prompt sistema para o Max
├── DIRECTORY-FACTORY-CONTINUIDADE.md      # Prompt de continuidade
├── README-DIRECTORY-FACTORY.md            # Este arquivo
├── directory-config-schema.json           # Schema JSON do builder
├── _shared/
│   ├── templates/listinghub/              # Template ListingHub customizado
│   ├── templates/metronic/                # Componentes Metronic
│   ├── workflows/n8n/                     # Workflows N8N (WF-01 a WF-11)
│   ├── scripts/                           # Scripts de build e deploy
│   └── schemas/                           # Schemas JSON
├── docs/                                  # Documentação técnica detalhada
└── prompts/                               # Prompts por micro tarefa
    ├── MT-01-criar-repo.md
    ├── MT-02-inicializar-estrutura.md
    ├── MT-03-configurar-cloudflare.md
    ├── MT-04-customizar-listinghub.md
    ├── MT-05-config-json.md
    ├── MT-06-importar-listings.md
    ├── MT-07-gerar-paginas.md
    ├── MT-08-gerar-blog-seo.md
    ├── MT-09-injetar-monetizacao.md
    ├── MT-10-publicar.md
    └── MT-11-arquivar-gdrive.md
```

---

## Stack Tecnológico

### Principal (obrigatório)
| Ferramenta | Função |
|-----------|--------|
| Cloudflare Pages | Hosting estático + CDN global |
| Cloudflare Workers | Lógica dinâmica (rotas, APIs) |
| Cloudflare DNS | Gerenciamento de domínios e subdomínios |
| GitHub | Versionamento + CI/CD (GitHub Actions) |
| Google Drive | Backup de assets, configs, exports |
| N8N | Orquestração de workflows e automação |

### Secundário (somente em exceções)
| Ferramenta | Função |
|-----------|--------|
| HostGator VPS + WHM/cPanel | Scraping pesado, PHP/MySQL, legacy |

### Templates e Ferramentas
| Ferramenta | Função |
|-----------|--------|
| ListingHub (ThemeForest) | Template HTML/Bootstrap 5.3 para directories |
| Metronic (ThemeForest) | Painel admin (Directory Builder) |
| Scrape Genius | Coleta de listings e leads |
| SeoContent | Engine de geração de conteúado SEO |
| Restro SaaS | WhatsApp food ordering (cafés/restaurantes) |

---

## Como Usar o Directory Builder

1. Acesse o painel Metronic em `/admin/directory-builder`
2. Preencha todos os campos dos 6 blocos
3. Clique em **"Construir Directory"**
4. Acompanhe o progresso em tempo real (11 micro tarefas)
5. Receba a URL do directory LIVE ao final

### Campos Obrigatórios
- Nome do directory
- Domínio + subdomínio
- Nicho e idioma
- Número de listings
- Número de artigos
- ID de afiliado Amazon
- Zone ID do Cloudflare
- Repositório GitHub de destino

---

## Dominios e Redes Ativas

| Domínio | Tipo | Mercado | Status |
|---------|------|---------|--------|
| ama.cafe | Directory cafés | Lusófono | Ativo |
| fond.coffee | Directory cafés | Global | Ativo (dubai.fond.coffee live) |
| places.guide | Yellow Pages | Mundial | Planejado |
| cwb.site | Yellow Pages nicho | Curitiba | Ativo |
| llc.reviews | Directory corporativo | USA B2B | Planejado |
| hho.expert | Portal reviews | Tech/Saúde | Planejado |

---

## Monetização por Directory

Cada directory gerado é configurado automaticamente com:

- Listings Premium (comerciantes pagam para aparecer em destaque)
- Google AdSense / Display Advertising
- Afiliados Amazon (artigos review com ID próprio)
- Lead Generation (dados coletados via Scrape Genius)
- Posts Patrocinados (reviews pagas de estabelecimentos)
- Restro SaaS (pedidos via WhatsApp para food & beverage)

---

## Contato e Suporte

**Projeto:** Directory Factory
**Empresa:** TechSites.ai
**Responsável:** Reynaldo Dallin
**Localização:** Curitiba, Paraná, Brasil

---

*Directory Factory v1.0.0 | TechSites.ai | Maio 2026*
*Stack: Cloudflare + GitHub + N8N + Metronic + ListingHub*
