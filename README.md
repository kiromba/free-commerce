# Projeto Free-Commerce

Free-commerce é um projeto de e-commerce para ajudar iniciantes a aprender Ruby On Rails.

### Sobre este projeto

- loja de produtos
- carrinho de compras
- admnistração de produtos e pedidos
- relatório de vendas


## Desenvolvendo!

### Instalando ferramentas
Veja [DOCKER.md](DOCKER.md) para entender como usar Docker em seu ambiente de desenvolvimento.

Eu recomendo fortemente que você use Docker, mas caso não queira, precisará instalar as seguintes ferramentas
You need Ruby, bundler, node.js, yarn, postgres, and chromedriver.

**Ruby**

1. Instale: [rvm](https://rvm.io/) ou [rbenv](https://github.com/rbenv/rbenv).
1. Quando estiver no diretório do projeto, instale a versão 2.6 our superior.
1. `gem install bundler`

**node.js**

1. (Recomendado) Instale [nvm](https://github.com/nvm-sh/nvm#installing-and-updating), que é um **n**ode **v**ersion **m**anager.
1. Instale uma versão atual do Node
1. Instale [yarn](https://classic.yarnpkg.com/en/docs/install). No Ubuntu, [instale do repositório oficial](https://classic.yarnpkg.com/en/docs/install/#debian-stable).

**PostgreSQL ("postgres")**

1. Confirmando a instalação:
  - No Mac, você pode usar [brew install postgres](https://wiki.postgresql.org/wiki/Homebrew) OU brew postgresql-upgrade-database se você tiver uma versão antiga já instalada.
  - Se estiver no Ubuntu, use `sudo apt-get install libpq-dev` para poder instalar a gem.

### Rodando o app

(*no Mac ou Linux*)

1. `git clone https://github.com/kiromba/free-commerce.git` clone o repositório.
1. `cd free-commerce/`
1. `bundle install`
1. `yarn install`
1. `bin/rails db:setup`

**Rodando o servidor**

1. `bin/rails server` run server
