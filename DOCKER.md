# Configuração de ambiente de desenvolvimento usando Docker

## Configuração inicial
Os comandos a seguir devem somente ser usados para a configuração inicial. Quando houver alterações no Dockerfile ou no Gemfile, rode o docker-compose build.
1. Instale [Docker Community Edition](https://docs.docker.com/install/) caso
   ainda não tenha.
3. Clone o repositório: `git clone
   https://github.com/kiromba/free-commerce.git`.
4. Acesse o diretório do projeto: `cd free-commerce`
5. Rode `docker-compose build` para criar as imagens dos serviços.
7. Rode `docker-compose run --rm web rails db:reset` para criar o banco de
   dev e teste, carregar o schema, e rodar o arquivo de seed.
8. Rode `docker-compose up -d` para iniciar todos os serviços.
9. Rode `docker-compose ps` para ver os status do container. Todos devem estar
   com o estado "Up".
10. Acesse http://localhost:3000 para ver a aplicação

## Para o dia-a-dia de desenvolvimento:
1. Rode `docker-compose up -d` para iniciar os serviços.
5. Rode `docker-compose ps` para ver o estado dos containers.
1. Rode `docker-compose stop` para parar todos os serviços.
1. Rode `docker-compose restart web` para reiniciar o serviço web.
1. Rode `docker-compose rm <service>` para remover um container parado.
1. Rode `docker-compose rm -f <service>` para remover a força um servico parado.
1. Rode `docker-compose up -d --force-recreate` para iniciar os serviços com novos
   containers.
1. Rode `docker-compose build web` para criar uma imagem do serviço web.
   Depois de recriar, rode `docker-compose up -d --force-recreate web`.
4. Rode `docker-compose down -v` se quiser parar e remover todos os containers.

### Rodando os comandos
Para poder rodar tasks, rails generators, bundle, etc., é preciso executá-los dentro do container, por exemplo:
```
$ docker-compose exec web rails db:migrate
```

Se o container não estiver rodando ainda, você pode criar um somente para isso, por exemplo:

```
$ docker-compose run --rm web bundle install
```

### Rodando o webpack-dev-server
Para agilizar a compilação dos assets, rode o webpackdev-server em uma janela do terminal separada:

```
$ docker-compose exec web bin/webpack-dev-server
```


### Ver logs
```
$ docker-compose logs -f <service>
```

For example:
```
$ docker-compose logs -f web
```

### Acessando serviços
#### Postgres
```
$ docker-compose exec database psql -h database -Upostgres casa_development
```

#### Console do Rails
```
$ docker-compose exec web rails c
```

## Suite de teste
Rode a suíte de dentro de um container:

```
$ docker-compose exec web rspec spec -fd
```
