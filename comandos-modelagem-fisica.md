# comandos SQL 

Comandos usados para a modelagem física.


## Criar banco de dados

```sql
CREATE DATABASE exemplo_raphael CHARACTER SET utf8mb4;
```


## Entrar no banco de dados para usá-lo

```sql
USE exemplo_raphael; (revisar, não funcionou)
```

## Criar a tabela de fabricantes


```sql
CREATE TABLE fabricantes(
    id tinyint not null primary key auto_increment,
    nome varchar(45) not null
);
```


## Criar a tabela de produtos



```sql
CREATE TABLE produtos(
    id smallint not null primary key auto_increment,
    nome varchar(45) not null,
    descricao text (1000) not null,
    fabricante_id tinyint not null
);
```



## Alterando a tabela produtos para criar um relacionamento a partir da coluna fabricante_id, com a coluna id da tabela fabricantes

```sql
ALTER TABLE produtos
    ADD CONSTRAINT fk_produtos_fabricantes
    FOREIGN KEY(fabricante_id) REFERENCES fabricantes(id);
```