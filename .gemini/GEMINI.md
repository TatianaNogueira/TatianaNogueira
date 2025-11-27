# Instruções para Construção do Site de Estética Avançada

Este documento descreve as diretrizes que **devem ser seguidas pelo Gemini** para implementar o site de Estética Avançada. Todas as instruções aqui definidas são obrigatórias durante o desenvolvimento.

---

## 🧱 Estrutura do Projeto
O projeto deve seguir a seguinte organização de diretórios e arquivos:

```
/
├── index.html
├── /assets
│   ├── imagens do site (JPG, PNG, SVG, WebP)
├── /js
│   └── main.js (scripts de interação)
```

- **HTML** → apenas marcações e estrutura do conteúdo.
- **TailwindCSS** → estilização aplicada via classes e customizações quando necessário.
- **JavaScript** → funcionalidades interativas e comportamentos visuais (menus, sliders etc.).
- **/assets** → todas as imagens obrigatoriamente devem ser colocadas aqui.

---

## 🧭 Estrutura de Navegação
O site deve conter os seguintes itens no menu:
- **Início**
- **Serviços**
- **Portfólio**
- **Sobre**
- **Contato**

Cada item deve direcionar para sua respectiva seção dentro da página `index.html` utilizando âncoras internas (ex: `#servicos`).

---

## 📱 Contato via WhatsApp (Regra Obrigatória)
O item **Contato**, presente tanto no menu quanto no rodapé ou botões adicionais, deve **sempre** direcionar para o WhatsApp.

Formato do link:
```
https://wa.me/SEU_NUMERO?text=MENSAGEM_PADRAO
```

- O número deve estar no formato internacional, sem espaços nem símbolos.
- Podem existir múltiplos botões, mas todos **devem usar este formato**.

---

## 🛠️ Tecnologias e Boas Práticas

### 🔹 HTML
- Usar estrutura semântica (`header`, `main`, `section`, `footer`).
- Evitar estilos inline.
- Componentizar por seções organizadas.

### 🔹 TailwindCSS
- **Não escrever CSS manual**, exceto em casos muito específicos.
- Estilizar tudo com classes utilitárias.
- O Tailwind CSS será incluído via CDN diretamente no `index.html`, não sendo necessário um processo de build ou geração de CSS.
- Configurar Tailwind via arquivo `tailwind.config.js` quando necessário (para customizações específicas, mas não para geração do CSS principal).



### 🔹 JavaScript
- Funções devem ficar no arquivo `/js/main.js`.
- Separação completa de responsabilidades: nenhuma lógica JS dentro dos arquivos HTML.
- Usar `addEventListener`, evitando atributos como `onclick`.

### 🔹 Assets
- Todas as imagens obrigatoriamente em `/assets`.
- Usar nomes descritivos: `banner-principal.webp`, `logo.svg`, `procedimento-laser.jpg`, etc.

---

## 🔧 Funcionalidades esperadas
O Gemini poderá implementar funcionalidades como:
- Menu mobile responsivo.
- Sliders/carrosséis.
- Animações simples.
- Formulário de contato **que abre WhatsApp**.
- Galeria de portfólio.

Desde que siga as regras de estrutura e boas práticas acima.

---

## 🚀 Deploy com GitHub Pages (SPA)
O deploy do site é feito para o GitHub Pages e está configurado para funcionar como um Single-Page Application (SPA), acessível através do domínio **https://dratatimayumi.com**, registrado na Hostinger.

O processo é automatizado pelo workflow do GitHub Actions, definido em `.github/workflows/deploy.yml`. As etapas principais são:
1.  Um diretório `dist/` é criado dinamicamente durante a execução do workflow. **Este diretório não existe no repositório**.
2.  Os arquivos essenciais (`index.html`, `assets/`, `js/`) são copiados para o `dist/`.
3.  O conteúdo do `dist/` é publicado no GitHub Pages.

Isso garante que apenas os arquivos necessários sejam servidos, mantendo a integridade da SPA e otimizando a publicação.

---

## 🚫 Regras de Git (Obrigatórias)
O Gemini **NÃO deve**:
- Fazer `git add`, `git commit` ou `git push`.
- Interagir com qualquer repositório remoto.

As modificações devem:
- **Permanecer apenas localmente**.
- Ser aplicadas por mim após revisão manual.

---

## ✔️ Objetivo Final
Garantir que o Gemini implemente o site seguindo boas práticas de desenvolvimento, estrutura organizada e separação de responsabilidades, permitindo que o projeto seja facilmente mantido e publicado posteriormente.

---

Se novas instruções forem necessárias, este arquivo poderá ser atualizado.

---

**Instrução Adicional:** Sempre que um novo pedido de mudança for feito, o Gemini deve revisar e atualizar estas instruções, se necessário, para garantir que estejam sempre alinhadas com as expectativas do usuário.