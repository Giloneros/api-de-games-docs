# api-de-games-docs
Está API é utilizada para TAL e TAL...
## Endpoints
### GET /games
Esse endpoint é responssavel por retornar a listagem de todos os games cadastrados no banco de dados
#### Parametros
Nenhum
#### Respostas
##### OK! 200
Caso essa resposta aconteça você vai receber a listagem de todos os games
Exemplo de resposta:

```
[
        {
            id: 23,
            title: "Call of duty MW",
            year: 2019,
            price: 60
        },
        {
            id: 65,
            title: "Sea of thieves",
            year: 2018,
            price: 40
        },
        {
            id: 2,
            title: "Minecraft",
            year: 2012,
            price: 20
        }
    ]
    
    ```
##### Falha na autenticação! 401
Caso essa resposta aconteça, isso significa que aconteceu alguma falha durante o processo de autenticação da requisição. Motivos: Token inválido, Token expirado.

Exemplo de resposta:

```
{
  "err": "Token inválido!"
}
```


### POST /auth
Esse endpoint é responssavel por retornar fazer o processo de login
#### Parametros
email: E-mail do usuário cadastrado no sistema.

password: senha do usuário cadastrado no sistema.

Exemplo:
```
{
  "email": "gilson@gmail.com",
  "password": "nodejs<3"
}
```
#### Respostas
##### OK! 200
Caso essa resposta aconteça você vai receber o token JWT para conseguir acessar endpoints protegidos na API.
Exemplo de resposta:

```
    "token":
    "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6MiwiZW1haWwiOiJKb2FxdWltbWltaUBnbWFpbC5jb20iLCJpYXQiOjE2MTA3MTA2NDIsImV4cCI6MTYxMDg4MzQ0Mn0.52hVZWPNHsL9M8j2sLVtMFXOt1cJFNUy4vnlpwIjXO4"
    
    ```
##### Falha na autenticação! 401
Caso essa resposta aconteça, isso significa que aconteceu alguma falha durante o processo de autenticação da requisição. Motivos: Senha ou email errados.

Exemplo de resposta:

```
{
  "err": "Credenciais inválidas!"
}
```
