
# 📊 Lição 3: Classificando Dados (SQL)

Na manipulação de bancos de dados, a sequência dos dados retornados não pode ser prevista a menos que uma ordem seja explicitamente especificada. Para isso, utilizamos a cláusula `ORDER BY`.

---

## 1. A Cláusula ORDER BY

A cláusula `ORDER BY` é utilizada para classificar os resultados de uma consulta. Ela recebe o nome de uma ou mais colunas que servirão como base para a ordenação.

### Sintaxe Básica

SQL

```
SELECT prod_name
FROM Products
ORDER BY prod_name;
```

> **⚠️ Regra de Ouro:** A cláusula `ORDER BY` deve ser sempre a **última** instrução dentro do bloco `SELECT`. Caso contrário, o sistema retornará um erro.

---

## 2. Métodos de Classificação

### A. Por Múltiplas Colunas

Útil quando há dados duplicados na primeira coluna de ordenação. Basta separar os nomes das colunas por vírgulas.

SQL

```
SELECT prod_id, prod_price, prod_name
FROM Products
ORDER BY prod_price, prod_name;
```

_Os produtos são ordenados pelo preço; se houver preços iguais, a ordenação secundária será pelo nome._

### B. Pela Posição da Coluna

Em vez do nome, utiliza-se o índice numérico da coluna conforme ela aparece no `SELECT`.

SQL

```
SELECT prod_id, prod_price, prod_name
FROM Products
ORDER BY 2, 3; 
-- Ordena pela 2ª (prod_price) e 3ª (prod_name) colunas
```

|**Vantagens**|**Desvantagens**|
|---|---|
|Evita redigitar nomes longos.|Maior chance de erro ao selecionar o índice errado.|
|Consultas rápidas e informais.|Quebra se você alterar a ordem das colunas no `SELECT`.|
|Prático para testes rápidos.|**Não funciona** para colunas fora da lista do `SELECT`.|

---

## 3. Direção da Classificação

A ordenação pode ser crescente (padrão) ou decrescente através de palavras-chave específicas.

- **ASC (Ascending):** Ordem crescente (A-Z, 0-9). É o padrão.
    
- **DESC (Descending):** Ordem decrescente (Z-A, 9-0).
    

### Exemplo Combinado

SQL

```
SELECT prod_id, prod_price, prod_name
FROM Products
ORDER BY prod_price DESC, prod_name;
```

> **Dica:** A palavra-chave `DESC` aplica-se **apenas** à coluna que a precede diretamente. Para inverter múltiplas colunas, você deve escrever `DESC` após cada uma delas.

---

### 💡 Notas Adicionais

- **Colunas Invisíveis:** É possível classificar por uma coluna que você **não** incluiu no `SELECT` (usando o nome real dela).
    
- **Mix de Técnicas:** Você pode misturar nomes de colunas e posições na mesma linha, mas evite isso para manter o código legível.
    


---
---

## Desafios

1) ```
   SELECT cust_name 
	FROM Customers 
	ORDER BY cust_name DESC
   ```

2) ```
   SELECT cust_id, order_num
	FROM Orders
	ORDER BY cust_id, order_date DESC
   ```

3) ```
   SELECT quantity, item_price
	FROM OrderItems
	ORDER BY quantity DESC, item_price DESC
   ```

4) ```
   em ORDER falta o BY, em SELECT vend_name não deve haver a vírgula
   ```
