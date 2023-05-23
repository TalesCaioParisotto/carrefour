#  API Fluxo Caixa
Este é um projeto de API RESTful de teste de fluco de caixa

## Execução do projeto
Para executar o projeto, é necessário ter o Java 17 e o Maven instalados.

## Como usar
Para usar a API, é necessário ter o Docker e o Docker Compose instalados.
## Clone o repositório:

```
### Execute o comando abaixo para compilar e empacotar o projeto:
```bash
mvn clean package
```
## Execute o docker-compose:
```bash
docker-compose up --build
```
A API estará disponível em http://localhost:8080.

Endpoint de autenticação:
POST /login
```
Body:
{
    "login": "Tales",
    "password": "1234"
}
```

A resposta será um token JWT, que deve ser incluído no header das requisições que exigem autenticação, no formato "Bearer {token}".
## Testes unitários
Para rodar os testes unitários, execute o comando abaixo:

```
mvn test
```
## Desenho Projeto
![image](https://github.com/TalesCaioParisotto/carrefour/assets/129349183/85ab8504-3347-423b-b3fd-8f13c5d31dfc)


## Padrões de microserviço utilizados
* Separação em camadas (Controller, Service e Repository)
* Injeção de dependências com Spring
* Uso de DTOs para transferência de dados entre a API e o banco de dados

## Padrões de projetos utilizados
- `Strategy`: utilizado para implementar diferentes formas de cálculo do saldo diário.
- `Repository`: utilizado para abstrair a camada de acesso ao banco de dados.
- `DTO`: utilizado para transferência de dados entre as camadas.

## Endpoints
- `POST /login`: endpoint para realizar a autenticação de um usuário e gerar um token JWT.
- `POST /lancamentos`: endpoint para adicionar um novo lançamento.
- `GET /lancamentos/{id}`: endpoint para buscar um lançamento por id.
- `GET /lancamentos`: endpoint para listar todos os lançamentos.
- `GET /lancamentos?data={data}`: endpoint para listar todos os lançamentos de uma determinada data.
- `GET /saldo-consolidado/{data}`: endpoint para calcular o saldo diário de uma determinada data.
