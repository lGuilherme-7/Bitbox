# 🍔 BiteBox — Cardápio Digital para Delivery

> Cardápio digital moderno, responsivo e funcional — desenvolvido com HTML, CSS e JavaScript puro, sem dependências externas.

---

## 📋 Sobre o Projeto

O **BiteBox** é um sistema de cardápio digital para delivery com carrinho de compras integrado e finalização de pedido via WhatsApp. Desenvolvido como um único arquivo `index.html`, não requer servidor, framework ou instalação.

---
## 📋 link para acessar 

link: https://lguilherme-7.github.io/Bitbox/

---
## ✨ Funcionalidades

- **Catálogo de produtos** com nome, descrição, preço e imagem
- **Categorias** separadas: Lanches, Pizzas, Bebidas, Sobremesas e Combos
- **Filtro por categoria** com scroll horizontal responsivo
- **Busca em tempo real** por nome e descrição do produto
- **Sistema de favoritos** com persistência no LocalStorage
- **Carrinho de compras** com:
  - Adição e remoção de itens
  - Controle de quantidade por produto
  - Cálculo automático de subtotal, entrega e total
  - Persistência via LocalStorage (carrinho salvo ao fechar o navegador)
- **Finalizar pedido pelo WhatsApp** com mensagem formatada automaticamente
- **Toasts de feedback** para ações do usuário
- **Design responsivo** (mobile first)

---

## 🗂️ Estrutura do Projeto

```
bitebox/
└── index.html        # Aplicação completa (HTML + CSS + JS em um único arquivo)
```

O projeto é intencionalmente um arquivo único para facilitar deploy e distribuição. O código interno está organizado em três blocos bem delimitados por comentários:

| Bloco | Localização | Conteúdo |
|---|---|---|
| HTML | `<body>` | Estrutura e marcação semântica |
| CSS | `<style>` | Estilos, variáveis e responsividade |
| JS | `<script>` | Dados, lógica e interatividade |

---

## 🚀 Como Usar

**1. Clone ou baixe o projeto:**
```bash
git clone https://github.com/seu-usuario/bitebox.git
```

**2. Abra o arquivo no navegador:**
```bash
# Simplesmente abra o arquivo:
open index.html

# Ou com um servidor local (opcional):
npx serve .
```

Não é necessário instalar nada. Funciona offline diretamente no navegador.

---

## ⚙️ Configuração

### Número do WhatsApp

No arquivo `index.html`, localize a função `sendWhatsApp()` e altere a variável `PHONE` para o número real da loja (com DDI + DDD, sem espaços ou caracteres especiais):

```javascript
const PHONE = '5511999990000'; // ← Altere aqui
//            55 = Brasil | 11 = DDD | número
```

### Produtos e Cardápio

Os produtos estão definidos no array `MENU` no bloco `<script>`. Cada item segue esta estrutura:

```javascript
{
  id: 1,                          // ID único (número)
  cat: 'lanches',                 // Categoria: lanches | pizzas | bebidas | sobremesas | combos
  badge: 'Top Venda',             // Badge opcional (string ou omitir)
  name: 'Classic BiteBox Burger', // Nome do produto
  desc: 'Descrição do produto.',  // Descrição curta
  price: 32.90,                   // Preço (número)
  img: 'https://...'              // URL da imagem
}
```

### Taxa de Entrega

Localizar e alterar o valor fixo dentro da função `sendWhatsApp()` e na função `renderDrawer()`:

```javascript
const delivery = 5; // Valor em R$
```

---

## 🎨 Tecnologias

| Tecnologia | Uso |
|---|---|
| HTML5 semântico | Estrutura e acessibilidade |
| CSS3 (variáveis, grid, flexbox) | Layout e design responsivo |
| JavaScript ES6+ | Lógica, DOM e LocalStorage |
| Google Fonts (Syne + DM Sans) | Tipografia |
| Unsplash | Imagens dos produtos |

Sem frameworks, sem bundlers, sem dependências de terceiros.

---

## 📱 Responsividade

| Breakpoint | Layout |
|---|---|
| `> 520px` | Grid com múltiplas colunas, busca no header visível |
| `≤ 520px` | Grid de 2 colunas, busca oculta no header |
| `≤ 360px` | Grid de 1 coluna |

---

## 🔧 Personalização Rápida

**Alterar as cores principais** — edite as variáveis CSS no topo do `<style>`:

```css
:root {
  --brand:       #FF4B1F;  /* Cor primária */
  --brand-dark:  #D93A10;  /* Hover / estados ativos */
  --brand-light: #FFF0EC;  /* Fundo suave da cor primária */
  --bg:          #F5F4F0;  /* Fundo da página */
  --text:        #1A1714;  /* Cor do texto principal */
}
```

**Adicionar nova categoria** — inclua a entrada em `CAT_META` e adicione o botão no HTML:

```javascript
// Em CAT_META no script:
minhas_massas: { label: 'Massas', icon: '🍝' }
```

```html
<!-- No bloco .cats-scroll no HTML: -->
<button class="cat-btn" data-cat="minhas_massas">
  <span class="cat-icon">🍝</span> Massas
</button>
```

---

## 📦 Deploy

Por ser um único arquivo estático, o BiteBox pode ser hospedado em qualquer serviço:

- **GitHub Pages** — basta subir o repositório e ativar Pages
- **Netlify / Vercel** — arrastar a pasta para o dashboard
- **Qualquer hospedagem compartilhada** — upload via FTP

---

## 📄 Licença

Este projeto está sob a licença MIT. Sinta-se livre para usar, modificar e distribuir.

---

Feito com ❤️ e muito sabor.