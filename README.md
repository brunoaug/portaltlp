# Plataforma TLP TRJ

Painel central de ferramentas usadas no dia a dia operacional do TLP TRJ. A entrada do sistema é o `index.html`, que reúne os módulos abaixo em um único hub, com identidade visual em tema escuro (navy + laranja).

## 📁 Estrutura do projeto

| Arquivo                  | Módulo                          | Descrição |
|---------------------------|----------------------------------|-----------|
| `index.html`              | **Painel principal**            | Tela inicial com o acesso a todos os módulos da plataforma. |
| `carimbos.html`           | **Carimbos**                    | Consulta, preenchimento e cópia rápida dos carimbos operacionais (CSC/CCI e Padrão). |
| `dashboardsitefora.html`  | **Dashboard Site Fora**         | Monitoramento em tempo real dos sites fora. |
| `extratorbruno.html`      | **Extrator Bruno**              | Planilha/ferramenta de extração de dados desenvolvida pelo Bruno. |
| `extratorfabio.html`      | **Extrator Fabio**              | Extração e processamento de planilhas desenvolvidas pelo Fabio. |
| `puxar_dados.exe`         | **Extrator (executável)**       | Executável para extração automática de dados, disponibilizado para download a partir do painel principal. |
| `tecnicosfixa.html`       | **Técnicos Fixa**                | Área de atuação dos técnicos da rede fixa. |
| `zoe.html`                | **Técnicos Móvel — Zona Oeste** | Visualização dos técnicos da rede móvel atuando na Zona Oeste. |

Cada módulo é um arquivo HTML independente (sem build, sem dependências de servidor), acessado a partir dos cartões do `index.html`.

## ▶️ Como usar

1. Mantenha todos os arquivos na mesma pasta (os links entre as páginas são relativos).
2. Abra o `index.html` em um navegador moderno (Chrome, Edge, Firefox).
3. Escolha o módulo desejado a partir dos cartões da tela inicial.
4. A internet é usada apenas para carregar as fontes do Google Fonts; o restante funciona localmente.

## 🧩 Módulo de Carimbos (`carimbos.html`)

É o módulo com mais lógica própria, por isso vale um detalhamento:

- Organiza os carimbos em dois grupos: **CSC / CCI** e **Padrão**.
- Cada carimbo é um cartão com campos editáveis (técnico, ticket, observação, etc.).
- **Copiar**: gera o texto final do carimbo (título + campos preenchidos) e copia para a área de transferência.
- **Copiar todos**: copia todos os carimbos visíveis (respeitando busca/filtro) de uma vez, separados por `---`.
- **Limpar**: apaga apenas o que foi digitado pelo usuário, preservando textos padrão pré-definidos.
- **＋ Novo**: abre um modal para criar carimbos personalizados (título, categoria, cor e campos livres).
- Busca e filtro por categoria.
- O conteúdo digitado é salvo automaticamente no `localStorage` do navegador (não há backend).

Os carimbos pré-cadastrados estão nos arrays `stampsCSC` e `stampsPadrao`, dentro da `<script>` do arquivo. Para adicionar um novo carimbo fixo, basta incluir um objeto no formato:

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

## 🎨 Identidade visual

Todos os módulos seguem (ou devem seguir) a mesma linguagem visual do `index.html`: fundo navy escuro, cartões com brilho (glow) e linha de destaque na base, tipografia **Outfit** (títulos), **DM Sans** (textos) e **DM Mono** (dados/campos), com cores de categoria (laranja, azul, verde, roxo, vermelho, âmbar) indicando o tipo de conteúdo.

## 👤 Créditos

Desenvolvido por **Bruno Augusto**
📧 bruno.augusto.bafs@gmail.com
