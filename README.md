# Passo a passo: Criação de um banco de dados
Tutorial de como criar um banco de dados SQL que organiza as informações de 'livros', 'editora', 'autores' e 'assuntos'.
Este guia será dividido em etapas para demonstrar desde a criação de tabelas, chaves e até manipulação/consulta de dados.

## Resumo de uma estrutura SQL 
- *_CREATE_*: para criar 'Banco de dados' ou 'Tabelas'
- *_ALTER_*: para adiciomar ou modificar colunas
- *_DROP_*: para remover 'Banco de dados' ou 'Tabelas'
- *_INSERT_*: parra adicionar registros na tabela
- *_UPDATE_*: para atualizar os registros
- *_SELECT_*: para consultar e visualizar dados



## Passo 1: criação do Banco de Ddados e das Tabelas
### 1.1 Criando o DB

```
CREATE DATABASE biblioteca;
USE biblioteca;
```

### 1.2 Criando a tabela 'editora'
```
CREATE TABLE editora (
    id_editora INT PRIMARY KEY AUTO_INCREMENT,
    nome_editora VARCHAR(100) NOT NULL,
    pais VARCHAR(50)
);
```

#### 1.3 Criando a tabela 'autor'
```
`CREATE TABLE autor(
    id_autor INT PRIMARY KEY AUTO_INCREMENT,
    nome_autor VARCHAR
    data_nascimento DATE
);
```

#### 1.4 Criando a tabela 'assunto'
``` 
CREATE TABLE assunto (
    id_assunto INT PRIMARY KEY AUTO_INCREMENT,
    descricao_assunto VARCHAR(200) NOT NULL
);
``` 
#### 1.5 Criando a tabela 'livro'
```
CREATE TABLE livro (
    id_livro INT PRIMARY KEY AUTO_INCREMENT,
    titulo VARCHAR(150) NOT NULL,
    ano_publicacao YEAR,
    FOREING KEY(id_editora) REFERENCES editora
    (id_editora),
    FOREING KEY(id_autor) REFERENCES autor(id_autor),
    FOREIGN KEY(id_assunto) REFERENCE assunto(id_assunto)
);
``` 

#### 1.6 Criando uma tabela EXTRA
A tavela EXTRA vai servir para exemplificar a exclusão

```
CREATE TABLE extra(
    id INT PRIMARY KEY AUTO_INCREMENT,
    produtos VARCHAR(50),
    quantidade INT(),
    preco 
);
```

## Passo 2: editar tabrlas usando 'ALTER'
Após a criação da tabela, podemos adicionar novos campos. Vamos adicionar uma coluna 'email' na tabela 'autor'

```SQL
ALTER TABLE autor
ADD COLUMN email VARCHAR(100);
``` 
