# Import Plan

## Objetivo

Documentar a estratégia de importação dos arquivos CSV para o PostgreSQL.

---

## Fonte dos Dados

Dataset

Brazilian E-Commerce Public Dataset by Olist

Formato

CSV

Codificação

UTF-8

Separador

,

---

## Ordem da Importação

1. Customers

2. Sellers

3. Products

4. Category Translation

5. Orders

6. Order Items

7. Order Payments

8. Order Reviews

9. Geolocation

---

## Estratégia

Cada tabela será criada manualmente no PostgreSQL.

Após a criação das tabelas:

- Importar os arquivos CSV
- Validar quantidade de registros
- Validar chaves primárias
- Validar integridade
- Criar índices necessários

---

## Tipos de Dados

Os tipos serão definidos manualmente utilizando:

VARCHAR

DATE

TIMESTAMP

NUMERIC

INTEGER

BOOLEAN

---

## Validação

Após cada importação serão executadas consultas SQL para validar:

Quantidade de registros

Valores nulos

Duplicidades

Integridade referencial

---

## Resultado Esperado

Banco operacional íntegro e preparado para a construção do Data Warehouse.