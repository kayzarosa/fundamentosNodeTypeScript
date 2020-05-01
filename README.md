<h1 align="center">
    <img alt="Rocketseat GoStack" src="https://camo.githubusercontent.com/d25397e9df01fe7882dcc1cbc96bdf052ffd7d0c/68747470733a2f2f73746f726167652e676f6f676c65617069732e636f6d2f676f6c64656e2d77696e642f626f6f7463616d702d676f737461636b2f6865616465722d6465736166696f732e706e67" width="100%" />
</h1>

## Rocketseat

# :rocket: Desafio 05: Fundamentos do NodeJS

> TUDO ESTÁ BEM!!!!!.  <img src="https://user-images.githubusercontent.com/20192309/80777643-4202cd80-8b3c-11ea-8f32-5348bda4486b.jpg" width="10%" />

## Sobre o desafio

Nesse desafio aprendemos a trabalhar com TypeScript e a trabalhar com a metodologia SOLID, separando as responsabilidades dentro do código.
Esse desafio consiste em salvar as tramsações financeiras de entra e de saída, aplicando alguams regras de negócio que não permite que nenhuma retirada seja feita se houver saldo suficiente para isso.

![fundamentoNode](https://user-images.githubusercontent.com/20192309/80778057-82af1680-8b3d-11ea-89b6-47809ae88d29.png)

## Versão

<a href="https://nodejs.org/pt/"> NodeJS 12.16.2 </a>

## Instalação

````sh
yarn
````

## Iniciar uma API

````sh
yarn dev
````

## Usando a API

Adicionar uma nova transação financeira com método POST, chame a URL http://localhost:3333/transactions/ no <a href="https://www.postman.com/downloads/">Postman</a>, no <a href="https://insomnia.rest/download/>Insomnia</a> ou na sua aplicação e informe o corpo da requisição:

Corpo da requisição:

Utilizando type como "income" para entradas e "outcome" para saídas de dinheiro

JSON

````sh
{
  "title": "Salario",
  "value": 3000,
  "type": "income"
}
````

Ele retorna todos os projetos cadastrados e o que acabou de ser cadastrado:

JSON

````sh
{
    "id": "2c53e878-5b27-41a6-b36f-68d84fa56825",
    "title": "Salario",
    "value": 3000,
    "type": "income"
}
````

Buscando as transações registrados, e o balance chame o método GET, chame um URL http://localhost:3333/transactions/

Ele retorna todas as transações e o balanço de entrada, saída e total cadastrados:

JSON

````sh
{
    "transactions": [
        {
            "id": "93c00e7b-5d6f-4ee1-8331-3a671603f73a",
            "title": "Salario",
            "value": 3000,
            "type": "income"
        },
        {
            "id": "f8369c3c-9cfc-4363-91cb-c31da1c41975",
            "title": "Aluguel",
            "value": 1000,
            "type": "outcome"
        }
    ],
    "balance": {
        "income": 3000,
        "outcome": 1000,
        "total": 2000
    }
}
````
Caso o usuário informe qualquer type diferente de "income" e "outcome" ele retornará o seguinte erro:

````sh
{
    "error": "Transaction type is invalid"
}
````

Se o total de saída "outcome" informado for maior que o saldo ele retornará a seguinte mensagem de erro:


````sh
{
    "error": "You do not have enough balance"
}
````

Feito com ♥ by Kayza :wave:
