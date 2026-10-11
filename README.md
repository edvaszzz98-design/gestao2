# Sistema de Gestão de Notas — Java

Aplicação web com back-end Java + Spring Boot, banco H2 em arquivo e interface web simples servida pelo próprio Spring Boot.

## Requisitos
- JDK 17 ou superior
- Maven 3.8+ (ou use sua IDE com suporte a Maven)

## Executar
Na pasta do projeto:
```bash
mvn spring-boot:run
```
Acesse: http://localhost:8080

## Funcionalidades
- Cadastro e exclusão de alunos
- Cadastro e exclusão de disciplinas
- Registro e exclusão de notas (0 a 10)
- Média por aluno e disciplina
- Boletim com situação acadêmica
- Persistência H2 em arquivo local

Regra demonstrativa: média >= 7 = Aprovado; média >= 5 e < 7 = Recuperação; média < 5 = Reprovado. Ajuste conforme as regras da escola.

## API REST
- `GET /api/students`
- `POST /api/students` — JSON: `{"name":"Ana Souza","email":"ana@escola.com"}`
- `DELETE /api/students/{id}`
- `GET /api/subjects`
- `POST /api/subjects` — JSON: `{"name":"Matemática"}`
- `DELETE /api/subjects/{id}`
- `GET /api/grades`
- `POST /api/grades` — JSON: `{"studentId":1,"subjectId":1,"score":8.5}`
- `DELETE /api/grades/{id}`
- `GET /api/students/{id}/summary`
- `GET /api/health`

## Versionar no GitHub/GitLab
```bash
git init
git add .
git commit -m "feat: sistema de gestão de notas em Java"
git branch -M main
git remote add origin URL_DO_REPOSITORIO
git push -u origin main
```
