Projeto Banco de Dados — Teste SQL

Este projeto foi desenvolvido como um **teste e estudo pessoal sobre SQL e bancos de dados**, com o objetivo de compreender melhor a criação, organização e relacionamento entre diferentes tabelas.

Durante o desenvolvimento, foram explorados conceitos importantes de banco de dados, como **chaves primárias, chaves estrangeiras, relacionamentos entre tabelas e manipulação de dados**.

Objetivo

O principal objetivo deste projeto é colocar em prática conhecimentos relacionados a:

* Criação de bancos de dados;
* Criação e organização de tabelas;
* Definição de **chaves primárias (PRIMARY KEY)**;
* Definição de **chaves estrangeiras (FOREIGN KEY)**;
* Relacionamento entre tabelas;
* Inserção e manipulação de dados;
* Consultas utilizando SQL;
* Estruturação e organização de um banco de dados.

Tecnologias utilizadas

* **SQL**
* Banco de dados utilizado: SQLite

Sobre o projeto

Este banco de dados foi criado exclusivamente para fins de **aprendizado e testes**.

A ideia é utilizar uma estrutura simples para entender, na prática, como os dados são armazenados e como diferentes tabelas podem se relacionar por meio de chaves primárias e estrangeiras.

O projeto também serve como uma forma de praticar comandos SQL e compreender melhor a estrutura de um banco de dados relacional.

Conceitos estudados

### Primary Key

A **chave primária** é utilizada para identificar de forma única cada registro dentro de uma tabela.

Exemplo:

ATTENDEE_ID


### Foreign Key

A **chave estrangeira** é utilizada para criar um relacionamento entre tabelas, fazendo referência à chave primária de outra tabela.

Exemplo:

PRIMARY_CONTENT_ATTENDEE_ID  OU ATTENDEE_ID


Estrutura

A estrutura do projeto contém os arquivos necessários para a criação e manipulação do banco de dados.

TABLE
- ATTENDEE
- COMPANY
- PRESENTATION
- PRESENTATION_ATTENDANCE
- ROOM


 Como utilizar

1. Baixe o arquivo zip clicando em CODE no repositório e depois extraia ele da pasta compactada:

2. Abra o arquivo SQL no seu sistema de gerenciamento de banco de dados.

3. Execute os comandos presentes no arquivo.

4. Explore as tabelas, relacionamentos e consultas disponíveis no projeto.

Observação

Este é um **projeto de estudo**, criado para praticar e compreender melhor os conceitos de SQL e bancos de dados relacionais.

Novas tabelas, relacionamentos e consultas poderão ser adicionados conforme o aprendizado evoluir.

---

**Projeto desenvolvido para fins de aprendizado e prática com SQL.**


EXEMPLO DE USO EM PRÁTICA: PARA VOCÊ VER TODAS AS APRESENTAÇÕES DO DIA PEGANDO O NOME DOS APRESENTADORES, DAS EMPRESAS E DESCRIÇÃO DELAS COM O HORÁRIO DE COMEÇO E FIM, CAPACIDADE DE CADEIRAS E O ANDAR DA APRESENTAÇÃO E VER SE A PESSOA É OU NÃO VIP
EX:

SELECT PRESENTATION.PRESENTATION_ID,
ATTENDEE.FIRST_NAME,
ATTENDEE.LAST_NAME,
COMPANY.NAME AS COMPANY_NAME,
COMPANY.DESCRIPTION,
ROOM.FLOOR_NUMBER,
ROOM.SEAT_CAPACITY,
START_TIME,
END_TIME,
PRESENTATION_ATTENDANCE.TICKET_ID,
ATTENDEE.VIP FROM PRESENTATION
INNER JOIN COMPANY
ON PRESENTATION.BOOKED_COMPANY_ID = COMPANY.COMPANY_ID
INNER JOIN ROOM
ON PRESENTATION.BOOKED_ROOM_ID = ROOM.ROOM_ID
INNER JOIN PRESENTATION_ATTENDANCE
ON PRESENTATION.PRESENTATION_ID = PRESENTATION_ATTENDANCE.PRESENTATION_ID
INNER JOIN ATTENDEE
ON PRESENTATION_ATTENDANCE.ATTENDEE_ID = ATTENDEE.ATTENDEE_ID
