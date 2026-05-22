# 🚀 PROMPT DE EXECUÇÃO: MIAMI DIRECTORY

## 📋 IDENTIFICAÇÃO DO PROJETO

**Cidade:** Miami, Florida, USA  
**Domínio:** miami.fond.coffee  
**Template:** ListingHub (Professional)  
**Idiomas:** Inglês (primário) + Espanhol (secundário)  
**Moeda:** USD  
**Timezone:** EST (UTC-5)

---

## 🎯 OBJETIVO

Lançar o Miami Directory em **48 horas** com monetização ativa através de:
- ✅ 500+ Listings de cafés, restaurantes e locais premium
- ✅ 30 artigos SEO otimizados
- ✅ Campanhas de WhatsApp e Email para comercios indexados
- ✅ Pacotes de monetização (Listing Premium + Site One-Page + Chatbot)

---

## 🏗️ CONFIGURAÇÃO TÉCNICA

### Cloudflare
```
Zone ID: [INSERIR_ZONE_ID]
API Token: [INSERIR_TOKEN]
Domínio: miami.fond.coffee
DNS: CNAME para pages.dev
```

### GitHub
```
Repositório: directory-factory/miami
Branch: main
Deploy: Cloudflare Pages (auto)
```

### N8N Workflows
```
Webhook Scrape: https://n8n.techsites.ai/webhook/miami-scrape
Webhook Index: https://n8n.techsites.ai/webhook/miami-index
Webhook Campaign: https://n8n.techsites.ai/webhook/miami-campaign
```

---

## 📊 PIPELINE DE EXECUÇÃO

### DIA 1: SETUP + SCRAPE + INDEX (0-24h)

#### MT-01: Configuração Inicial
```bash
# Criar estrutura de diretórios
/miami
  /content
    /listings
    /blog
  /assets
    /images
  /config
    miami-config.json
```

#### MT-02: Configuração do ListingHub
```json
{
  "city": "Miami",
  "state": "Florida",
  "country": "USA",
  "domain": "miami.fond.coffee",
  "branding": {
    "primaryColor": "#FF6B35",
    "secondaryColor": "#004E89",
    "logo": "/assets/miami-logo.svg",
    "tagline": "Discover Miami's Best Coffee & Dining Spots"
  },
  "languages": ["en", "es"],
  "currency": "USD",
  "timezone": "America/New_York"
}
```

#### MT-03: Scrape de Listings
**Google Places API Query:**
```
- "coffee shop in Miami"
- "cafe in Miami"
- "restaurant in Miami"
- "brunch spot in Miami"
- "bakery in Miami"
```

**Campos obrigatórios por listing:**
- name
- address
- phone
- email (se disponível)
- website
- google_rating
- latitude/longitude
- opening_hours
- photos (mínimo 3)
- description (gerada por AI se necessário)

**Meta:** 500-1000 listings scraped

#### MT-04: Processamento e Enriquecimento
- Validação de dados (phone, email, website)
- Geração de descrições com GPT-4 (para listings sem descrição)
- Categorização automática (Coffee, Restaurant, Bakery, etc.)
- Upload de fotos para Cloudflare Images
- Geocoding e mapa

#### MT-05: Indexação no ListingHub
- Deploy dos listings no directory
- Geração de páginas individuais
- SEO metadata (title, description, schema.org)
- Sitemap.xml update
- Robots.txt configurado

#### MT-06: Conteúdo SEO
**30 artigos otimizados:**
- "Best Coffee Shops in Miami 2024"
- "Top 10 Brunch Spots in Miami Beach"
- "Hidden Gem Cafes in Wynwood"
- "Best Cuban Coffee in Little Havana"
- "Miami's Most Instagram-Worthy Cafes"
- [25 artigos adicionais com keywords long-tail]

**Formato:**
- 800-1200 palavras
- 3-5 imagens
- Internal links para listings
- Schema.org Article markup

---

### DIA 2: CAMPANHAS + MONETIZAÇÃO (24-48h)

#### MT-07: Preparação de Campanhas

**Email Campaign:**
```
Subject: "🎉 Your business is now featured on Miami.fond.coffee!"

Body:
Hi [Business Name],

Great news! We've featured your business on Miami.fond.coffee, 
Miami's premium directory for coffee shops and restaurants.

Your current listing: [LISTING_URL]

Want to stand out even more? Upgrade to Premium:
✅ Featured placement in search results
✅ Priority in "Best of Miami" guides
✅ Custom one-page website
✅ AI chatbot for customer inquiries

Upgrade now: [UPGRADE_LINK]

Best regards,
Miami Fond Team
```

**WhatsApp Campaign (Z-API):**
```
Olá [Business Name]! 👋

Seu negócio está no miami.fond.coffee! ☕

Quer destaque premium?
📍 Featured listing
🌐 Site próprio
🤖 Chatbot IA

Veja: [SHORT_LINK]
```

#### MT-08: Disparo de Campanhas
- **Email:** 500 contatos via Postmark/SMTP
- **WhatsApp:** 500 números via Z-API (lotes de 50/dia para evitar ban)
- **Tracking:** UTM parameters para conversão

#### MT-09: Pacotes de Monetização

**Listing Premium - $49/mês**
- Featured badge
- Top 3 nos resultados de busca
- Analytics dashboard
- Priority support

**Site One-Page - $199 (setup único) + $29/mês**
- Landing page personalizada
- Domain próprio ou subdomínio
- Formulário de contato
- Google Analytics integrado

**Chatbot IA - $99/mês**
- Chatbot no site do cliente
- Responde perguntas sobre menu/horários
- Lead capture para WhatsApp
- Integração Z-API

**Pacote Completo - $199/mês** (save $78)
- Tudo incluído
- Setup gratuito

#### MT-10: Configuração de Pagamentos
- Stripe Checkout configurado
- Webhooks para ativação automática
- Invoice automático via email
- Renewals automáticos

#### MT-11: Validação e QA
- [ ] Testar 20 listings aleatórios
- [ ] Verificar responsividade mobile
- [ ] Validar formulários de contato
- [ ] Testar checkout de pagamento
- [ ] Verificar velocidade (Lighthouse >90)
- [ ] Sitemap submetido ao Google Search Console

---

## 📈 MÉTRICAS DE SUCESSO

### Lançamento (48h)
- ✅ 500+ listings LIVE
- ✅ 30 artigos publicados
- ✅ 500 emails enviados
- ✅ 500 mensagens WhatsApp disparadas
- ✅ Domain DNS configurado
- ✅ SSL ativo

### Semana 1
- 🎯 10 conversões para Listing Premium
- 🎯 3 conversões para Site One-Page
- 🎯 2 conversões para Chatbot
- 🎯 1.000 visitantes únicos
- 🎯 50 leads B2B capturados

### Mês 1
- 🎯 $2.500 MRR
- 🎯 25 clientes Premium ativos
- 🎯 10.000 visitantes/mês
- 🎯 500 listings com dados completos

---

## 🚨 CHECKLIST PRÉ-LANÇAMENTO

**Infraestrutura:**
- [ ] Cloudflare Zone configurado
- [ ] GitHub repo criado
- [ ] Cloudflare Pages conectado
- [ ] N8N workflows ativos
- [ ] GDrive backup configurado

**Conteúdo:**
- [ ] 500+ listings scraped e validados
- [ ] 30 artigos SEO publicados
- [ ] Imagens otimizadas (WebP)
- [ ] Sitemap.xml gerado

**Monetização:**
- [ ] Stripe account configurado
- [ ] Pricing pages criadas
- [ ] Checkout flows testados
- [ ] Email templates prontos
- [ ] WhatsApp templates aprovados

**Campanhas:**
- [ ] Lista de 500 contatos validada
- [ ] Email campaign agendada
- [ ] WhatsApp campaign configurada
- [ ] UTM tracking implementado

**QA:**
- [ ] Mobile responsiveness OK
- [ ] Page speed >90 (Lighthouse)
- [ ] Forms funcionando
- [ ] SSL ativo
- [ ] Analytics integrado

---

## 🔄 AUTOMAÇÃO PÓS-LANÇAMENTO

### Daily (Automático)
- Backup de listings para GDrive
- Monitoramento de uptime (Better Uptime)
- Processamento de novos listings scraped

### Weekly (N8N)
- Report de métricas para Slack
- Novos artigos SEO (5/semana)
- Follow-up com leads não convertidos

### Monthly
- Invoice de renewals
- Report de MRR e churn
- Review de performance por categoria

---

## 📞 CONTATO E SUPORTE

**Para dúvidas técnicas:**
- Slack: #directory-factory
- Email: tech@techsites.ai
- Notion: [Link do projeto]

**Para aprovações:**
- Design: Aprovar logo e cores antes do deploy
- Copy: Revisar email/WhatsApp templates
- Pricing: Confirmar valores dos pacotes

---

## ⚡ COMANDO DE EXECUÇÃO

```bash
# Copie e execute este comando para iniciar o Miami Directory:

CITY=miami \
DOMAIN=miami.fond.coffee \
ZONE_ID=[ZONE_ID] \
TEMPLATE=listinghub \
SCRAPE_TARGET=500 \
ARTICLES=30 \
CAMPAIGN_SIZE=500 \
bash launch-directory.sh
```

---

## 🎯 PRÓXIMOS DIRECTORIES (Fila)

1. **Miami** ← ATUAL (48h)
2. **Austin** (48h)
3. **Portland** (48h)
4. **Seattle** (48h)
5. **San Diego** (48h)

**Cadência:** 1 directory a cada 2 dias = 15 directories/mês

---

**🚀 LET'S LAUNCH MIAMI!**
