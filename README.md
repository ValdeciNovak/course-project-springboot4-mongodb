# Workshop MongoDB com Spring Boot

## Descrição / Sobre o projeto

O projeto tem como foco demonstrar a integração entre Spring Boot e MongoDB, aplicando conceitos de desenvolvimento de APIs REST modernas, como modelagem NoSQL, tratamento de exceções e consultas avançadas.

## Tecnologias utilizadas

- **Linguagens**: Java
- **Frameworks**: Spring Boot
- **Bibliotecas**: Spring Data MongoDB, Spring Web, Spring Boot Starter Data MongoDB
- **Banco de dados**: MongoDB

## Funcionalidades

- Gerenciamento de usuários: CRUD (Criar, Ler, Atualizar, Deletar) de usuários.
- Gerenciamento de posts: CRUD de posts associados a usuários.
- Sistema de comentários: Adicionar comentários aos posts.
- Consultas avançadas: Busca de posts por texto, data, etc.
- Tratamento de exceções: Manipulação de erros com respostas padronizadas.

## Como executar o projeto

### Pré-requisitos

- Java 11 ou superior
- Maven 3.6 ou superior
- MongoDB instalado e rodando localmente (porta padrão 27017)

### Clonar repositório

```bash
git clone https://github.com/ValdeciNovak/workshopmongo.git
cd workshopmongo
```

### Instalar dependências

```bash
mvn clean install
```

### Comando para rodar

```bash
mvn spring-boot:run
```

O aplicativo estará disponível em `http://localhost:8080`.

## Organização de pastas

O projeto segue a estrutura padrão do Spring Boot:

- `src/main/java/com/valdeci/workshopmongo/`: Código fonte principal
  - `config/`: Configurações de inicialização (ex: Instanciação de dados)
  - `domain/`: Entidades do domínio (User, Post)
  - `dto/`: Objetos de transferência de dados (UserDTO, PostDTO, etc.)
  - `repository/`: Interfaces de repositório para acesso ao MongoDB
  - `resources/`: Controladores REST (UserResource, PostResource)
    - `exception/`: Tratamento de exceções
    - `util/`: Utilitários (ex: URL)
  - `services/`: Lógica de negócio (UserService, PostService)
    - `exception/`: Exceções customizadas
- `src/main/resources/`: Recursos estáticos e configurações (application.properties)
- `src/test/`: Testes unitários

## Endpoints principais

| Método | Endpoint | Descrição |
|------|--------|----------|
| GET | `/users` | Lista todos os usuários |
| GET | `/users/{id}` | Busca um usuário pelo ID |
| POST | `/users` | Cria um novo usuário |
| PUT | `/users/{id}` | Atualiza os dados de um usuário |
| DELETE | `/users/{id}` | Remove um usuário |
| GET | `/users/{id}/posts` | Lista os posts de um usuário |
| GET | `/posts/{id}` | Busca um post pelo ID |
| GET | `/posts/titlesearch?text=valor` | Busca posts pelo texto do título. Ex: /posts/titlesearch?text=spring | 
| GET | `/posts/fullsearch` | Busca avançada de posts por texto e intervalo de datas. Ex: /posts/fullsearch?text=mongo&minDate=2023-01-01&maxDate=2024-01-01 | 

## Padrões utilizados

- Arquitetura em camadas: Separação clara entre apresentação (resources), negócio (services), dados (repository) e domínio.
- Padrão DTO: Uso de objetos de transferência para comunicação entre camadas.
- Tratamento de exceções centralizado: Uso de @ControllerAdvice para respostas de erro padronizadas.
- Injeção de dependências: Utilização do Spring IoC para gerenciar dependências.

## Aprendizados

Durante o desenvolvimento deste projeto, aprendi a integrar o Spring Boot com MongoDB, utilizando o Spring Data MongoDB para simplificar o acesso aos dados. Desafios enfrentados incluíram a modelagem de dados NoSQL e a implementação de consultas complexas. Conceitos aplicados: RESTful APIs, injeção de dependências, tratamento de exceções e persistência de dados em bancos NoSQL.

## Autor

- Valdeci Novak Junior
- GitHub: https://github.com/ValdeciNovak
- LinkedIn - https://www.linkedin.com/in/valdecijuniordev/
