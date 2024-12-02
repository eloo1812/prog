# Aplicação Web de Cadastro de Produtos - Spring Boot + Thymeleaf

## Descrição

Este é um projeto de exemplo de uma aplicação web utilizando **Spring Boot** para o backend e **Thymeleaf** como template engine para o frontend. A aplicação implementa operações **CRUD** para gerenciamento de produtos, utilizando um banco de dados **MySQL** ou **PostgreSQL**. As entidades são mapeadas com **JPA** e **Hibernate**.

## Funcionalidades

A aplicação permite a criação, leitura, atualização e exclusão de **produtos** no sistema, com as seguintes funcionalidades:

- **Cadastro de Produtos**: Os usuários podem cadastrar produtos com nome e valor.
- **Listagem de Produtos**: Todos os produtos cadastrados podem ser visualizados.
- **Edição de Produtos**: Produtos cadastrados podem ser editados.
- **Exclusão de Produtos**: Produtos podem ser removidos da base de dados.
  
Essas funcionalidades são implementadas como operações CRUD. 

## Operações CRUD

### 1. **Criar Produto (POST)**

O endpoint `POST /products` permite criar um novo produto no sistema. O produto deve ser enviado com o seguinte formato:

- `name`: Nome do produto.
- `value`: Preço do produto.

Exemplo de requisição:

```json
{
  "name": "Produto A",
  "value": 99.99
}
Resposta:

201 Created: Produto criado com sucesso.
2. Listar Produtos (GET)
O endpoint GET /products permite listar todos os produtos cadastrados no sistema. Este endpoint retorna uma lista com os produtos existentes.

Resposta:

json
Copiar código
[
  {
    "idProduct": "UUID do Produto",
    "name": "Produto A",
    "value": 99.99
  },
  {
    "idProduct": "UUID do Produto",
    "name": "Produto B",
    "value": 149.99
  }
]
3. Detalhar Produto (GET)
O endpoint GET /products/{id} permite visualizar os detalhes de um produto específico através do seu idProduct.

Exemplo de requisição: GET /products/abc123

Resposta:

json
Copiar código
{
  "idProduct": "abc123",
  "name": "Produto A",
  "value": 99.99
}
4. Atualizar Produto (PUT)
O endpoint PUT /products/{id} permite atualizar as informações de um produto específico. Para atualizar o produto, basta enviar os novos valores para name e value.

Exemplo de requisição:

json
Copiar código
{
  "name": "Produto Atualizado",
  "value": 129.99
}
Resposta:

200 OK: Produto atualizado com sucesso.
5. Excluir Produto (DELETE)
O endpoint DELETE /products/{id} permite excluir um produto específico. Após a exclusão, o produto será removido permanentemente do banco de dados.

Exemplo de requisição: DELETE /products/abc123

Resposta:

200 OK: Produto deletado com sucesso.
Tecnologias Usadas
Spring Boot (Backend)
Thymeleaf (Frontend)
MySQL ou PostgreSQL (Banco de Dados)
JPA & Hibernate (ORM)
Maven (Gerenciamento de dependências)
Estrutura do Projeto
Camadas do Projeto:
Controladores (Controllers): Responsáveis pelo controle das requisições HTTP e interação com as camadas de serviço e modelo.
Modelos (Models): Representações das entidades do banco de dados.
Repositórios (Repositories): Interfaces responsáveis pela persistência das entidades no banco de dados.
DTOs (Data Transfer Objects): Objetos usados para transferir dados entre a camada de controle e a camada de serviço.
Exemplo de Entidades:
Produto: Entidade que representa um produto no sistema.
idProduto: UUID do produto.
nome: Nome do produto.
valor: Preço do produto.
Configuração do Banco de Dados
MySQL
Crie um banco de dados chamado produtos_db no MySQL.
No arquivo application.properties, defina as configurações de conexão:
properties
Copiar código
spring.datasource.url=jdbc:mysql://localhost:3306/produtos_db
spring.datasource.username=root
spring.datasource.password=senha
spring.jpa.hibernate.ddl-auto=update
spring.datasource.driver-class-name=com.mysql.cj.jdbc.Driver
PostgreSQL
Crie um banco de dados chamado produtos_db no PostgreSQL.
No arquivo application.properties, defina as configurações de conexão:
properties
Copiar código
spring.datasource.url=jdbc:postgresql://localhost:5432/produtos_db
spring.datasource.username=postgres
spring.datasource.password=senha
spring.jpa.hibernate.ddl-auto=update
spring.datasource.driver-class-name=org.postgresql.Driver
Como Rodar o Projeto
Pré-requisitos:
Java 17 ou superior.
Maven 3.6+.
Banco de dados MySQL ou PostgreSQL.
Passos:
Clone o repositório:

bash
Copiar código
git clone https://github.com/eloo1812/prog.git
Acesse o diretório do projeto:

bash
Copiar código
cd prog
Instale as dependências:

bash
Copiar código
mvn install
Execute o servidor:

bash
Copiar código
mvn spring-boot:run
Acesse a aplicação no navegador em:

arduino
Copiar código
http://localhost:8080
Estrutura do Repositório
src/main/java/com/example/springboot/controllers: Contém os controladores, como ProdutoController.
src/main/java/com/example/springboot/models: Contém os modelos de dados, como ProdutoModel.
src/main/java/com/example/springboot/repositories: Contém os repositórios JPA, como ProdutoRepository.
src/main/resources/templates: Contém os templates Thymeleaf para a interface do usuário.
src/main/resources/application.properties: Arquivo de configuração do Spring Boot.
Contribuição
Se você deseja contribuir para este projeto, basta seguir os passos abaixo:

Fork o repositório.
Crie uma branch para sua feature (git checkout -b minha-feature).
Faça suas modificações e commit (git commit -am 'Adiciona nova feature').
Push para a branch (git push origin minha-feature).
Abra um Pull Request.
Licença
Este projeto é licenciado sob a Apache License 2.0.

Referências
Spring Boot Documentation
Thymeleaf Documentation
JPA & Hibernate
