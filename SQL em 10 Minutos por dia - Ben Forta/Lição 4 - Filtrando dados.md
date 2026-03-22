

# 🔍 Lição 4: Filtrando Dados com a Cláusula WHERE

Para obter apenas os dados desejados, é necessário especificar critérios de pesquisa, também conhecidos como **condições de filtro**.

## 1. O que é a Cláusula WHERE?

Dentro de uma instrução `SELECT`, os dados são filtrados através da cláusula `WHERE`, que deve ser posicionada logo após o nome da tabela (`FROM`).

**Exemplo de Igualdade Simples:**

SQL

```
SELECT prod_name, prod_price
FROM Products
WHERE prod_price = 3.49;
```

_Este comando verifica se a coluna possui exatamente o valor especificado e filtra o restante._

> **⚠️ IMPORTANTE - Ordem das Cláusulas:** Ao usar `ORDER BY` e `WHERE` juntos, o **ORDER BY deve vir sempre por último**. Caso contrário, o SQL gerará um erro.

---

## 2. Operadores da Cláusula WHERE

O SQL suporta uma vasta gama de operadores condicionais para refinar suas buscas.

|**Operador**|**Descrição**|
|---|---|
|`=`|Igual a|
|`<>` ou `!=`|Diferente de|
|`<`|Menor que|
|`<=`|Menor ou igual a|
|`>`|Maior que|
|`>=`|Maior ou igual a|
|`BETWEEN`|Entre dois valores (intervalo)|
|`IS NULL`|É um valor nulo (vazio)|

---

## 3. Exemplos Práticos de Comparação

### Verificando Valores Únicos

Para listar produtos com preço menor que $ 10:

SQL

```
SELECT prod_name, prod_price
FROM Products
WHERE prod_price < 10;
```

Para obter produtos que custam $ 10 ou menos:

SQL

```
SELECT prod_name, prod_price
FROM Products
WHERE prod_price <= 10;
```

### Verificando Não Correspondências

Para listar todos os itens que **não** pertencem ao fornecedor 'DLL01':

SQL

```
SELECT vend_id, prod_name
FROM Products
WHERE vend_id <> 'DLL01';
```

> **💡 Dica de Sintaxe:** Use **aspas simples** para delimitar strings (textos). Colunas numéricas não precisam de aspas.

---

## 4. Filtragem por Intervalo e Valores Nulos

### Operador BETWEEN

Utilizado para verificar um intervalo de valores. Requer o valor inicial, o final e a palavra-chave `AND`.

SQL

```
SELECT prod_name, prod_price
FROM Products
WHERE prod_price BETWEEN 5 AND 10;
```

### Verificando a Ausência de Valor (NULL)

Quando uma coluna não possui informação, ela contém um valor `NULL`. Para filtrar esses casos, usamos `IS NULL` em vez do sinal de igual.

SQL

```
SELECT prod_name
FROM Products
WHERE prod_price IS NULL;
```

_Esta instrução retorna produtos que não possuem preço cadastrado._

---

### ⚠️ Cuidado: NULL e Correspondências

Fique atento: ao procurar por correspondências (ex: `WHERE preco <> 10`), o SQL **não retorna** as linhas que possuem valor `NULL`. Elas são tratadas como "desconhecidas" e acabam ficando de fora tanto dos filtros de igualdade quanto de desigualdade.

---



## Desafios

1) 
   ```
SELECT prod_id, prod_name
FROM Products
WHERE prod_price = 9.49

   ```

2) 
```
SELECT prod_id, prod_name
FROM Products
WHERE prod_price >= 9
```

3) 
   ```
SELECT order_num
FROM OrderItems
WHERE quantity >= 100
   ```

4) 
```
SELECT prod_name, prod_price
FROM Products
WHERE prod_price BETWEEN 3 AND 6
ORDER BY prod_price
   ```