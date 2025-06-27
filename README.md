# AutheticUser – API de Autenticação com JWT

Esta API foi desenvolvida utilizando *Spring Boot* e implementa autenticação baseada em **JWT (JSON Web Token)**. Abaixo estão as instruções para executar o projeto, acessar ferramentas úteis e realizar testes de carga.

---

## ✅ Pré-requisitos

Certifique-se de ter os seguintes itens instalados:

- Java 11 ou superior  
- Maven  
- JMeter (para realizar testes de carga)

---

## 🚀 Executando o projeto

1. Clone o repositório:

   ```bash
   git clone https://github.com/seuusuario/autheticuser.git
   cd autheticuser
Compile o projeto:

bash

mvn clean install
Inicie a aplicação:

bash

mvn spring-boot:run
A aplicação será iniciada e poderá ser acessada em:
👉 http://localhost:8080

📄 Documentação da API (Swagger)
Você pode visualizar e interagir com a documentação da API no Swagger:

👉 http://localhost:8080/swagger-ui/index.html#/Autenticação/login

Para testar a autenticação via Swagger:

Acesse o endpoint POST /auth/login

Utilize o seguinte corpo na requisição:

json

{
  "username": "admin",
  "password": "123456"
}
🗃️ Console do H2
O banco de dados em memória H2 pode ser acessado por meio do console em:

👉 http://localhost:8080/h2-console

Credenciais de acesso:

JDBC URL: jdbc:h2:mem:testdb

Usuário: Adisio

Senha: 123456

🧪 Testes de carga com JMeter
Para simular carga na aplicação utilizando o JMeter, siga os passos:

Crie um novo plano de testes:
File > New

Adicione um Thread Group:
Test Plan > Add > Threads (Users) > Thread Group

Number of Threads (users): 200

Ramp-up period (seconds): 20

Loop Count: 10 (ou marque "Forever" para requisições contínuas)

Adicione uma requisição HTTP:
Thread Group > Add > Sampler > HTTP Request

Name: Login Request

Protocol: http

Server Name or IP: localhost

Port Number: 8080

Method: POST

Path: /auth/login

Configure o corpo da requisição (Body Data):

json

{
  "username": "admin",
  "password": "123456"
}
Adicione o HTTP Header Manager:
Login Request > Add > Config Element > HTTP Header Manager

Name: Content-Type

Value: application/json

Para visualizar os resultados:
Thread Group > Add > Listener > View Results Tree

