# Comandos SQL para operações de dados (CRUD)

## Resumo

- C: CREATE (criar dados usando o comando INSERT)
- R: READ (ler dados usando o comando SELECT)
- U: UPDATE (atualizar dados usando o comando UPDATE)
- D: DELETE (excluir dados usando o comando DELETE)

## INSERT 

### Tabela Fabricantes

```sql
INSERT INTO fabricantes (nome) VALUES('Microsoft');
INSERT INTO fabricantes (nome) VALUES('Asus');
INSERT INTO fabricantes (nome) VALUES('Dell');

INSERT INTO fabricantes (nome)
VALUES ('Apple'), ('LG'), ('Samsung'), ('Brastemp');
```

### Tabela Produtos

```sql
INSERT INTO produtos (nome, descricao, fabricante_id) VALUES ('Ultrabook','Laptop de última geração com processador Intel Core i9 e memória de 16GB RAM.', 3);

INSERT INTO produtos (nome, descricao, fabricante_id) VALUES ('Tablet Android','Tablet com a versão 13 do sistema Android, com tela de 10 polegadas e 64 GB de armazenamento.', 6);

INSERT INTO produtos (nome, descricao, fabricante_id) VALUES ('iPhone 13 Pro Max','Alta durabilidade, processador XYZ 14, 128 GB de armazenamento, 6 GB de RAM e caro pra caramba.', 4);

INSERT INTO produtos (nome, descricao, fabricante_id) VALUES ('Geladeira','Refrigerador frost-free com acesso à Internet e bla bla bla.', 7);

INSERT INTO produtos (nome, descricao, fabricante_id) VALUES ('Xbox 123','Vídeo-game de última geração.', 1);

INSERT INTO produtos (nome, descricao, fabricante_id) VALUES ('iPad Mini','Tablet Apple com tela retina de 4k.', 4);

INSERT INTO produtos (nome, descricao, fabricante_id) VALUES ('Ultrabook','Equipamento com processador AMD Ryzen, 12 GB de RAM.', 2);

```


## SELECT

### Ler dados da tabela PRODUTOS

```sql
SELECT * FROM produtos;

SELECT nome FROM produtos;

SELECT nome, descricao FROM produtos;

SELECT descricao, nome FROM produtos;

-- Exercício: trazer o nome dos produtos apenas Apple
-- Dica: use o comando WHERE (ONDE) para indicar a condição

SELECT nome FROM produtos WHERE fabricante_id = 4; 

-- OPERADOR DIFERENTE: != OU <>
SELECT nome FROM produtos WHERE fabricante_id != 4;
SELECT nome FROM produtos WHERE fabricante_id <> 4;

-- operador ou: OR

SELECT nome, descricao FROM produtos
WHERE fabricante_id = 2 OR fabricante_id = 3;

-- ORDENANDO POR ORDEM CRESCENTE (ASC - padrão)
SELECT nome, descricao FROM produtos ORDER BY nome;

-- ORDENANDO POR ORDEM DESCRESCENTE (DESC)
SELECT nome, descricao FROM produtos ORDER BY nome DESC;

-- COUNT (campo especial) é uma função de contagem de registros
SELECT COUNT(id) FROM produtos;

-- Usando AS para defenir um apelido para a coluna de resultados 
SELECT COUNT(id) AS Quantidade FROM produtos;

```

## UPDATE (💀SEMPRE COM WHERE!!!!☠️)


```sql
UPDATE fabricantes SET nome = 'Asus do Brasil' WHERE id = 2;


-- 1) Na tabela de produtos, atualize o produto Geladeira mudando
-- o fabricante de Brastemp para Samsung.
UPDATE produtos SET fabricante_id = 6 WHERE id = 4;

-- 2) Na tabela de produtos, referente ao produto Xbox 123, mude
-- o nome para "Xbox One" e a descrição para "Novo lançamento com parcelamento em 256x."
UPDATE produtos SET nome = 'Xbox One', descricao = 'Novo lançamento em 256x.' WHERE id = 5;

```
## UPDATE (💀👹SEMPRE COM WHERE!!!!☠️👿)

```sql
DELETE FROM produtos WHERE id = 3;

-- ERRO (não da pra apagar pois há produtos deste fabricante)
DELETE FROM fabricantes WHERE id = 1; 
```



