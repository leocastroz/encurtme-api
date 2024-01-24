<p align="center"><a href="https://laravel.com" target="_blank"><img src="https://raw.githubusercontent.com/laravel/art/master/logo-lockup/5%20SVG/2%20CMYK/1%20Full%20Color/laravel-logolockup-cmyk-red.svg" width="400" alt="Laravel Logo"></a></p>

<p align="center">
<a href="https://github.com/laravel/framework/actions"><img src="https://github.com/laravel/framework/workflows/tests/badge.svg" alt="Build Status"></a>
<a href="https://packagist.org/packages/laravel/framework"><img src="https://img.shields.io/packagist/dt/laravel/framework" alt="Total Downloads"></a>
<a href="https://packagist.org/packages/laravel/framework"><img src="https://img.shields.io/packagist/v/laravel/framework" alt="Latest Stable Version"></a>
<a href="https://packagist.org/packages/laravel/framework"><img src="https://img.shields.io/packagist/l/laravel/framework" alt="License"></a>
</p>

## UTILIZANDO O PROJETO

#### composer version 2.6.6
#### PHP 8.3.2


- Ter o Largon + PHPAdmin instalado no `disco:C`
- Clone o projeto dentro do Laragon em `C:\laragon\www`

##### Clone SSH
```sh
git@github.com:leocastroz/encurtme-api.git
```

- Utilize o terminal do Laragon e roda o comando `cp .env.example .env`.
- Logo após utilize `composer install`, para instalar os pacotes.
- Depois vamos utilizar o comando `php artisan jwt:secret`, para gerar a chave do pacote JWT.
##### ex:
```sh
JWT_SECRET=YOU_SECRET_JWT
```
- Depois utilize o comando `php artisan key:generate`, para gerar a chave do APP_KEY.
##### ex:
```sh
APP_KEY=YOU_KEY
```
- Utilize `php artisan serve`, para conferir se está tudo OK!.

#### Para meu back-end, tive por preferência popular meus dados com seeders..
- Neste caso utilizei `php artisan migrate`, para gerar minha tabela.
- E logo após em `database>seeders>DatabaseSeeder`, descomentei o campo `\App\Models\User::factory(10)->create();`, para gerar minhas migrations.
- Utilize o comando `php artisan migrate:fresh --seed`, para gerar os dados dos usuários.

##### Para esta migration, o padrão de senha do usuário será `senha="password"`. Para todos os migrations registrados.
</br>

#### Por padrão, o projeto já está auto-configurado para `localhost`, caso queira utilizar `MySQL`.
- Para testar minhas rotas, utilizei o <a href="https://www.postman.com/downloads/">Postman</a>, utilizei o método `POST` para rota `http://127.0.0.1:8000/api/login`.


### POST 

`(POST)=http://127.0.0.1:8000/api/login`

##### envio:
```sh
{
    "email": "oturcotte@example.net",
    "password": "password"
}

```

##### retorno:
```sh
{
    "access_token": "eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJpc3MiOiJodHRwOi8vMTI3LjAuMC4xOjgwMDAvYXBpL2xvZ2luIiwiaWF0IjoxNzA2MDc1Mjg2LCJleHAiOjE3MDYwNzg4ODYsIm5iZiI6MTcwNjA3NTI4NiwianRpIjoiQ2FsMFQ3aEdYUXNtZGZSMiIsInN1YiI6IjEiLCJwcnYiOiIyM2JkNWM4OTQ5ZjYwMGFkYjM5ZTcwMWM0MDA4NzJkYjdhNTk3NmY3In0.dcBEDkPVTR_eJCcgysRYVfpLcQXhkwZesv8hOYJdgSA",
    "token": "eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJpc3MiOiJodHRwOi8vMTI3LjAuMC4xOjgwMDAvYXBpL2xvZ2luIiwiaWF0IjoxNzA2MDc1Mjg2LCJleHAiOjE3MDYwNzg4ODYsIm5iZiI6MTcwNjA3NTI4NiwianRpIjoiQ2FsMFQ3aEdYUXNtZGZSMiIsInN1YiI6IjEiLCJwcnYiOiIyM2JkNWM4OTQ5ZjYwMGFkYjM5ZTcwMWM0MDA4NzJkYjdhNTk3NmY3In0.dcBEDkPVTR_eJCcgysRYVfpLcQXhkwZesv8hOYJdgSA",
    "user": {
        "id": 1,
        "name": "Ms. Clare Heller",
        "email": "oturcotte@example.net",
        "email_verified_at": "2024-01-23T22:17:15.000000Z",
        "created_at": "2024-01-23T22:17:15.000000Z",
        "updated_at": "2024-01-23T22:17:15.000000Z"
    }
}
```

##### errors:
```sh
{
    "message": "The email field is required. (and 1 more error)",
    "errors": {
        "email": [
            "The email field is required."
        ],
        "password": [
            "The password field must be at least 8 characters."
        ]
    }
}
```




