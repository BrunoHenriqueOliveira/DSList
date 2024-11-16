# DSList

 ![Java](https://img.shields.io/badge/java-%23ED8B00.svg?style=for-the-badge&logo=openjdk&logoColor=white)
 ![Spring](https://img.shields.io/badge/spring-%236DB33F.svg?style=for-the-badge&logo=spring&logoColor=white)

## Descrição:

Este projeto consiste em uma API REST desenvolvida em Java com Spring Boot, que se 
comunica com um banco de dados H2 para gerenciar uma coleção de jogos. A API permite
a leitura, atualização, além de organizar os jogos em listas.


## Tabela de Jogos em suas respectivas listas e posições:

| POSITION | GAME_ID | LIST_ID | TITLE                        |
|----------|---------|---------|------------------------------|
| 0        | 1       | 1       | Mass Effect Trilogy          |
| 1        | 2       | 1       | Red Dead Redemption 2        |
| 2        | 3       | 1       | The Witcher 3: Wild Hunt     |
| 3        | 4       | 1       | Sekiro: Shadows Die Twice    |
| 4        | 5       | 1       | Ghost of Tsushima            |
| 0        | 6       | 2       | Super Mario World            |
| 1        | 7       | 2       | Hollow Knight                |
| 2        | 8       | 2       | Ori and the Blind Forest     |
| 3        | 9       | 2       | Cuphead                      |
| 4        | 10      | 2       | Sonic CD                     |

## Estrutura do Projeto:
```
├── DSList/
├── build.gradle
├── gradle/
│   ├── wrapper/
│       ├── gradle-wrapper.jar
│       └── gradle-wrapper.properties
├── gradlew
├── gradlew.bat
├── LICENSE
├── settings.gradle
└── src/
    ├── main/
    │   ├── java/
    │   │   └── com/
    │   │       └── devsuperior/
    │   │           └── dslist/
    │   │               ├── config.java
    │   │               │   └── WebConfig
    │   │               ├── controllers
    │   │               │   ├── GameController
    │   │               │   └── GAmeListController    
    │   │               ├── dto
    │   │               │   ├── GameDTO
    │   │               │   ├── GameListDTO
    │   │               │   ├── GameMinDTO
    │   │               │   └── ReplacementDTO
    │   │               ├── entities
    │   │               │   ├── Belonging
    │   │               │   ├── BelongingPK
    │   │               │   ├── Game
    │   │               │   └── GameList
    │   │               ├── projections
    │   │               │   └── GameMinProjection
    │   │               ├── respositories
    │   │               │   ├── GameListRepository
    │   │               │   └── GameRepository
    │   │               ├── services
    │   │               │   ├── GameListRepository
    │   │               │   └── GameRepository
    │   │               └── dslistApplication.java
    │   ├── resources/
    │   │   ├── static
    │   │   ├── templates
    │   │   ├── application.properties
    │   │   ├── application-dev.properties
    │   │   ├── application-prod.properties
    │   │   ├── application-test.properties
    │   │   └── import.sql
    │   │
    └── test/
```

## Tecnologias Utilizadas:

* java - 21
* Spring Web
* Spring Data JPA
* gradle
* H2 Database
* PostgreSQL
* Lombok

## Instalação:

````bash
  git clone https://github.com/BrunoHenriqueOliveira/DSList
````

## Como Usar:

Apos iniciar o projeto acesse a URL:
```
    http://localhost:8080/h2-console
```

Prencha os seguintes campos no login do H2

* JDBC URL: jdbc:h2:mem:testdb
* User Name: sa

## API Endpoints
Utilizando um programa para realizar chamadas para os endpoint, como o [Insomnia](https://insomnia.rest/download) ou o [Postman](https://www.postman.com/)

**GET games**
```markdown
GET http://localhost:8080/games
```
**GET games by id**
```markdown
GET http://localhost:8080/games/2
```
**GET lists**
```markdown
GET http://localhost:8080/lists
```
**GET games by list**
```markdown
GET http://localhost:8080/lists/1/games
```
**POST list replacement**

Passe o id do jogo que deseja realocar e o id que deseja realocar ele
```markdown
GET http://localhost:8080/lists/2/replacement
```
```json
{
  "sourceIndex": 3,
  "destinationIndex": 1
}
```

## Licença:

* Este projeto é licenciado sob a MIT License.

## Autores:

* Bruno Henrique 

## Agradecimentos:

Esse projeto foi desenvolvido durante a semana de intensivão de Java Spring com o Nelio do [DevSuperior](https://github.com/devsuperior)