
## Objetivo

Documentar o relacionamento entre as entidades do banco de dados operacional do Olist.

---

# Visão Geral

O banco de dados representa um marketplace onde clientes realizam pedidos contendo um ou mais produtos vendidos por diferentes vendedores.

Cada pedido pode possuir:

- um cliente
- um ou mais itens
- um pagamento
- uma avaliação

Os produtos pertencem a categorias e cada vendedor é responsável pelos itens comercializados.

---

# Entidades

## Customers

Representa os clientes cadastrados na plataforma.

Primary Key

customer_id

Relacionamentos

Customers (1) ---- (N) Orders

---

## Orders

Representa os pedidos realizados pelos clientes.

Primary Key

order_id

Foreign Keys

customer_id

Relacionamentos

Orders (1) ---- (N) Order Items

Orders (1) ---- (1) Order Payments

Orders (1) ---- (1) Order Reviews

---

## Order Items

Representa cada produto vendido dentro de um pedido.

Primary Key

(order_id + order_item_id)

Foreign Keys

order_id

product_id

seller_id

Relacionamentos

Order Items (N) ---- (1) Products

Order Items (N) ---- (1) Sellers

---

## Products

Cadastro de produtos.

Relacionamentos

Products (N) ---- (1) Categories

---

## Sellers

Cadastro de vendedores.

---

## Order Payments

Informações financeiras dos pedidos.

---

## Order Reviews

Avaliações dos clientes.

---

## Geolocation

Localização baseada no CEP.

---

## Category Translation

Tabela de tradução do nome das categorias.