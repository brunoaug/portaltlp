# Carimbos · Plataforma TLP TRJ

Aplicação web single-file (HTML + CSS + JS puro, sem dependências de build) para consulta, preenchimento e cópia rápida de carimbos operacionais usados no dia a dia do TLP TRJ.

## ✨ O que o sistema faz

- Organiza os carimbos em dois módulos: **CSC / CCI** e **Padrão**.
- Cada carimbo é um cartão com campos editáveis (técnico, ticket, observação, etc.).
- Botão **Copiar** gera o texto final do carimbo (título + campos preenchidos) e copia para a área de transferência com um efeito visual de confirmação.
- Botão **Copiar todos** copia todos os carimbos visíveis (respeitando filtro de busca/categoria) de uma vez, separados por `---`.
- Botão **Limpar** apaga apenas o que foi digitado pelo usuário, preservando textos padrão pré-definidos (ex: textos de abono de SLA, observações fixas).
- Botão **Novo** abre um modal para criar carimbos personalizados (título, categoria, cor e campos livres).
- Busca e filtro por categoria em cada módulo.
- Os dados digitados ficam salvos automaticamente no `localStorage` do navegador (não há backend/servidor).

## 📁 Estrutura do arquivo

Tudo está em um único arquivo HTML (`aa.html`), dividido em três blocos:

- `<style>` — visual da aplicação (tema escuro navy/laranja, inspirado na identidade da Plataforma TLP TRJ).
- corpo HTML — header, página inicial (home), página CSC/CCI, página Padrão, modal de criação e toast de notificação.
- `<script>` — dados dos carimbos (`stampsCSC` e `stampsPadrao`), renderização dos cartões, busca/filtro, cópia para a área de transferência, criação/edição/exclusão e persistência em `localStorage`.

## ▶️ Como usar

1. Baixe o arquivo `aa.html`.
2. Abra-o em qualquer navegador moderno (Chrome, Edge, Firefox) — não precisa de instalação, servidor ou internet (exceto para carregar as fontes do Google Fonts).
3. Escolha o módulo desejado na tela inicial.
4. Preencha os campos do carimbo necessário e clique em **Copiar**.
5. Cole o texto copiado diretamente no chamado/ticket.

## ➕ Adicionando ou editando carimbos

### Pela interface
Use o botão **＋ Novo** dentro de cada módulo para criar um carimbo customizado (título, categoria, cor e campos).

### Direto no código
Os carimbos pré-cadastrados estão nos arrays `stampsCSC` e `stampsPadrao`, dentro da tag `<script>`. Cada item segue o formato:

```js
{
  id: 1,
  title: "TÍTULO DO CARIMBO",
  color: "blue", // azul, amarelo, laranja, verde, roxo, vermelho, escuro
  category: "Categoria",
  fields: [
    { label: "Campo:", value: "" }
  ]
}
```

Para adicionar um novo carimbo fixo, basta incluir um novo objeto na lista correspondente.

## 🎨 Identidade visual

O layout segue a mesma linguagem visual da página principal da Plataforma TLP TRJ: fundo navy escuro, cartões com brilho (glow) e linha de destaque na base, tipografia **Outfit** (títulos), **DM Sans** (textos) e **DM Mono** (campos/dados), com cores de categoria (laranja, azul, verde, roxo, vermelho, âmbar) indicando o tipo de carimbo.

## 👤 Créditos

Desenvolvido por **Bruno Augusto**
📧 bruno.augusto.bafs@gmail.com
