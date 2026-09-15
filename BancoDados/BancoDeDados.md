````markdown
# 📊 Atividade SQL — Vale Ferramentas

## 📌 Sobre a atividade

Nesta atividade foram realizadas consultas SQL utilizando um banco de dados de vendas da empresa **Vale Ferramentas**.

O objetivo foi praticar comandos de consulta, filtros, ordenação, funções de agregação, cálculos e também a manutenção dos dados da tabela.

---

## 🎯 Objetivos

- Consultar registros do banco de dados;
- Utilizar `SELECT` para visualizar informações;
- Utilizar `LIMIT` para limitar os resultados;
- Utilizar `COUNT()` para contar registros;
- Utilizar `DISTINCT` para eliminar valores repetidos;
- Utilizar `WHERE` para filtrar informações;
- Utilizar `BETWEEN` para trabalhar com intervalos;
- Utilizar `IN` para pesquisar vários valores;
- Utilizar `LIKE` para pesquisar textos por padrão;
- Utilizar `ORDER BY` para ordenar resultados;
- Realizar cálculos utilizando `SUM()`, `AVG()`, `MAX()` e `MIN()`;
- Utilizar `AS` para criar apelidos nas colunas;
- Realizar `INSERT`, `UPDATE` e `DELETE`.

---

## 🗂️ Banco de Dados

O banco contém uma tabela chamada:

```sql
vendas
````

A tabela possui informações relacionadas às vendas, como:

* ID da venda;
* Data da venda;
* Nome do cliente;
* Cidade;
* Estado;
* Categoria;
* Produto;
* Quantidade;
* Preço unitário;
* Desconto;
* Forma de pagamento;
* Vendedor;
* Status da entrega.

---

## 🔎 Consultas realizadas

Durante a atividade foram realizadas **20 questões**, divididas em cinco blocos:

### 1️⃣ Conhecendo a base

Foram utilizadas consultas para:

* Visualizar as primeiras 20 vendas;
* Contar o total de vendas;
* Listar categorias sem repetição;
* Listar cidades e estados.

### 2️⃣ Filtros com WHERE

Foram realizadas consultas para encontrar:

* Vendas da categoria `EPI`;
* Vendas com grande quantidade e preço;
* Vendas de cidades específicas;
* Vendas realizadas em março de 2026;
* Clientes cujo nome começa com "Metalúrgica";
* Vendas canceladas pagas por Boleto ou PIX.

### 3️⃣ Ordenação

Foram utilizadas ordenações para:

* Encontrar os 10 maiores preços;
* Encontrar as 5 vendas mais antigas de uma categoria;
* Consultar as vendas da vendedora Ana Ribeiro.

### 4️⃣ Cálculos e funções

Foram realizados cálculos de:

* Valor bruto das vendas;
* Valor líquido considerando descontos;
* Faturamento bruto total;
* Faturamento da categoria EPI;
* Ticket médio;
* Maior e menor venda;
* Quantidade de vendas.

### 5️⃣ Manutenção dos dados

Por fim, foram realizados comandos para:

* Cadastrar uma nova venda com `INSERT`;
* Alterar o status da venda com `UPDATE`;
* Excluir a venda com `DELETE`;
* Conferir a quantidade final de registros com `COUNT()`.

---

## 🛠️ Principais comandos utilizados

```sql
SELECT
INSERT
UPDATE
DELETE
WHERE
ORDER BY
LIMIT
COUNT()
SUM()
AVG()
MAX()
MIN()
DISTINCT
BETWEEN
IN
LIKE
AS
```

---

## 💡 O que foi aprendido

A atividade ajudou a compreender como utilizar SQL para consultar e analisar informações de um banco de dados.

Também foi praticado o uso de filtros, ordenações e funções matemáticas para obter informações específicas sobre as vendas.

Além disso, foram realizados comandos de inserção, alteração e exclusão de registros, reforçando a importância de utilizar `WHERE` corretamente para evitar alterações em toda a tabela.

---

## 📁 Arquivos

```text
📦 Atividade
 ├── 📄 banco_vendas_valeferramentas.sql
 └── 📄 README.md
```

---

## 👨‍💻 Conclusão

A atividade permitiu aplicar na prática os principais comandos SQL estudados, desde consultas simples até cálculos e manutenção dos dados.

Com isso, foi possível desenvolver uma melhor compreensão sobre como bancos de dados podem ser utilizados para armazenar, consultar, analisar e modificar informações.

```

Esse README já está em **um único bloco Markdown**, então é só copiar tudo para o seu `README.md` no VS Code.
```
![alt text](<Captura de tela 2026-09-15 083622.png>)
![alt text](<Captura de tela 2026-09-15 085303.png>)
![alt text](<Captura de tela 2026-09-15 090014.png>)
![alt text](<Captura de tela 2026-09-15 100737.png>)
![alt text](<Captura de tela 2026-09-15 100807.png>)
![alt text](<Captura de tela 2026-09-15 100847.png>)
![alt text](<Captura de tela 2026-09-15 100914.png>)
![alt text](<Captura de tela 2026-09-15 101001.png>)
![alt text](<Captura de tela 2026-09-15 101126.png>)
![alt text](<Captura de tela 2026-09-15 101216.png>)
![alt text](<Captura de tela 2026-09-15 101259.png>)
![alt text](<Captura de tela 2026-09-15 101338.png>)
![alt text](<Captura de tela 2026-09-15 101421.png>)
![alt text](<Captura de tela 2026-09-15 101508.png>)
![alt text](<Captura de tela 2026-09-15 101654.png>)
![alt text](<Captura de tela 2026-09-15 101745.png>)
![alt text](<Captura de tela 2026-09-15 101831.png>)
![alt text](<Captura de tela 2026-09-15 101934.png>)
![alt text](<Captura de tela 2026-09-15 102025.png>)
![alt text](<Captura de tela 2026-09-15 102111.png>)
![alt text](<Captura de tela 2026-09-15 102304.png>)
![alt text](<Captura de tela 2026-09-15 102403.png>)
![alt text](<Captura de tela 2026-09-15 102435.png>)
![alt text](<Captura de tela 2026-09-15 102507.png>)
![alt text](<Captura de tela 2026-09-15 102533.png>)
![alt text](<Captura de tela 2026-09-15 102558.png>)
![alt text](<Captura de tela 2026-09-15 102640.png>)