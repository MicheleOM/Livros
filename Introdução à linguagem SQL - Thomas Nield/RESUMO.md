
___
___

## CAPÍTULO 1 - PORQUE APRENDER SQL

### O que é SQL e porque ele é vendável?

O **SQL (Structured Query Language)** é a linguagem padrão universal para comunicação com bancos de dados relacionais. Ele é "vendável" porque vivemos na era dos dados; a capacidade de extrair, manipular e analisar informações diretamente da fonte é uma das habilidades mais requisitadas no mercado moderno.

- **Insights:** Permite transformar dados brutos em inteligência de negócio.
    
- **Padronização:** Uma vez aprendido o SQL básico, você consegue trabalhar com quase qualquer sistema (MySQL, PostgreSQL, SQL Server).
    

### Pra quem se destina o SQL?

A versatilidade do SQL divide os profissionais em dois grandes pilares:

- **Lado Empresarial/Analítico:** Analistas de dados, gestores de BI, profissionais de marketing e estratégia que precisam de autonomia para gerar relatórios sem depender do TI.
    
- **Lado de TI/Desenvolvimento:** Engenheiros de software, administradores de banco de dados (DBA), arquitetos de sistemas e engenheiros de dados que constroem e mantêm a infraestrutura onde os dados residem.
    

---

## CAPÍTULO 2 - BANCO DE DADOS

### O que é um banco de dados

Um **RDBMS (Relational Database Management System)** é o software que gerencia coleções de tabelas relacionadas. Diferente de um simples arquivo de texto, ele garante a integridade e a segurança dos dados.

### Examinando banco de dados relacionais

- **Tabelas:** Estruturas compostas por **Colunas** (atributos/campos) e **Linhas** (registros/tuplas).
    
- **Relacionamentos:** As tabelas se conectam através de chaves (Primary Keys e Foreign Keys), permitindo que os dados sejam consultados de forma combinada.
    

### Porque tabelas separadas

O motivo principal é a **Normalização**.

- **Redução de Redundância:** Evita repetir a mesma informação (ex: nome do cliente) em cada linha de pedido.
    
- **Integridade:** Se o endereço de um fornecedor mudar, você altera em apenas um lugar.
    
- **Eficiência:** Tabelas menores e específicas tornam a manutenção e a busca mais ágeis.
    

### Selecionando uma solução de banco de dados

|**Tipo**|**Exemplos**|**Características**|
|---|---|---|
|**Leves (Serverless)**|SQLite, MS Access|Um único arquivo, sem necessidade de servidor, ideal para apps locais e protótipos.|
|**Centralizados (Client-Server)**|MySQL, PostgreSQL, Oracle|Exigem um servidor, suportam milhares de usuários simultâneos e grandes volumes de tráfego.|

---

## CAPÍTULO 3 - SQLITE

### O que é SQLite?

É uma biblioteca C que implementa um mecanismo de banco de dados SQL independente e de configuração zero.

- **Portabilidade:** O banco de dados inteiro é um único arquivo em disco.
    
- **Uso:** Onipresente em dispositivos móveis (Android/iOS) e navegadores.
    
- **Limitação:** Não suporta alta concorrência de escrita (vários usuários editando ao mesmo tempo).
    

### SQLiteStudio

Ferramenta visual (GUI) para gerenciar bases de dados SQLite sem precisar usar apenas a linha de comando.

### Importando e procurando banco de dados

Ao observar as tabelas, é crucial entender os **Tipos de Dados**:

- `INTEGER`: Números inteiros (ex: 1, 10, 500).
    
- `DECIMAL` / `REAL`: Números com casas decimais (preços, medidas).
    
- `DATETIME`: Carimbos de data e hora.
    
- `BOOLEAN`: Valores lógicos (Verdadeiro/Falso ou 1/0).
    

---

## CAPÍTULO 4 - SELECT

### Recuperando dados com SQL

A cláusula `SELECT` é a base de quase tudo no SQL.

- `SELECT * FROM tabela;` -> Seleciona todas as colunas.
    
- `SELECT col1, col2 FROM tabela;` -> Seleciona colunas específicas (melhor prática para performance).
    

### Expressões em instruções SELECT

Você pode criar **Colunas Calculadas** (Campos Calculados) que existem apenas durante a execução da consulta.

**Exemplo de aumento de preço com Alias (`AS`):**

SQL

```
SELECT 
    product_id, 
    description, 
    price, 
    ROUND(price * 1.07, 2) AS taxed_price 
FROM product;
```

> [!TIP]
> 
> Use sempre **Underscores** (`_`) em vez de espaços em nomes de aliases para evitar erros de sintaxe.

**Operadores Matemáticos Comuns:**

- `+` (Adição)
    
- `-` (Subtração)
    
- `*` (Multiplicação)
    
- `/` (Divisão)
    
- `%` (Módulo - resto da divisão)
    

### Concatenação de texto

A concatenação permite unir strings ou colunas de texto. No SQLite e PostgreSQL, usa-se o operador de barra dupla `||`.

**Exemplo de Concatenação:**

Para unir o nome e o sobrenome de um cliente em uma única coluna:

SQL

```
SELECT 
    first_name || ' ' || last_name AS full_name 
FROM customers;
```

- O resultado será tratado como um tipo de dado de texto (String).
    


---

## CAPÍTULO 5 - WHERE


### Filtrando registros

### Usando WHERE com números

### Instruções NAD, OR e IN

### Usando WHERE com texto

### Usando WHERE com booleanos

### Manipulando NULL

### Agrupando condições