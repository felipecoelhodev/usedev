# UseDev | E-commerce

![React](https://img.shields.io/badge/React-19.1.0-blue?logo=react)
![TypeScript](https://img.shields.io/badge/TypeScript-5.8.3-blue?logo=typescript)
![Vite](https://img.shields.io/badge/Vite-6.3.5-purple?logo=vite)
![TailwindCSS](https://img.shields.io/badge/TailwindCSS-4.1.8-38B2AC?logo=tailwind-css)

## Sobre o Projeto

O **UseDev | E-commerce** é um projeto idealizado e feito para fins de estudo, nele foi explorado padrões de composição com custom hooks. Ele simula um e-commerce moderno, responsivo e interativo voltado para o público desenvolvedor e geek. A loja oferece desde roupas temáticas até gadgets e acessórios de tecnologia, com o objetivo de atender paixões e hobbies com muito estilo e autenticidade. 

A aplicação foi construída visando boas práticas de desenvolvimento Frontend, separando responsabilidades através do uso de Context API para gerenciamento de estado global (como o carrinho de compras e listagem de produtos), custom hooks para fetch de dados e buscas de texto, além de Higher-Order Components (HOC) para a manipulação de formulários.

## Funcionalidades

* **Catálogo de Produtos:** Visualização de itens separados por categorias (Roupas, Decoração, Canecas, Acessórios).
* **Busca e Filtros:** Pesquisa interativa por texto (com debounce) e sistema de filtros rápidos por categoria.
* **Página de Detalhes:** Visualização detalhada de cada produto com opções de seleção de tamanho, cor e quantidade.
* **Carrinho de Compras:** Sistema completo de gerenciamento de carrinho, permitindo adicionar itens, remover, alterar quantidades e visualizar subtotal/total dinamicamente.
* **Checkout Simulado:** Fluxo de finalização de pedido que esvazia o carrinho e exibe uma tela de sucesso.
* **Tipografia Customizada:** Estilização baseada em Tailwind CSS utilizando as fontes *Orbitron* (para títulos) e *Poppins* (para textos variados).

## Tecnologias e Ferramentas

O projeto foi desenvolvido com as seguintes tecnologias:

* **[React 19](https://react.dev/):** Biblioteca principal para a construção da interface do usuário.
* **[TypeScript](https://www.typescriptlang.org/):** Tipagem estática para garantir maior segurança e qualidade do código.
* **[Vite](https://vitejs.dev/):** Ferramenta de build rápida e otimizada.
* **[Tailwind CSS (v4)](https://tailwindcss.com/):** Framework de utilitários CSS para estilização rápida e responsiva.
* **[React Router (v7)](https://reactrouter.com/):** Gerenciamento de rotas e navegação SPA (Single Page Application).
* **[JSON-Server](https://github.com/typicode/json-server):** Mock de API RESTful local para simular o banco de dados de produtos e categorias.
* **[Jest & React Testing Library](https://testing-library.com/docs/react-testing-library/intro/):** Suíte de testes unitários e de integração implementada para garantir a estabilidade das funções e do carrinho.
* **[GitHub Actions](https://github.com/features/actions):** Pipeline de CI configurado para rodar o npm install e os testes automatizados a cada `push` de código em ambiente Node.js 20.

## Como Rodar o Projeto Localmente

Siga os passos abaixo para configurar e executar a aplicação na sua máquina:

### Pré-requisitos
* [Node.js](https://nodejs.org/en/) (Versão 20 recomendada conforme o pipeline de CI)
* Gerenciador de pacotes (`npm`, `yarn` ou `pnpm`)

### Passos
1. **Clone o repositório**

```bash
git clone https://github.com/seu-usuario/usedev.git
cd usedev 
```

2. **Instale as dependências**
```bash
npm install
```

3. **Inicie o Servidor Mock (API REST local)**:
   *Isso disponibilizará os produtos na rota `http://localhost:3001`.*
```bash
npm run server 
```

4. **Inicie a Aplicação Web**:
   *Abra um novo terminal (mantendo o servidor mock rodando) e inicie o app React.*
```bash
npm run dev  
```

5. A aplicação estará disponível no seu navegador, geralmente no endereço `http://localhost:5173`.

## Testes Automatizados

O projeto conta com testes unitários focados em contextos utilitários e renderização de componentes críticos (Carrinho, Header, Footer).

Para rodar os testes localmente, execute:
```bash
npm run test
```
A integração contínua (CI) roda automaticamente o comando de testes em um ambiente virtual Ubuntu a cada alteração enviada ao repositório via GitHub Actions.
