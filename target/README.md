# 📚 Sistema de Gestão Acadêmica (SGA)

Este projeto consiste no desenvolvimento do **Backend de um Sistema de Gestão Acadêmica (SGA)**, criado como parte de uma Atividade Prática Supervisionada (APS).
O sistema fornece uma **API REST** para gerenciar **Cursos** e **Alunos**, servindo como base para futuras aplicações web ou mobile.

---

## 🎯 Missão do Projeto

Modernizar a gestão escolar por meio de uma API profissional, utilizando tecnologias amplamente adotadas no mercado de trabalho, como **Java**, **Spring Boot** e **Banco de Dados Relacional**.

> ⚠️ Este projeto **não possui frontend**. Toda a interação é feita via requisições HTTP (Postman ou Insomnia).

---

## 🛠️ Tecnologias Utilizadas

- **Java**: JDK 17+
- **Spring Boot**: 3.x
- **Spring Data JPA**
- **Banco de Dados**: H2 (em memória)
- **Maven**: Gerenciador de dependências
- **IDE**: VS Code / Eclipse / IntelliJ IDEA
- **Teste de API**: Postman ou Insomnia

---

## 🧩 Estrutura do Projeto

src/main/java/com/example/demo
│
├── controller
│ ├── CursoController.java
│ └── AlunoController.java
│
├── model
│ ├── Curso.java
│ └── Aluno.java
│
├── model/repository
│ ├── CursoRepository.java
│ └── AlunoRepository.java
│
└── DemoApplication.java

---

## 🗃️ Entidades do Sistema

### 📘 Curso

- `id` (Long) — chave primária
- `nome` (String) — obrigatório
- `sigla` (String) — único
- `descricao` (String) — opcional

### 👨‍🎓 Aluno

- `id` (Long) — chave primária
- `nome` (String) — obrigatório
- `matricula` (String) — única
- `email` (String) — formato válido
- `curso` — relacionamento **ManyToOne**

---

## 🔗 Endpoints da API

### 📌 Cursos (`/api/cursos`)

| Método | Endpoint           | Descrição                            |
| ------ | ------------------ | ------------------------------------ |
| POST   | `/api/cursos`      | Cadastrar curso                      |
| GET    | `/api/cursos`      | Listar cursos                        |
| GET    | `/api/cursos/{id}` | Buscar curso por ID                  |
| DELETE | `/api/cursos/{id}` | Remover curso (se não houver alunos) |

---

### 📌 Alunos (`/api/alunos`)

| Método | Endpoint           | Descrição        |
| ------ | ------------------ | ---------------- |
| POST   | `/api/alunos`      | Matricular aluno |
| GET    | `/api/alunos`      | Listar alunos    |
| GET    | `/api/alunos/{id}` | Buscar aluno     |
| PUT    | `/api/alunos/{id}` | Atualizar dados  |
| DELETE | `/api/alunos/{id}` | Remover aluno    |

---

## 🧪 Exemplos de JSON

### ➕ Cadastro de Curso

```json
{
  "nome": "Técnico em Enfermagem",
  "sigla": "ENF",
  "descricao": "Curso focado em saúde e cuidados assistenciais."
}
{
  "nome": "João da Silva",
  "matricula": "2024ENF99",
  "email": "joao.silva@aluno.ce.gov.br",
  "curso": {
    "id": 1
  }
}
spring.datasource.url=jdbc:h2:mem:sga_db
spring.datasource.driverClassName=org.h2.Driver
spring.datasource.username=sa
spring.datasource.password=
spring.jpa.database-platform=org.hibernate.dialect.H2Dialect
spring.h2.console.enabled=true
http://localhost:8080/h2-console
```
