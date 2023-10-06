# API DE GAMES
Esta API é utilizada para teste técnicos e aprendizado


## EndPoints
### GET /games
Esse endpoint é responsável por retornar a listagem de todos os games cadastrados no banco de dados.
#### Parametros
Nenhum
#### Respostas
##### OK ! 200
caso essa resposta aconteça você vai receber a listagem de todos os games
```[
    {
        "id": 23,
        "name": "Fortnite",
        "year": 2013,
        "price": "free"
    },
    {
        "id": 24,
        "name": "Call of Duty",
        "year": 2019,
        "price": 60
    },
    {
        "id": 50,
        "name": "UFC 5",
        "year": 2023,
        "price": 300
    }
]

```
#### Falha na autenticação! 401
Caso essa resposta aconteça, isso significa que aconteceu alguma falha durante o processo de autenticação da requisição. Motivos: Token invalido ou token expirado.
Exemplo de resposta:

```
{
    "error": {
        "name": "JsonWebTokenError",
        "message": "invalid token"
    }
}
```




### POST /auth
Esse endpoint é responsável por fazer o processo de login
#### Parametros
````
{
    "email":"teste@gmail.com",
    "senha":"caique123"
}
`````
#### Respostas
##### OK ! 200

caso essa resposta aconteça você vai um token de acesso.
```{
    "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6MSwiZW1haWwiOiJ0ZXN0ZUBnbWFpbC5jb20iLCJpYXQiOjE2OTY2MjMyOTcsImV4cCI6MTY5NjYzMDQ5N30.L5XeI1tgq5d8D-cuWAaRJc7CeblXjrhqCdX_f_c2CW8"
}
```
#### Falha na autenticação! 404
Caso essa resposta aconteça, isso significa que aconteceu alguma falha durante o processo de autenticação da requisição. Motivos: Email invalido ou senha incorreta
Exemplo de resposta:

```
{
    "message": "erro"
}
```






