# Instruções para Manutenção do Site de Estética Avançada

Este documento descreve as diretrizes que **devem ser seguidas pelo Claude** para manutenção e desenvolvimento do site de Estética Avançada. Todas as instruções aqui definidas são obrigatórias durante o desenvolvimento.

---

## 🧱 Estrutura do Projeto
O projeto segue a seguinte organização de diretórios e arquivos:

```
/
├── index.html
├── /assets
│   ├── /portfolio (imagens de trabalhos realizados)
│   └── imagens do site (JPG, PNG, SVG, WebP)
├── /.claude
│   └── CLAUDE.md (este arquivo)
├── /.gemini
│   └── GEMINI.md (instruções para Gemini)
└── /.github
    └── /workflows (CI/CD)
```

- **HTML** → apenas marcações e estrutura do conteúdo.
- **TailwindCSS via CDN** → estilização aplicada via classes utilitárias e customizações inline quando necessário.
- **JavaScript inline** → funcionalidades interativas dentro do próprio `index.html` (funções simples no `<script>`).
- **/assets** → todas as imagens obrigatoriamente devem ser colocadas aqui.

---

## 🧭 Estrutura de Navegação
O site contém os seguintes itens no menu:
- **Início** (`#inicio`)
- **Serviços** (`#servicos`)
- **Portfólio** (`#portfolio`)
- **Sobre** (`#sobre`)
- **Contato** (`#contato`)

Cada item direciona para sua respectiva seção dentro da página `index.html` utilizando âncoras internas.

---

## 📱 Contato via WhatsApp (Regra Obrigatória)

### ⚠️ Configuração Centralizada
O número de WhatsApp e a mensagem padrão estão centralizados em um único ponto do código JavaScript para facilitar manutenção futura.

Localização: `index.html` (seção `<script>`)
```javascript
const WHATSAPP_CONFIG = {
  number: "5511945575694",
  defaultMessage: "Olá! Gostaria de agendar um horário.",
};
```

**Regras:**
- **NUNCA** altere links de WhatsApp manualmente no HTML
- **SEMPRE** altere apenas o objeto `WHATSAPP_CONFIG`
- Todos os links são atualizados automaticamente via JavaScript
- O formato do link gerado é: `https://wa.me/{number}?text={message}`

### Onde o WhatsApp aparece:
- Menu desktop (botão "Agende já")
- Seção Hero (botão "Agendar Consulta")
- Seção Portfólio (botão "Quero meu resultado")
- Seção Contato (botão "Fale Conosco pelo WhatsApp")
- Botão flutuante fixo (canto inferior direito)

---

## 🎨 Identidade Visual

### Paleta de Cores
- **Rose Gold**: `#b76e79` (cor principal)
- **Rose Gold Hover**: `#a35d68`
- **Soft Pink**: `#fff5f7` (backgrounds suaves)
- **Texto**: `#1f2937` (gray-800)
- **Texto Secundário**: `#4b5563` (gray-600)

### Tipografia
- **Títulos**: "Playfair Display", serif (elegante, serifada)
- **Texto Geral**: "Poppins", sans-serif (limpa, legível)
- Ambas importadas via Google Fonts

### Classes Customizadas
```css
.rose-gold         /* Cor de texto rose gold */
.rose-gold-bg      /* Background rose gold */
.soft-pink-bg      /* Background rosa suave */
.hover-rose        /* Hover com tom mais escuro */
.hover-lift        /* Efeito de elevação ao hover */
.elegant-border    /* Borda sutil rose gold */
.decorative-line   /* Linha decorativa com gradiente */
```

---

## 🛠️ Tecnologias e Boas Práticas

### 🔹 HTML
- Usar estrutura semântica (`header`, `main`, `section`, `footer`)
- Manter organização por seções bem definidas
- Usar comentários HTML para demarcar seções principais
- IDs nas seções principais para navegação por âncoras

### 🔹 TailwindCSS
- **Incluído via CDN**: `https://cdn.tailwindcss.com`
- **Não criar arquivo CSS separado**, usar apenas classes utilitárias
- Customizações de estilo devem ser feitas via `<style>` inline no HTML
- Usar classes responsivas: `sm:`, `md:`, `lg:` para breakpoints
- Preferir classes do Tailwind sobre CSS customizado

### 🔹 JavaScript
- **Código inline** no próprio `index.html` dentro de `<script>`
- Manter funções simples e objetivas
- Usar `addEventListener` quando possível
- `onclick` inline é aceitável para casos muito simples (menu toggle)
- **Configurações globais** (como WhatsApp) devem estar em objetos no topo do script

### 🔹 Assets
- **Organização**:
  - Logo: `/assets/logo-bigger-no-text-transparent-removebg-preview.png`
  - Portfólio: `/assets/portfolio/labial-*.jpeg`
  - Imagens procedimentos: `/assets/portfolio/injetando.jpeg`
- Usar nomes descritivos e consistentes
- Preferir formatos otimizados (WebP, JPEG otimizado)

---

## 📋 Seções do Site

### 1. Hero Section
- Logo centralizado
- Título principal "Dra. Tati Mayumi"
- Subtítulo "Estética Avançada"
- Descrição breve do serviço
- CTA: "Agendar Consulta" (WhatsApp)

### 2. Serviços
**Procedimentos oferecidos:**
- **Botox**: Suavização de rugas e linhas de expressão
- **Preenchimento Labial**: Aumento e modelagem com ácido hialurônico

Cada serviço tem:
- Ícone SVG
- Título
- Descrição
- 3 benefícios principais

### 3. Portfólio
- Grid 2 colunas (desktop) / 1 coluna (mobile)
- Imagens de antes/depois
- Aspecto quadrado (1:1)
- Título do procedimento
- Descrição breve
- Disclaimer: "*Resultados podem variar de acordo com cada pessoa"
- CTA: "Quero meu resultado"

### 4. Sobre
- Título: "Por que nos escolher?"
- Texto institucional
- Foto da Dra. Tati em ação (circular)
- Badge: "10+ Anos" de experiência
- Estatísticas:
  - 10+ Anos de Experiência na Área da Saúde
  - 100% Segurança e Qualidade

### 5. Contato
- **Endereço**: Rua Catiguá, 159 - Tatuapé, São Paulo, SP - CEP 03065-030
- Link para Google Maps
- **Formas de Pagamento**:
  - Cartão de crédito e débito (parcelamento disponível)
  - PIX aceito
  - Logos: Visa, Mastercard
- CTA: "Fale Conosco pelo WhatsApp"

### 6. Footer
- Copyright: "© 2025 Dra. Tati Mayumi. Todos os direitos reservados."

### 7. Botão WhatsApp Flutuante
- Fixo no canto inferior direito
- Ícone do WhatsApp
- Verde característico: `#25d366`
- Efeito de escala ao hover

---

## 🔧 Funcionalidades Implementadas

### Menu Mobile
- Toggle via função `toggleMenu()`
- Exibe/oculta menu com classe `.hidden`
- Menu hambúrguer (3 linhas)

### WhatsApp Automático
- Sistema de atualização automática de links
- Função `updateWhatsAppLinks()` executada no `DOMContentLoaded`
- Todos os links `a[href*="wa.me"]` são atualizados dinamicamente

### Responsividade
- Mobile-first approach
- Breakpoints: `sm:`, `md:`, `lg:`
- Menu mobile para telas < 768px
- Grid adaptativo (1 coluna → 2 colunas)

---

## 🚀 Deploy com GitHub Pages

O deploy é automatizado via GitHub Actions (`.github/workflows/deploy.yml`):

1. **Não modificar** arquivos de workflow
2. Deploy ocorre automaticamente ao fazer push para `main`
3. Site acessível em: **https://dratatimayumi.com** (domínio registrado na Hostinger)
4. GitHub Pages serve a branch `gh-pages` (criada automaticamente pelo workflow)

**Processo:**
```
Push → GitHub Actions → Build dist/ → Deploy gh-pages → Hostinger DNS → Site Live
```

---

## 🚫 Regras de Git

### ✅ O Claude PODE:
- Ler e analisar o repositório
- Sugerir mudanças
- Modificar arquivos localmente
- Executar `git status`, `git diff`, `git log`

### ❌ O Claude NÃO DEVE (a menos que explicitamente solicitado):
- **Fazer commits** sem permissão explícita do usuário
- Fazer push para repositório remoto
- Modificar configurações do Git
- Executar comandos destrutivos (`reset --hard`, `push --force`)

**Regra de Commits:**
- Apenas criar commits quando o usuário **explicitamente solicitar**
- Sempre mostrar `git status` e `git diff` antes de commitar
- Mensagens de commit devem ser claras e descritivas
- Incluir: `🤖 Generated with [Claude Code](https://claude.com/claude-code)`

---

## 📝 Padrões de Código

### HTML
- Indentação: 2 espaços
- Atributos entre aspas duplas
- Classes ordenadas: layout → espaçamento → cores → tipografia → efeitos

### JavaScript
- Constantes em UPPER_CASE (ex: `WHATSAPP_CONFIG`)
- Funções em camelCase (ex: `updateWhatsAppLinks`)
- Comentários descritivos para blocos lógicos
- Usar `const` por padrão, `let` quando necessário

### Comentários
```html
<!-- Seção Principal -->
<!-- Fim da Seção -->
```

```javascript
// Configuração centralizada do WhatsApp
// Atualiza todos os links de WhatsApp na página
```

---

## 🔄 Manutenção Futura

### Para alterar o número de WhatsApp:
```javascript
const WHATSAPP_CONFIG = {
  number: "5511945575694", // <-- alterar aqui
  defaultMessage: "Olá! Gostaria de agendar um horário.",
};
```

### Para adicionar novo serviço:
1. Copiar estrutura de card existente em `#servicos`
2. Alterar ícone, título, descrição e benefícios
3. Manter classes e estrutura HTML

### Para adicionar imagem ao portfólio:
1. Colocar imagem em `/assets/portfolio/`
2. Copiar estrutura `.before-after-card`
3. Atualizar `src`, `alt`, título e descrição

### Para alterar endereço:
1. Atualizar texto em `#contato`
2. Atualizar link do Google Maps

---

## ✔️ Objetivo Final

Garantir que o site mantenha:
- **Consistência visual** (paleta de cores, tipografia, espaçamentos)
- **Código limpo e organizado** (HTML semântico, classes Tailwind, JS modular)
- **Facilidade de manutenção** (configurações centralizadas, comentários claros)
- **Responsividade** (mobile-first, breakpoints bem definidos)
- **Performance** (CDN, imagens otimizadas, código mínimo)

---

## 📌 Notas Importantes

1. **Este é um site estático de página única (SPA)**
2. **Não há backend** - todo contato via WhatsApp
3. **Não há formulários** que enviem dados para servidor
4. **Foco em conversão** - CTAs estratégicos em todas as seções
5. **Identidade visual elegante** - rose gold, tipografia serifada, espaçamentos generosos

---

**Última atualização:** 2025-11-30

**Instrução Adicional:** Sempre que um novo pedido de mudança for feito, o Claude deve revisar e atualizar estas instruções, se necessário, para garantir que estejam sempre alinhadas com as expectativas do usuário e o estado atual do projeto.
