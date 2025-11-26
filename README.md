# Site de Estética Avançada

Este projeto visa a criação do site da Dra Tati Mayumi Estética Avançada, seguindo diretrizes específicas de estrutura, tecnologias e boas práticas de desenvolvimento.

## 🚀 Tecnologias Utilizadas

-   **HTML5**: Para a estrutura e marcação semântica do conteúdo.
-   **Tailwind CSS v4.0**: Para estilização, utilizando classes utilitárias e evitando CSS manual.
-   **JavaScript**: Para funcionalidades interativas e comportamentos visuais.

## 🧱 Estrutura do Projeto

A organização dos arquivos e diretórios segue o padrão:

```
/
├── index.html
├── /assets
│   ├── imagens do site (JPG, PNG, SVG, WebP)
├── /js
│   └── main.js (scripts de interação)
```

-   **`index.html`**: Página principal do site.
-   **`/assets`**: Contém todas as imagens do site.
-   **`/css/styles.css`**: Arquivo CSS gerado pelo Tailwind CSS.
-   **`/js/main.js`**: Contém todo o código JavaScript para interatividade.

## 🧭 Navegação

O site inclui os seguintes itens de menu, que devem direcionar para seções específicas na `index.html` via âncoras internas:

-   Início
-   Serviços
-   Portfólio
-   Sobre
-   Contato

## 📱 Contato via WhatsApp

Todos os links e botões de contato devem direcionar para o WhatsApp, utilizando o formato:

```
https://wa.me/SEU_NUMERO?text=MENSAGEM_PADRAO
```

O número deve estar no formato internacional, sem espaços ou símbolos.

## 🛠️ Boas Práticas e Desenvolvimento

### HTML

-   Uso de estrutura semântica (`header`, `main`, `section`, `footer`).
-   Evitar estilos inline.
-   Componentização por seções.

### Tailwind CSS

-   Estilização exclusiva com classes utilitárias.
-   O Tailwind CSS será incluído via CDN diretamente no `index.html`, não sendo necessário um processo de build ou geração de CSS.
-   Configuração via `tailwind.config.js` quando necessário (para customizações específicas, mas não para geração do CSS principal).



### JavaScript

-   Funções no arquivo `/js/main.js`.
-   Separação completa de responsabilidades (sem lógica JS no HTML).
-   Uso de `addEventListener`.

### Assets

-   Todas as imagens em `/assets`.
-   Nomes de arquivos descritivos.

## 🔧 Funcionalidades Esperadas

O site pode incluir funcionalidades como:

-   Menu mobile responsivo.
-   Sliders/carrosséis.
-   Animações simples.
-   Formulário de contato que abre o WhatsApp.
-   Galeria de portfólio.

## 🚀 Deploy com GitHub Pages (SPA)

O deploy é configurado para GitHub Pages como um Single-Page Application (SPA) via GitHub Actions (`.github/workflows/deploy.yml`). O workflow:

1.  Instala dependências (se houver).
2.  Copia `index.html`, `assets/` e `js/` para `dist/`.
3.  Publica o conteúdo de `dist/` no GitHub Pages.
