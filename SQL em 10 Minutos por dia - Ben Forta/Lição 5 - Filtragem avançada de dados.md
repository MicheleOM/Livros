


O SQL permite combinar múltiplas condições na cláusula `WHERE` para um controle refinado dos dados.

> obs: quando usar string, necessário colocar apenas uma aspa: ' '

## 1. Operadores de Combinação (AND e OR)

> [!ABSTRACT] Definição
> 
> **Operador:** Palavra-chave usada para juntar ou alterar cláusulas dentro de um `WHERE`. Também conhecidos como operadores lógicos.

### 🔹 Operador AND

Retorna apenas as linhas que atendem a **todas** as condições especificadas.

- **Exemplo:**
    

SQL

```
SELECT prod_id, prod_price, prod_name
FROM Products
WHERE vend_id = 'DLL01' AND prod_price <= 4;
```

- _(Filtra produtos do fornecedor DLL01 **E** com preço até $ 4)._
    

### 🔸 Operador OR

Retorna linhas que correspondam a **qualquer uma** das condições.

- **Exemplo:**
    

SQL

```
SELECT prod_id, prod_price, prod_name
FROM Products
WHERE vend_id = 'DLL01' OR vend_id = 'BRS01';
```

- _(Filtra produtos que pertençam a um **OU** a outro fornecedor)._
    

---

## ⚖️ Ordem de Avaliação (Precedência)

Ao misturar `AND` e `OR`, o SQL segue uma hierarquia que pode causar resultados inesperados.

1. **Precedência Padrão:** O SQL processa o `AND` antes do `OR`.
    
2. **A Solução:** Use **parênteses `()`** para agrupar explicitamente as condições.
    
3. **Boa Prática:** Nunca confie na ordem padrão; use parênteses para eliminar ambiguidades e facilitar a leitura.
    

---

## 📋 Operador IN

O operador `IN` especifica uma lista de valores válidos entre parênteses, separados por vírgula.

SQL

```
SELECT prod_name, prod_price
FROM Products
WHERE vend_id IN ('DLL01', 'BRS01')
ORDER BY prod_name;
```

### Por que usar o IN em vez de vários OR?

- **Sintaxe:** Muito mais limpa e legível para listas longas.
    
- **Gestão:** Mais fácil de gerenciar a ordem de avaliação com outros operadores.
    
- **Velocidade:** Quase sempre é executado mais rápido que múltiplos `OR`.
    
- **Dinamismo:** Pode conter uma subinstrução `SELECT` (subquery).
    

---

## 🚫 Operador NOT

O `NOT` tem a função única de **negar** a condição que o segue.

- **Sintaxe:** Pode ser usado antes da coluna (ex: `NOT vend_id = 'DLL01'`).
    
- **Utilidade:** Extremamente útil em filtros complexos, como encontrar linhas que **não** estão em uma lista de critérios (`NOT IN`).
    
- **Nota:** Muitas vezes pode ser substituído pelo operador de diferença `<>`.
    



---
---

## Desafios

1) 
   ```
SELECT vend_name
FROM Vendors
WHERE vend_country = 'USA' AND vend_state = 'CA'
   ```

2) 
   ```
SELECT order_num, prod_id, quantity
FROM orderItems
WHERE prod_id IN ('BR01', 'BR02', 'BR03') AND  quantity >= 100
   ```

3) 
   ```
SELECT prod_name, prod_price
FROM Products
WHERE prod_price >= 3 AND prod_price <= 6
ORDER BY prod_price
   ```

4) 
   ```
 ORDER BY vem após instruções WHERE
   ```