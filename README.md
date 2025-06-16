
# Workshop Spring Boot 3 + JPA

Este projeto foi desenvolvido como parte do **curso de Web Services com Spring Boot e JPA / Hibernate**, oferecido pela [DevSuperior](https://devsuperior.com.br) e ministrado pelo Dr. Nelio Alves.

O principal objetivo é apresentar, na prática, os fundamentos do desenvolvimento de aplicações RESTful com Spring Boot, modelagem de dados com JPA/Hibernate, camadas de serviço e repositório, e a persistência de dados com H2 e PostgreSQL.

---

## 🎯 Objetivos do Projeto

- Criar uma API RESTful com Spring Boot 3
- Modelar entidades como `User`, `Order`, `Product`, `Category`, etc.
- Criar relacionamento entre entidades: 1-N, N-N, 1-1
- Implementar as camadas:
  - Resource (Controller)
  - Service
  - Repository
- Persistência de dados com JPA/Hibernate
- Seed do banco de dados com dados de exemplo
- Tratamento robusto de exceções
- Perfis de ambiente (`test`, `dev`, `prod`)
- Deploy opcional com PostgreSQL local ou Heroku

---

## 🧱 Modelo de Domínio

Entidades implementadas:

- `User`
- `Order`
- `Category`
- `Product`
- `OrderItem`
- `Payment`

Relações:

- `User` 1-N `Order`
- `Order` 1-1 `Payment`
- `Product` N-N `Category`
- `Order` N-N `Product` (via `OrderItem`)

---

## 🚀 Tecnologias e Ferramentas

- **Java 17**
- **Spring Boot 3**
- **Spring Web**
- **Spring Data JPA**
- **H2 Database** (perfil de teste)
- **PostgreSQL** (dev/prod)
- **Maven**
- **Heroku (opcional, não utilizei)**

---

## 🔧 Perfis de Ambiente

- **test**: Usa banco em memória (H2)
- **dev**: Usa PostgreSQL local
- **prod**: Preparado para deploy em nuvem (Heroku opcional, não utilizei)

---

## 🛠️ Como Executar Localmente

### 1. Clonar o repositório

```bash
git clone https://github.com/leonardorosario/workshop-springboot3-jpa.git
cd workshop-springboot3-jpa
```

### 2. Definir o perfil ativo

No arquivo `src/main/resources/application.properties`, defina o perfil desejado:

```properties
spring.profiles.active=test
```

> Use `test` para H2 ou `dev` para PostgreSQL local (ver `application-dev.properties`).

### 3. Executar o projeto

```bash
./mvnw spring-boot:run
```

---

## 📦 Exemplos de Dados Povoando o Banco

```json
POST /users

{
  "name": "Bob Brown",
  "email": "bob@gmail.com",
  "phone": "977557755",
  "password": "123456"
}
```

---

## 🧠 Conceitos Abordados

- CRUD completo com Spring Boot
- JPA Repository e consultas
- Injeção de dependências com `@Autowired`
- Mapeamento relacional complexo (chave composta, `@JoinTable`, `@ManyToMany`, `@OneToOne`)
- Exceções customizadas (`ResourceNotFoundException`, `DatabaseException`)
- Formatação de data com `Instant` e padrão ISO 8601
- Camada de serviço com lógica de negócio
- Deploy com Heroku e PostgreSQL (opcional, apenas acompanhei)


---

## 🙋‍♂️ Autor

**Leonardo Teixeira Rosario**  
[GitHub: @leonardorosario](https://github.com/leonardorosario)
