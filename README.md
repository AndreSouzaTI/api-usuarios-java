# **API de gerenciamento de usuários**


Este projeto é uma API REST de gerenciamento de usuários, desenvolvida com Java 17 e Spring Boot, seguindo boas práticas de desenvolvimento e arquitetura de software em camadas. A API permite operações CRUD (Create, Read, Update, Delete) para usuários, conectando-se a um banco de dados MySQL.

## **Tabela de Conteúdos**

* Requisitos
* Tecnologias Utilizadas
* Estrutura do Projeto
* Instalação e Configuração
* Execução do Projeto
* Testando a API
  * Criar um novo usuário (POST)
  * Obter todos os usuários (GET)
  * Obter usuário por ID (GET)
  * Atualizar usuário por ID (PUT)
  * Deletar usuário por ID (DELETE)
* Erros e Exceções
* Futuras Melhorias
* Licença

## **Requisitos**

Antes de rodar o projeto, verifique se você possui os seguintes softwares instalados:

* Java 17
* Maven (para gerenciamento de dependências)
* MySQL (para o banco de dados)
* Postman ou cURL (para testar a API, opcional)

## **Tecnologias Utilizadas**

* Java 17 - Linguagem de programação.
* Spring Boot - Framework para construção de aplicações web e API REST.
* Spring Data JPA - Para a interação com o banco de dados.
* MySQL - Banco de dados relacional.
* Hibernate - Implementação de JPA para persistência.
* Lombok (opcional) - Para reduzir o código boilerplate, como getters e setters.
* Maven - Para gerenciamento de dependências.

## **Estrutura do Projeto**

`src/
│
├── main/
│   ├── java/
│   │   └── com/
│   │       └── suaempresa/
│   │           └── usermanagement/
│   │               ├── controller/      # Controladores de requisições
│   │               ├── model/           # Modelos de dados (Entidades)
│   │               ├── repository/      # Repositórios (acesso ao banco de dados)
│   │               ├── service/         # Lógica de negócio
│   │               ├── dto/             # Objetos de transferência de dados (DTO)
│   │               └── exception/       # Exceções personalizadas
│   └── resources/
│       └── application.properties       # Configurações da aplicação`

## **Instalação e Configuração**

### Clone o Repositório

https://github.com/AndreSouzaTI/api-usuarios-java.git

## **Execução do Projeto**

Após a configuração, você pode rodar a aplicação localmente executando o comando:

mvn spring-boot:run

A aplicação estará disponível em: http://localhost:8080

## **Testando a API**

Aqui estão alguns exemplos de como testar a API de gerenciamento de usuários. Você pode usar Postman, cURL, ou qualquer outra ferramenta de sua escolha.

### **1. Criar um novo usuário (POST)**

POST /api/users
Content-Type: application/json

`{
"name": "João Silva",
"email": "joao.silva@example.com"
}`

Resposta (exemplo):

`{
"id": 1,
"name": "João Silva",
"email": "joao.silva@example.com"
}`

### **2. Obter todos os usuários (GET)**

GET /api/users

Resposta(exemplo):

`[
{
"id": 1,
"name": "João Silva",
"email": "joao.silva@example.com"
}
]`

### **3. Obter usuário por ID (GET)**

GET /api/users/1

Resposta(exemplo):

`{
"id": 1,
"name": "João Silva",
"email": "joao.silva@example.com"
}`

### **4. Atualizar usuário por ID (PUT)**

Resposta(exemplo):

`{
"id": 1,
"name": "João Pedro",
"email": "joao.pedro@example.com"
}`

### **5. Deletar usuário por ID (DELETE)**

DELETE /api/users/1

## **Erros e Exceções**

A API lança respostas apropriadas de erro para condições como:

404 Not Found: Quando um usuário não é encontrado.

400 Bad Request: Quando a requisição contém dados inválidos.

500 Internal Server Error: Para erros inesperados no servidor.

Exemplo de erro 404 (usuário não encontrado):

`{
"timestamp": "2024-10-10T12:34:56",
"status": 404,
"error": "Not Found",
"message": "User not found with id: 1",
"path": "/api/users/1"
}`



