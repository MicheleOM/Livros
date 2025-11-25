
## 📚 Lição 2 - Obtenção de Dados


## 💻 Instrução `SELECT`

Seu objetivo é **obter informações** de uma ou mais tabelas.

> **Observação:** Uma **palavra-chave** é uma palavra reservada que faz parte da linguagem SQL e **não pode** ser usada para nomear tabela ou coluna.

Para utilizar o `SELECT`, deve-se especificar duas informações: **o que** deseja selecionar e **de onde** (qual tabela).

---

### Obtendo Colunas Individuais

A sintaxe básica para selecionar uma única coluna é:

SQL

```
SELECT prod_name
FROM Products;
```

O exemplo usa a instrução `SELECT` para obter uma única coluna chamada `prod_name` da tabela `Products`. O nome da coluna desejada é especificado logo após a palavra-chave `SELECT`, e a palavra-chave `FROM` especifica o nome da tabela da qual os dados serão obtidos.

Uma instrução `SELECT` simples como essa retorna **todas as linhas** de uma tabela. Os dados não são filtrados nem classificados.

---

### Detalhes Importantes do SQL

#### Encerrando Instruções

Múltiplas instruções SQL devem ser separadas por **ponto e vírgula** (`;`). A maioria dos SGBDs (Sistemas Gerenciadores de Banco de Dados) não exige que um ponto e vírgula seja especificado após instruções únicas.

#### Instrução SQL e Distinção entre Maiúsculas e Minúsculas

As instruções SQL **não diferenciam maiúsculas e minúsculas**. É uma prática comum utilizar as palavras-chave da instrução em **maiúsculas** (`SELECT`, `FROM`, etc.) para facilitar a leitura e a depuração do código.

Embora a linguagem não faça distinção entre maiúsculas e minúsculas para suas palavras-chave, os **nomes das tabelas**, **colunas** e **valores** podem ser _case sensitive_ (diferenciar maiúsculas de minúsculas), dependendo do SGBD e de sua configuração.

#### Espaços em Branco

Todo o espaço em branco extra em uma instrução é **ignorado** quando a instrução é processada. As instruções SQL podem ser especificadas em uma linha longa ou divididas em várias linhas para melhor legibilidade.

---

### Obtendo Múltiplas Colunas

Para obter múltiplas colunas, também é utilizada a instrução `SELECT`. A diferença é que vários nomes de coluna devem ser especificados, e cada coluna deve ser separada por **vírgula** (`,`).

> **Atenção:** Após o último nome de coluna, **não** se deve colocar uma vírgula para evitar um erro de sintaxe.

SQL

```
SELECT prod_id, prod_name, prod_price
FROM Products;
```

---

### Obtendo Todas as Colunas

As instruções `SELECT` também podem solicitar **todas as colunas** sem especificar individualmente cada uma. Para isso, usa-se o **asterisco** (`*`).

SQL

```
SELECT *
FROM Products;
```

> **Observação:** Como regra, é melhor **não utilizar o `*`** sem necessidade, pois obter colunas desnecessárias geralmente **diminui o desempenho** da consulta e da aplicação. No entanto, ele é útil para obter nomes de colunas desconhecidas ou em consultas exploratórias.

---

### Obtendo Linhas Distintas

Para obter as ocorrências de valores **distintos** (únicos) em uma coluna, utiliza-se a palavra-chave **`DISTINCT`**. Ao usá-la, deve ser colocada **obrigatoriamente** antes dos nomes das colunas.

SQL

```
SELECT DISTINCT vend_id
FROM Products;
```

---

### Limitando os Resultados (Limpeza de Linhas)

A instrução `SELECT` por padrão retorna todas as linhas correspondentes da tabela especificada. Se você quiser ou precisar apenas de um número específico de linhas, é possível fazer isso dependendo do SGBD que está sendo usado:

|**SGBD**|**Sintaxe para as Primeiras X Linhas**|**Exemplo (Primeiras 5)**|
|---|---|---|
|**Microsoft SQL Server**|`TOP X`|`SELECT TOP 5 prod_name FROM Products;`|
|**DB2**|`FETCH FIRST X ROWS ONLY`|`SELECT prod_name FROM Products FETCH FIRST 5 ROWS ONLY;`|
|**MySQL, MariaDB, PostgreSQL, SQLite**|`LIMIT X`|`SELECT prod_name FROM Products LIMIT 5;`|

#### Obtendo Linhas com Início e Quantidade Específicos

Para outros valores, você pode indicar onde começar (`OFFSET`) e a quantidade de linhas a serem obtidas (`LIMIT`).

SQL

```
SELECT prod_name
FROM Products
LIMIT 5 OFFSET 5;
```

Esta instrução limita a quantidade de linhas a ser obtida para 5 (`LIMIT 5`), começando a contagem **após as primeiras 5 linhas** (`OFFSET 5`).

> **Atenção:** A contagem das linhas (`OFFSET`) geralmente começa no **0** em muitos SGBDs.

Abreviação em MySQL, MariaDB e SQLite:

Nesses SGBDs, é possível usar uma abreviação, onde a ordem da combinação muda:

LIMIT inicio, quantidade

SQL

```
-- Equivalente a LIMIT 4 OFFSET 3 (Começa na 4ª linha, obtém 3 linhas)
SELECT prod_name
FROM Products
LIMIT 3, 4; 
```

---

### Usando Comentários

É possível comentar em SQL para documentar o código:

|**Tipo de Comentário**|**Sintaxe**|**Exemplo**|
|---|---|---|
|**Comentário de Linha (Após escrita)**|Duplo hífen (`--`)|`SELECT prod_name -- Obtém o nome do produto`|
|**Comentário de Linha (Linha inteira)**|Hashtag (`#`)|`# Instrução para obter todos os produtos`|
|**Comentários de Múltiplas Linhas**|Barra e asterisco (`/*` e `*/`)|`/* Este comentário pode se estender por várias linhas */`|

