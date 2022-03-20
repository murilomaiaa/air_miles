# Air Miles
**Sistema feito para gerenciamento de milhas aéreas**
O usuário irá cadastrar um cartão informando o bandeira (Visa, MaterCard, Elo, etc) e poderá enviar email para todos os donos de uma determinada bandeira.


- [Air Miles](#air-miles)
  - [Sobre o projeto](#sobre-o-projeto)
    - [Tecnologias utilizadas](#tecnologias-utilizadas)
  - [Execução local](#execução-local)
    - [Pré-requisitos](#pré-requisitos)
    - [Executando o projeto](#executando-o-projeto)

---

## Sobre o projeto
Projeto desenvolvido para praticar conceitos de micro serviços. Os micro serviços são
- [Air miles card](https://github.com/murilomaiaa/air_miles_card) 
Api responsável pelo cadastro dos cartões
- [Air miles newsletter](https://github.com/murilomaiaa/air_miles_newsletter) 
Api responsável pelo envio de emails

### Tecnologias utilizadas
- Node + Typescript
- RabbitMq para mensageria
- Jest como ferramenta de testes automatizados
- Eslint para padronizar alguns aspectos do código como aspas simples e ponto-vírgula
- Husky e lint-staged para garantir que o desenvolvedor não suba o código sem executar os testes e lint
- Typeorm para manipulação de banco de dados
- Swagger para documentação

### Pré-requisitos

- [Docker](https://docs.docker.com/get-docker/) e [Docker-Compose](https://docs.docker.com/compose/install/) instalados.

### Executando o projeto

Para executar o projeto, você deverá clonar, entrar na pasta do projeto e executar os serviços utilizando [docker-compose](./docker-compose.yml). Segue exemplo utilizando SSH. Você também pode baixar usando a CLI do github

```sh
git clone git@github.com:murilomaiaa/air_miles.git \ 
  && cd air_miles \
  docker-compose up -d


```
O docker-compose irá iniciar os seguintes serviços
1. Uma instância de RabbitMQ.
2. Banco de dados Postgres para o air_miles_card
3. Redis para fazer rate limiter do air_miles_card
4. air_miles_card.
5. Banco de dados Postgres para o air_miles_newsletter
6. air_miles_newsletter