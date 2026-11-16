# Fórmula 1 MySQL

Projeto acadêmico de banco de dados relacional que conecta países, equipes, pilotos e Grandes Prêmios. A base reúne pilotos de épocas diferentes, com afiliações, grids e salários ilustrativos.

Estrutura do banco

Tabela Finalidade

`paises` Registra os países associados a pilotos, equipes e corridas.
`equipes` Armazena a sigla, o nome e o país de cada equipe.
`pilotos` Registra os pilotos e seus vínculos com países e equipes.
`corridas` Armazena os Grandes Prêmios, o país-sede e a quantidade de voltas.
`participantes` Relaciona pilotos e corridas e registra a posição de largada.

Em `participantes`, a chave primária composta impede que o mesmo piloto seja inscrito duas vezes no mesmo GP. A restrição `UNIQUE` impede que dois pilotos ocupem a mesma posição de largada naquela corrida.

O que o script demonstra

- Montagem do grid de largada com `INNER JOIN` entre três tabelas.
- Contagem de pilotos por país com `COUNT` e `GROUP BY`.
- Inclusão da coluna `salario` com `ALTER TABLE` e preenchimento com `UPDATE`.
- Filtro por faixa salarial com `BETWEEN` e cálculo de médias com `AVG`.

Como executar

1. Conecte-se a um servidor MySQL pelo MySQL Workbench.
2. Abra e execute o arquivo [`formula1.sql`](formula1.sql) para criar o banco `db_formula1`, carregar os dados e rodar as consultas.
3. Confira o último resultado. O grid ilustrativo do GP do Brasil deve mostrar cinco pilotos, de Ayrton Senna em 1º a Emerson Fittipaldi em 5º.

Se `db_formula1` já contiver as tabelas do projeto, use um nome de banco livre nas instruções `CREATE DATABASE` e `USE` antes de executar o script completo.
