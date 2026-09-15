````markdown
# 📊 Atividade SQL — Banco de Dados Vale Ferramentas

## 📌 Sobre a atividade

Nesta atividade foi desenvolvido um conjunto de consultas SQL utilizando um banco de dados fictício da empresa **Vale Ferramentas**.

A atividade tem como objetivo praticar comandos SQL para **consultar, filtrar, ordenar, calcular, inserir, alterar e excluir informações** de uma tabela de vendas.

O banco de dados utilizado possui **10.000 registros de vendas**, permitindo trabalhar com uma quantidade maior de informações e aplicar diferentes formas de consulta.

Durante a atividade foram utilizadas funções e comandos que já haviam sido estudados anteriormente, como `SELECT`, `INSERT`, `UPDATE`, `DELETE`, `WHERE`, `ORDER BY`, `SUM`, `MAX`, `MIN`, `AVG` e cálculos utilizando `AS`.

Além desses comandos, foram introduzidos novos recursos:

- `LIMIT`
- `COUNT(*)`
- `DISTINCT`
- `BETWEEN`
- `IN`
- `LIKE`

---

# 🎯 Objetivos

Os principais objetivos da atividade foram:

- Aprender a consultar informações de uma tabela;
- Visualizar uma quantidade limitada de registros;
- Contar registros utilizando funções de agregação;
- Encontrar valores diferentes sem repetições;
- Filtrar informações utilizando diferentes condições;
- Trabalhar com intervalos de valores e datas;
- Pesquisar informações utilizando listas de valores;
- Realizar pesquisas utilizando padrões de texto;
- Ordenar resultados de forma crescente ou decrescente;
- Realizar cálculos diretamente nas consultas;
- Calcular o valor bruto e líquido das vendas;
- Utilizar funções como `SUM()`, `AVG()`, `MAX()`, `MIN()` e `COUNT()`;
- Inserir novos registros;
- Alterar informações existentes;
- Excluir registros;
- Conferir se as alterações foram realizadas corretamente.

---

# 🗃️ Estrutura do banco de dados

A tabela principal utilizada na atividade é:

```sql
vendas
````

Ela armazena informações relacionadas às vendas realizadas pela empresa.

Entre os principais campos utilizados estão:

| Campo                 | Descrição                         |
| --------------------- | --------------------------------- |
| `id_venda`            | Identificação única da venda      |
| `data_venda`          | Data em que a venda foi realizada |
| `nome_cliente`        | Nome do cliente                   |
| `cidade`              | Cidade do cliente                 |
| `estado`              | Estado do cliente                 |
| `categoria`           | Categoria do produto              |
| `produto`             | Nome do produto vendido           |
| `quantidade`          | Quantidade de unidades vendidas   |
| `preco_unitario`      | Preço de cada unidade             |
| `desconto_percentual` | Percentual de desconto aplicado   |
| `forma_pagamento`     | Forma utilizada para o pagamento  |
| `vendedor`            | Vendedor responsável pela venda   |
| `status_entrega`      | Situação da entrega               |

---

# 🧠 Novos comandos estudados

## 🔹 LIMIT

O `LIMIT` é utilizado para limitar a quantidade de registros apresentados no resultado.

Por exemplo:

```sql
SELECT *
FROM vendas
LIMIT 20;
```

Nesse caso, apenas os **20 primeiros registros** serão exibidos.

Isso é bastante útil quando uma tabela possui milhares de registros e não queremos visualizar todos de uma vez.

---

## 🔹 COUNT()

O `COUNT(*)` é utilizado para contar a quantidade de registros existentes.

Exemplo:

```sql
SELECT COUNT(*)
FROM vendas;
```

Também podemos utilizar `AS` para dar um nome mais claro ao resultado:

```sql
SELECT COUNT(*) AS total_de_vendas
FROM vendas;
```

---

## 🔹 DISTINCT

O `DISTINCT` remove valores repetidos de uma consulta.

Exemplo:

```sql
SELECT DISTINCT categoria
FROM vendas;
```

Dessa forma, cada categoria será exibida apenas uma vez.

---

## 🔹 BETWEEN

O `BETWEEN` é utilizado para pesquisar valores dentro de um intervalo.

Exemplo:

```sql
SELECT *
FROM vendas
WHERE quantidade BETWEEN 10 AND 20;
```

Nesse caso, serão encontradas vendas cuja quantidade esteja entre **10 e 20**, incluindo os dois valores.

Também pode ser utilizado com datas:

```sql
WHERE data_venda BETWEEN '2026-03-01' AND '2026-03-31'
```

---

## 🔹 IN

O `IN` permite verificar se um valor pertence a uma lista.

Exemplo:

```sql
SELECT *
FROM vendas
WHERE cidade IN ('Americana', 'Campinas', 'Piracicaba');
```

Isso é uma forma mais prática de utilizar várias condições com `OR`.

---

## 🔹 LIKE

O `LIKE` é utilizado para pesquisar textos utilizando padrões.

Exemplo:

```sql
SELECT *
FROM vendas
WHERE nome_cliente LIKE 'Metalúrgica%';
```

O símbolo `%` representa qualquer sequência de caracteres.

Nesse exemplo, serão encontrados clientes cujo nome **começa com "Metalúrgica"**.

---

# 📚 Questões realizadas

A atividade foi dividida em **5 blocos**, contendo um total de **20 questões**.

---

# 🟦 BLOCO 1 — CONHECENDO A BASE

## Questão 01 — Visualização dos registros

Foi utilizada a consulta:

```sql
SELECT *
FROM vendas
LIMIT 20;
```

O objetivo foi visualizar todas as colunas das **20 primeiras vendas cadastradas**.

O `*` representa todas as colunas da tabela e o `LIMIT 20` limita o resultado para os primeiros 20 registros.

---

## Questão 02 — Contagem de vendas

Foi utilizado:

```sql
SELECT COUNT(*) AS total_de_vendas
FROM vendas;
```

O objetivo foi descobrir quantas vendas existem no banco de dados.

O resultado esperado inicialmente é de **10.000 registros**.

O `AS total_de_vendas` foi utilizado para deixar o resultado mais fácil de entender.

---

## Questão 03 — Categorias de produtos

Foi utilizada a consulta:

```sql
SELECT DISTINCT categoria
FROM vendas
ORDER BY categoria ASC;
```

O `DISTINCT` evita que uma mesma categoria apareça várias vezes.

O `ORDER BY categoria ASC` organiza as categorias em ordem alfabética crescente.

---

## Questão 04 — Cidades e estados

Foi utilizada:

```sql
SELECT DISTINCT cidade, estado
FROM vendas
ORDER BY cidade ASC;
```

O objetivo foi descobrir em quais cidades e estados existem clientes.

O `DISTINCT` garante que uma mesma combinação de cidade e estado não apareça repetidamente.

---

# 🟩 BLOCO 2 — FILTRANDO COM WHERE

## Questão 05 — Categoria EPI

Consulta utilizada:

```sql
SELECT id_venda, produto, quantidade, preco_unitario
FROM vendas
WHERE categoria = 'EPI';
```

O objetivo foi listar somente as vendas pertencentes à categoria **EPI**.

Foram exibidos:

* ID da venda;
* Produto;
* Quantidade;
* Preço unitário.

---

## Questão 06 — Vendas grandes e caras

Consulta utilizada:

```sql
SELECT id_venda, produto, quantidade, preco_unitario
FROM vendas
WHERE quantidade > 40
AND preco_unitario > 300;
```

Foram procuradas vendas que atendam **às duas condições ao mesmo tempo**:

* Quantidade maior que 40;
* Preço unitário maior que R$ 300,00.

O operador `AND` exige que as duas condições sejam verdadeiras.

---

## Questão 07 — Região de Campinas

Foi utilizado o comando `IN`:

```sql
SELECT id_venda, nome_cliente, cidade, produto
FROM vendas
WHERE cidade IN ('Americana', 'Campinas', 'Piracicaba');
```

O objetivo foi encontrar vendas realizadas para clientes dessas três cidades:

* Americana;
* Campinas;
* Piracicaba.

O `IN` facilita a utilização de várias possibilidades dentro do mesmo filtro.

---

## Questão 08 — Vendas de março de 2026

Foi utilizado o `BETWEEN`:

```sql
SELECT id_venda, data_venda, nome_cliente, produto
FROM vendas
WHERE data_venda BETWEEN '2026-03-01' AND '2026-03-31'
ORDER BY data_venda ASC;
```

A consulta retorna as vendas realizadas entre o dia **01/03/2026 e 31/03/2026**.

Os resultados são organizados pela data, começando pelas vendas mais antigas.

---

## Questão 09 — Clientes Metalúrgicos

Foi utilizado o `LIKE`:

```sql
SELECT *
FROM vendas
WHERE nome_cliente LIKE 'Metalúrgica%';
```

O objetivo foi encontrar clientes cujo nome começa com:

```text
Metalúrgica
```

O `%` permite que existam outros caracteres depois dessa palavra.

---

## Questão 10 — Cancelamentos

Consulta utilizada:

```sql
SELECT *
FROM vendas
WHERE status_entrega = 'Cancelado'
AND forma_pagamento IN ('Boleto', 'PIX');
```

Foram pesquisadas vendas que:

* Possuem status `Cancelado`;
* Foram pagas utilizando `Boleto` ou `PIX`.

Nessa consulta foram combinados `WHERE`, `AND` e `IN`.

---

# 🟨 BLOCO 3 — ORDENANDO OS RESULTADOS

## Questão 11 — Maiores preços

Foi utilizada:

```sql
SELECT id_venda, produto, preco_unitario AS preco
FROM vendas
ORDER BY preco_unitario DESC
LIMIT 10;
```

O objetivo foi encontrar os **10 maiores preços unitários**.

O `DESC` faz com que os maiores valores apareçam primeiro.

O `LIMIT 10` mostra somente os dez primeiros resultados.

---

## Questão 12 — Vendas mais antigas

Consulta utilizada:

```sql
SELECT id_venda, data_venda, produto, nome_cliente
FROM vendas
WHERE categoria = 'Instrumentos de Medição'
ORDER BY data_venda ASC
LIMIT 5;
```

Primeiro são filtradas apenas as vendas da categoria:

```text
Instrumentos de Medição
```

Depois, elas são organizadas da mais antiga para a mais recente.

Por fim, são mostradas apenas as **5 primeiras**.

---

## Questão 13 — Extrato da Ana Ribeiro

Foi utilizada:

```sql
SELECT *
FROM vendas
WHERE vendedor = 'Ana Ribeiro'
ORDER BY data_venda DESC, quantidade DESC
LIMIT 20;
```

A consulta mostra as vendas realizadas pela vendedora **Ana Ribeiro**.

A ordenação funciona da seguinte forma:

1. Data mais recente primeiro;
2. Em caso de empate na data, maior quantidade primeiro;
3. Apenas as 20 primeiras vendas são exibidas.

---

# 🟥 BLOCO 4 — CÁLCULOS E FUNÇÕES

## Questão 14 — Valor bruto

O valor bruto de uma venda é calculado multiplicando:

```text
quantidade × preço unitário
```

A consulta utilizada foi:

```sql
SELECT
    id_venda,
    produto,
    quantidade,
    preco_unitario,
    quantidade * preco_unitario AS valor_bruto
FROM vendas
WHERE categoria = 'Ferramentas Elétricas'
ORDER BY valor_bruto DESC
LIMIT 10;
```

O resultado mostra as **10 maiores vendas brutas** da categoria `Ferramentas Elétricas`.

O `AS valor_bruto` cria um nome para o resultado do cálculo.

---

## Questão 15 — Valor líquido

Nesta questão foi considerado o desconto.

A fórmula utilizada foi:

```text
valor bruto × (1 - desconto / 100)
```

A consulta:

```sql
SELECT
    id_venda,
    produto,
    quantidade,
    preco_unitario,
    desconto_percentual,
    quantidade * preco_unitario AS valor_bruto,
    quantidade * preco_unitario
    * (1 - desconto_percentual / 100) AS valor_liquido
FROM vendas
WHERE desconto_percentual > 0
ORDER BY valor_liquido DESC
LIMIT 10;
```

Somente vendas que possuem desconto são consideradas.

O resultado apresenta as **10 maiores vendas pelo valor líquido**.

---

## Questão 16 — Faturamento bruto

### 16a — Faturamento total

Foi utilizada a função `SUM()`:

```sql
SELECT
    SUM(quantidade * preco_unitario) AS faturamento_bruto_total
FROM vendas;
```

A consulta soma o valor bruto de todas as vendas.

---

### 16b — Faturamento da categoria EPI

Foi utilizada:

```sql
SELECT
    SUM(quantidade * preco_unitario) AS faturamento_bruto_epi
FROM vendas
WHERE categoria = 'EPI';
```

Nesse caso, a soma considera somente as vendas da categoria **EPI**.

---

## Questão 17 — Indicadores de São Paulo

Foi utilizada uma única consulta:

```sql
SELECT
    AVG(quantidade * preco_unitario) AS ticket_medio,
    MAX(quantidade * preco_unitario) AS maior_venda,
    MIN(quantidade * preco_unitario) AS menor_venda,
    COUNT(*) AS quantidade_de_vendas
FROM vendas
WHERE estado = 'SP';
```

Foram calculadas quatro informações:

* `AVG()` → ticket médio;
* `MAX()` → maior venda;
* `MIN()` → menor venda;
* `COUNT()` → quantidade de vendas.

A consulta considera somente clientes do estado de **São Paulo (SP)**.

---

# 🟪 BLOCO 5 — MANUTENÇÃO DOS DADOS

## Questão 18 — Inserção de uma nova venda

Foi utilizado o comando `INSERT INTO` para cadastrar uma nova venda.

O ID escolhido foi:

```text
10001
```

Esse número foi utilizado porque o ID da venda é uma chave primária e não é gerado automaticamente.

Depois da inserção, foi realizada uma consulta para confirmar o cadastro:

```sql
SELECT *
FROM vendas
WHERE id_venda = 10001;
```

Assim foi possível verificar se o novo registro realmente foi salvo.

---

## Questão 19 — Alteração do status

Após cadastrar a venda, o status da entrega foi alterado para:

```text
Cancelado
```

Foi utilizado:

```sql
UPDATE vendas
SET status_entrega = 'Cancelado'
WHERE id_venda = 10001;
```

O `WHERE` é muito importante nessa operação.

Sem ele, o comando poderia alterar o status de **todas as vendas da tabela**.

Depois do `UPDATE`, foi feito um `SELECT` para confirmar a alteração.

---

## Questão 20 — Exclusão da venda

Por último, a venda criada na questão 18 foi excluída:

```sql
DELETE FROM vendas
WHERE id_venda = 10001;
```

Depois foi utilizada a função `COUNT()`:

```sql
SELECT COUNT(*) AS total_de_vendas
FROM vendas;
```

O objetivo é confirmar que a venda criada foi removida e que a tabela voltou a possuir:

```text
10.000 registros
```

---

# 🛠️ Comandos SQL utilizados

Durante a atividade foram utilizados diversos comandos e recursos do SQL:

```text
SELECT
INSERT INTO
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
AND
```

---

# 📈 Principais conceitos aprendidos

## Consultas

O comando `SELECT` permite buscar informações armazenadas no banco de dados.

## Filtros

O `WHERE` permite selecionar somente os registros que atendem a determinadas condições.

## Ordenação

O `ORDER BY` permite organizar os resultados.

* `ASC` → crescente;
* `DESC` → decrescente.

## Funções de agregação

Foram utilizadas funções para analisar os dados:

| Função    | Utilidade              |
| --------- | ---------------------- |
| `COUNT()` | Conta registros        |
| `SUM()`   | Soma valores           |
| `AVG()`   | Calcula média          |
| `MAX()`   | Encontra o maior valor |
| `MIN()`   | Encontra o menor valor |

## Manipulação de dados

Também foram praticados comandos responsáveis por modificar o banco:

| Comando  | Função             |
| -------- | ------------------ |
| `INSERT` | Adiciona registros |
| `UPDATE` | Altera registros   |
| `DELETE` | Exclui registros   |

---

# ⚠️ Cuidados importantes

Durante a atividade também foi possível perceber alguns cuidados necessários ao trabalhar com banco de dados.

### UPDATE

Sempre utilizar `WHERE` quando a intenção for alterar apenas um registro.

```sql
UPDATE vendas
SET status_entrega = 'Cancelado'
WHERE id_venda = 10001;
```

### DELETE

Também é importante utilizar `WHERE` ao excluir um registro específico.

```sql
DELETE FROM vendas
WHERE id_venda = 10001;
```

Sem `WHERE`, o comando poderia afetar vários registros da tabela.

---

# 📂 Organização dos arquivos

O projeto pode ser organizado da seguinte forma:

```text
📁 Atividade SQL
│
├── 📄 banco_vendas_valeferramentas.sql
│
└── 📄 README.md
```

### banco_vendas_valeferramentas.sql

Arquivo contendo todas as consultas SQL utilizadas para responder às 20 questões.

### README.md

Arquivo responsável por apresentar e explicar a atividade, os objetivos, comandos utilizados e o que foi desenvolvido.

---

# 💻 Ferramentas utilizadas

* **Visual Studio Code** — edição do arquivo SQL;
* **PostgreSQL** — gerenciamento e execução das consultas SQL;
* **Git/GitHub** — armazenamento e versionamento do projeto.

---

# 📚 Conclusão

A atividade possibilitou colocar em prática diversos conceitos de SQL utilizando uma tabela com **10.000 vendas**.

Foram realizadas consultas para conhecer os dados, aplicar filtros, ordenar resultados, realizar cálculos e obter informações estatísticas.

Também foram praticados recursos como `LIMIT`, `COUNT()`, `DISTINCT`, `BETWEEN`, `IN` e `LIKE`, ampliando o conhecimento sobre consultas SQL.

Na parte final, foram utilizados `INSERT`, `UPDATE` e `DELETE`, permitindo praticar a manutenção dos registros do banco de dados.

Dessa forma, a atividade ajudou a compreender melhor como o SQL pode ser utilizado para **consultar, analisar e manipular informações armazenadas em um banco de dados**.

```

Esse está bem mais completo e já fica com cara de **README de projeto/atividade para GitHub**, incluindo a explicação das **20 questões**, os comandos, conceitos, cuidados e organização dos arquivos.
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