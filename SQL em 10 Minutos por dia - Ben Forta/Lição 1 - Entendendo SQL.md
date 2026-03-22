
## 📝 Lição 1 - Entendendo SQL: A Linguagem dos Bancos de Dados

O **SQL (Structured Query Language)** é a linguagem padrão usada para **interagir e manipular bancos de dados relacionais**.

É a base para diversas operações do dia a dia, como:

- **Selecionar** um contato salvo no celular.
    
- Fazer **login** em um sistema usando nome de usuário e senha.
    
- Realizar uma **pesquisa** no Google.
    

---

## 🏛️ Estrutura e Componentes Essenciais

Para entender o SQL, é fundamental conhecer os elementos que compõem um sistema de gerenciamento de banco de dados (SGBD).

### **Banco de Dados (Database)**

- Um **container** (geralmente um arquivo ou um conjunto de arquivos) usado para **armazenar dados organizados**.
    
- **Analogia:** O banco de dados é como um **armário de arquivos físico**, um local para guardar todas as informações.
    

### **SGBD (Sistema de Gerenciamento de Banco de Dados)**

- É o **software de banco de dados**. Ele é responsável por gerenciar o banco de dados, permitindo a criação, leitura, atualização e exclusão (CRUD) de dados.
    

### **Tabelas (Tables)**

- Uma **lista estruturada de dados de um tipo específico** (ex: lista de clientes, catálogo de produtos, etc.).
    
- **Analogia:** Dentro do armário de arquivos, a informação não é jogada na gaveta; é criado um **arquivo/pasta (Tabela)** para conter os dados relacionados.
    

> **❗ Importante:** Os dados armazenados em uma tabela devem ser do **mesmo tipo de dado ou lista relacionada**. Por exemplo, nunca se armazenaria uma lista de clientes e uma lista de pedidos na mesma tabela.

- Toda tabela tem um **nome único** que a identifica no banco de dados (mas nomes podem ser reutilizados em bancos de dados diferentes).
    

### **Esquema (Schema)**

- O conjunto de informações que descreve o **layout e as propriedades** do banco de dados e das tabelas.
    
- Descreve as **características e propriedades** dos dados armazenados em uma tabela.
    

### **Coluna (Column)**

- Um **único campo** em uma tabela. Todas as tabelas são compostas por uma ou mais colunas.
    
- É crucial separar os dados em várias colunas corretamente para melhor **classificar ou filtrar** as informações.
    

### **Datatype (Tipo de Dado)**

- Um **tipo de dado permitido** (ex: texto, número inteiro, data).
    
- Cada coluna tem um Datatype associado que **restringe** os dados permitidos e ajuda a otimizar o uso do disco.
    

> **⚠️ Cuidado:** Os Datatypes e seus nomes são uma das principais fontes de **incompatibilidade** entre diferentes implementações de SQL (diferentes SGBDs).

### **Linha (Row) / Registro (Record)**

- Um **registro** completo em uma tabela. Os dados em uma tabela são armazenados em linhas, onde cada linha representa uma ocorrência única.
    

> **💡 Lembre-se:** Assim como em uma planilha, as **colunas** são as divisões **verticais** da tabela, e as **linhas** são as divisões **horizontais**.
> 
> ![Imagem de a database table showing columns and rows](https://encrypted-tbn0.gstatic.com/licensed-image?q=tbn:ANd9GcQ9Lnt_CiW3G5pb-052zPkdgAx46tdjKUt0WR_Nqr-uRpXw-7SQWqhBMC-L8p6v6d4fK6dACLAjGRnNCEr7fWCje9TsOPJzOnAtmws0Q6ZN04kFmUs)
> 
> Shutterstock
> 
> Explorar

---

## 🔑 Chaves Primárias (Primary Keys)

- Uma coluna (ou conjunto de colunas) cujos valores **identificam de forma única cada linha** em uma tabela.
    
- Embora não seja uma exigência estrutural absoluta para o SGBD, é **essencial** criar uma chave primária para possibilitar a manipulação e o gerenciamento de dados no futuro.
    

### **Condições Essenciais para uma Chave Primária:**

Qualquer coluna pode ser definida como chave primária, desde que atenda a estas condições:

- **Unicidade:** Duas linhas não podem ter o mesmo valor de chave primária.
    
- **Não Nulidade:** Cada linha deve ter um valor na coluna da chave primária (**NULL não é permitido**).
    
- **Imutabilidade:** Os valores nas colunas da chave primária **nunca** devem ser modificados ou atualizados.
    
- **Não Reutilização:** Os valores da chave primária **nunca** devem ser reutilizados, mesmo que a linha original seja excluída.
    

---
