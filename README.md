# UseDev

Loja virtual fictícia de produtos geek e para desenvolvedores. O projeto foi criado para fins de estudo e demonstra uma aplicação React completa com catálogo, filtros, detalhes de produto e carrinho de compras.

## Sobre o projeto

A **UseDev** é uma e-commerce com tema de programação e cultura geek. O catálogo inclui camisetas, canecas, acessórios e itens de decoração com referências ao universo dev — como "Boné 404 Not Found", "Xícara 'Haverá bug'" e "Chaveiro 'Na minha máquina funciona'".

A aplicação consome uma API REST simulada via **json-server** e gerencia o estado global com **React Context API**.

## Funcionalidades

- **Página inicial** — hero, busca por nome, filtro por categoria e grade de produtos
- **Detalhes do produto** — seleção de cor, tamanho e quantidade antes de adicionar ao carrinho
- **Carrinho de compras** — alteração de quantidade, remoção de itens, resumo do pedido e checkout simulado
- **Navegação** — rotas para home, produto, carrinho e página 404
- **Layout responsivo** — interface adaptada para mobile, tablet e desktop com Tailwind CSS

## Tecnologias

| Categoria   | Tecnologia             |
| ----------- | ---------------------- |
| Framework   | React 19               |
| Linguagem   | TypeScript             |
| Build       | Vite 6                 |
| Estilização | Tailwind CSS 4         |
| Roteamento  | React Router 7         |
| API mock    | json-server            |
| Testes      | Jest + Testing Library |
| Lint        | ESLint 9               |

## Pré-requisitos

- [Node.js](https://nodejs.org/) 20 ou superior
- npm

## Instalação e execução

1. Clone o repositório e entre na pasta do projeto:

```bash
git clone <url-do-repositorio>
cd usedev
```

2. Instale as dependências:

```bash
npm install
```

3. Em um terminal, inicie a API mock:

```bash
npm run server
```

A API ficará disponível em `http://localhost:3001`.

4. Em outro terminal, inicie o frontend:

```bash
npm run dev
```

A aplicação ficará disponível em `http://localhost:5173` (porta padrão do Vite).

## Scripts disponíveis

| Comando           | Descrição                                     |
| ----------------- | --------------------------------------------- |
| `npm run dev`     | Inicia o servidor de desenvolvimento Vite     |
| `npm run build`   | Compila TypeScript e gera o build de produção |
| `npm run preview` | Pré-visualiza o build de produção             |
| `npm run server`  | Inicia o json-server na porta 3001            |
| `npm run test`    | Executa os testes com Jest                    |
| `npm run lint`    | Executa o ESLint no projeto                   |

## Rotas

| Rota           | Tela     | Descrição                                  |
| -------------- | -------- | ------------------------------------------ |
| `/`            | Home     | Catálogo com busca e filtros por categoria |
| `/product/:id` | Produto  | Detalhes e adição ao carrinho              |
| `/cart`        | Carrinho | Itens, totais e finalização do pedido      |
| `*`            | NotFound | Página de erro 404                         |

## Estrutura do projeto

```
usedev/
├── public/                  # Arquivos estáticos (imagens de produtos e categorias)
├── src/
│   ├── assets/              # Ícones e logos
│   ├── components/          # Componentes reutilizáveis
│   │   ├── Button/
│   │   ├── Counter/
│   │   ├── Footer/
│   │   ├── Header/
│   │   ├── Input/
│   │   ├── Link/
│   │   ├── ProductCard/
│   │   ├── RadioButton/
│   │   ├── SearchInput/
│   │   └── Selector/
│   ├── context/             # Providers e hooks de estado global
│   │   ├── cart/            # Carrinho de compras
│   │   ├── categories/      # Categorias
│   │   └── products/        # Produtos e produto selecionado
│   ├── routes/              # Configuração de rotas e layout wrapper
│   ├── screens/             # Páginas da aplicação
│   │   ├── Cart/
│   │   ├── Home/
│   │   ├── NotFound/
│   │   └── Product/
│   ├── types/               # Interfaces TypeScript
│   └── utils/               # Funções utilitárias (formatação de preço, totais)
├── server.json              # Dados mock da API (produtos, categorias, carrinho)
├── jest.config.ts           # Configuração do Jest
└── vite.config.ts           # Configuração do Vite
```

## API mock

O arquivo `server.json` expõe os seguintes endpoints via json-server:

| Endpoint            | Descrição                   |
| ------------------- | --------------------------- |
| `GET /products`     | Lista todos os produtos     |
| `GET /products/:id` | Retorna um produto pelo ID  |
| `GET /categories`   | Lista todas as categorias   |
| `GET /cart`         | Carrinho (vazio por padrão) |

### Categorias

- Roupas
- Decoração
- Canecas
- Acessórios

## Estado global

O estado é gerenciado com três contexts aninhados:

- **ProductsContext** — lista de produtos e produto selecionado
- **CategoriesContext** — categorias do catálogo
- **CartContext** — itens do carrinho com funções `addItem`, `removeItem`, `changeQuantity` e `clear`

Hooks disponíveis: `useProducts`, `useCategories` e `useCart`.

## Utilitários

Funções em `src/utils/index.ts`:

- `formatPrice` — formata valores em Real (BRL)
- `calculateTotalPrice` — calcula o total do carrinho
- `calculateTotalPriceWithDiscount` — calcula total com desconto percentual

## Testes

O projeto inclui testes unitários e de componentes:

- `src/components/Header/Header.test.tsx`
- `src/components/Footer/Footer.test.tsx`
- `src/screens/Cart/__tests__/Cart.test.tsx`
- `src/utils/index.test.ts`

Para executar:

```bash
npm test
```

## CI/CD

O workflow `.github/workflows/test.yaml` executa os testes automaticamente em pushes e pull requests para a branch `master`, usando Node.js 20.

## Observações

- Projeto fictício desenvolvido para fins de estudo.
- O checkout do carrinho é simulado (sem integração com gateway de pagamento real).
- O carrinho é mantido apenas em memória — os dados não persistem após recarregar a página.
