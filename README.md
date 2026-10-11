# Sistema de Gestão de Notas

Aplicação web para cadastro de alunos, disciplinas e notas, com cálculo de médias e consulta da situação acadêmica. O projeto utiliza Java, Spring Boot, Spring Data JPA e banco H2 local.

## Tecnologias

- Java 17+
- Spring Boot 3
- Maven
- Spring Web e Spring Data JPA
- H2 Database
- HTML, CSS e JavaScript

## Funcionalidades

- Cadastro e exclusão de alunos
- Cadastro e exclusão de disciplinas
- Registro e exclusão de notas de 0 a 10
- Consulta das notas e médias
- Boletim com situação acadêmica
- Persistência em banco H2 local
- API REST para as operações principais

**Regra demonstrativa:** média igual ou superior a 7 = Aprovado; média igual ou superior a 5 e inferior a 7 = Recuperação; média inferior a 5 = Reprovado. Ajuste esses limites conforme as regras da instituição.

## Pré-requisitos

- JDK 17 ou superior
- Maven 3.8+ (ou uma IDE com suporte a projetos Maven)

Confira as instalações:

```bash
java -version
mvn -version
```

## Executar localmente

1. Clone o repositório:

   ```bash
   git clone https://github.com/edvaszzz98-design/gestao2.git
   cd gestao2
   ```

2. Inicie a aplicação:

   ```bash
   mvn spring-boot:run
   ```

3. Abra no navegador: http://localhost:8080

O banco H2 é armazenado localmente. Os arquivos do banco não devem ser enviados ao GitHub.

## Gerar o pacote executável

```bash
mvn clean package
java -jar target/sistema-gestao-notas-1.0.0.jar
```

## API REST

| Método | Endpoint | Finalidade |
|---|---|---|
| GET | `/api/health` | Verificar se a API está ativa |
| GET | `/api/students` | Listar alunos |
| POST | `/api/students` | Cadastrar aluno |
| DELETE | `/api/students/{id}` | Excluir aluno |
| GET | `/api/subjects` | Listar disciplinas |
| POST | `/api/subjects` | Cadastrar disciplina |
| DELETE | `/api/subjects/{id}` | Excluir disciplina |
| GET | `/api/grades` | Listar notas |
| POST | `/api/grades` | Registrar nota |
| DELETE | `/api/grades/{id}` | Excluir nota |
| GET | `/api/students/{id}/summary` | Consultar boletim e médias |

Exemplos de corpos JSON:

```json
{
  "name": "Ana Souza",
  "email": "ana@escola.com"
}
```

```json
{
  "name": "Matemática"
}
```

```json
{
  "studentId": 1,
  "subjectId": 1,
  "score": 8.5
}
```

## Publicar atualizações no GitHub

Se você já clonou o repositório, copie os arquivos atualizados para a pasta local do projeto e execute:

```bash
git status
git add .
git commit -m "docs: preparar projeto para publicação"
git push origin main
```

Se estiver começando do zero, clone o repositório existente antes de copiar os arquivos. Não é necessário executar `git init` em uma pasta que já é um clone.

## Estrutura do projeto

```text
src/
└── main/
    ├── java/br/com/notacerta/
    │   ├── controller/
    │   ├── dto/
    │   ├── model/
    │   ├── repository/
    │   └── NotasApplication.java
    └── resources/
        ├── application.properties
        └── static/index.html
pom.xml
README.md
.gitignore
```

## Contribuição

Consulte [CONTRIBUTING.md](CONTRIBUTING.md) para orientações sobre contribuições.

## Licença

Este projeto está disponível sob a licença MIT. Consulte [LICENSE](LICENSE).
