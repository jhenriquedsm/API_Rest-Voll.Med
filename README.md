
# VOLL.MED API

API REST com CRUD de Médicos e Pacientes da Voll.Med.

Projeto realizado durante a Formação Java e Spring Boot - Alura.


## Tecnologias utilizadas

- Java
- Spring 3.0.5
- MySQL
- Insomnia

## Dependências utilizadas
- Spring Web
- Spring Boot Dev Tools
- Spring Data JPA
- Lombok
- MySQL Driver
- Flyway Migration


## Rodando localmente

Baixe o projeto

```bash
  Download Zip
```

Crie o banco de dados na sua máquina (MySQL)

```bash
  create database vollmed_api;
```

Rode a aplicação (IDE INTELLIJ)

```bash
  Run 'ApiApplication.main()'
```



## Documentação da API

### Paginação:

#### Cadastro de Médico

```http
  POST http://localhost:8080/medicos
```

#### Listagem de Médico

```http
  GET http://localhost:8080/medicos
```

#### Para controlar a quantidade de registros serão devolvidos é preciso utilizar o "?size=x", onde x é o valor de registros que serão devolvidos. Caso não passe o size, o Spring retorna por padrão size = 20. No nosso caso, passamos a anotação "@PageableDefault", que diz ao Spring que se não houver parametros na requisição, o size será igual a 10 e a ordenação será feita pelo atributo nome. Caso seja passado parâmetros, eles sobrescrevem o "@PageableDefault"

```http
  GET http://localhost:8080/medicos?size=1
```

#### Adicionando o "&page=x", onde x é o valor da página desejada, você diz ao Spring qual página será devolvida. (A primeira página é 0).

```http
  GET http://localhost:8080/medicos?size=1&page=1
```

### Ordenação:

#### Utilizando o "?sort=nome", a requisição irá devolver os registros ordenados pelo atributo nome da nossa API. Para ordenar de acordo com o atributo desejado é só utilizar "?sort=atributo", onde atributo é o nome do atributo desejado.

```http
  GET http://localhost:8080/medicos?sort=nome
```

#### Por padrão a ordenação é em ordem crescente (asc), mas e se eu quiser exibir os registros em ordem decrescente? É só utilizar o ",desc" após o "?sort=atributo". No caso dessa requisição, a ordenação será feita em ordem decrescente em relação ao atributo nome.

```http
  GET http://localhost:8080/medicos?sort=nome,desc
```

### Requisição:

#### Nesta requisição estamos pedindo para apresentar os registros de acordo com o atributo nome de forma crescente (asc), com tamanho de 2 registros por página e requisitando a página 0 (primeira página).

```http
  GET http://localhost:8080/medicos?sort=nome,asc&size=2&page=0
```
## Aprendizados

Neste projeto foi possível aprender e aprimorar conceitos, teorias e práticas com Spring Boot em Java.
A criação desta API Rest com CRUD completo, utilizando dependencias como Lombok para construção de Getters, Args e EqualsAndHashCode. Spring Data JPA para persistir os dados no banco de dados, utilizando JpaRepository. Flyway Migration para trabalhar com as migrations necessárias e ter um histórico da evolução do banco de dados. E por fim, Spring Web: onde conseguimos mapear a nossa API para receber as requisições e funcionar nosso CRUD.


## Autores

- [@jhenriquedsm](https://www.github.com/jhenriquedsm)


## Feedback

Se você tiver algum feedback, sugestão ou algo para falar, por favor me comunique por jhsilvamata@gmail.com
