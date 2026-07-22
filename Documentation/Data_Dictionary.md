# Data Dictionary

## Tabela: Customers

Armazena informações dos clientes.

Quantidade de registros: 99441


| Campo         | Tipo    | Descrição                       |
|---------------|---------|---------------------------------|
| customer_id   | VARCHAR | Identificador único             |
| customer_unique_id | VARCHAR | Identificador permanente do cliente |
| customer_city | VARCHAR | Cidade                          |
| customer_state | CHAR(2) | Estado                          |

Relacionamentos: 
 | Tabela | Campo de Junção |
 |--------|------------------|
 | orders | customer_id      |

## Tabela: Geolocation
Armazena informações de geolocalização.

Quantidade de registros: 1000163

| Campo         | Tipo    | Descrição                       |
|---------------|---------|---------------------------------|
| geolocation_zip_code_prefix | INT     | Identificador único             |
| geolocation_lat  | DECIMAL | Latitude                        |
| geolocation_lng  | DECIMAL | Longitude                       |
| geolocation_city | VARCHAR | Cidade                          |
| geolocation_state | VARCHAR | Estado                         |

Relacionamentos:


## Tabela: Orders_Items

Armazena informações dos pedidos.

Quantidade de registros: 112650

| Campo         | Tipo    | Descrição                       |
|---------------|---------|---------------------------------|
| order_id      | VARCHAR | Identificador único do pedido    |
| order_item_id | VARCHAR | Identificador único do item      |
| product_id    | VARCHAR | Identificador do produto        |
| seller_id     | VARCHAR | Identificador do vendedor       |
| shipping_limit_date | DATETIME | Data limite de envio       |
| price         | DECIMAL | Preço do item                   |
| freight_value | DECIMAL | Valor do frete                  |

Relacionamentos:
 | Tabela | Campo de Junção |
 |--------|------------------|
 | products | product_id      |
 | sellers  | seller_id       |
 | orders   | order_id       |

## Tabela: Order_payments

Armazena informações dos pagamentos dos pedidos.

Quantidade de registros: 103886

| Campo         | Tipo    | Descrição                       |
|---------------|---------|---------------------------------|
| order_id      | VARCHAR | Identificador único do pedido    |
| payment_sequential    | INT | Identificador único do pagamento  |
| payment_type  | VARCHAR | Tipo de pagamento               |
| payment_installments | INT | Número de parcelas               |
| payment_value | DECIMAL | Valor do pagamento              |

Relacionamentos:
 | Tabela | Campo de Junção |
 |--------|------------------|
 | orders | order_id       |

## Tabela: Order_reviews
Armazena informações das avaliações dos pedidos.

Quantidade de registros: 99441

| Campo         | Tipo    | Descrição                       |
|---------------|---------|---------------------------------|
| review_id     | VARCHAR | Identificador único da avaliação  |
| order_id      | VARCHAR | Identificador único do pedido    |
| review_score  | INT     | Nota da avaliação               |
| review_comment_title | TEXT    | Título do comentário da avaliação         |
| review_comment_message | TEXT    | Comentário da avaliação         | 
| review_creation_date | DATETIME | Data de criação da avaliação         |
| review_answer_timestamp | DATETIME | Data da resposta da avaliação         |

Relacionamentos:
 | Tabela | Campo de Junção |
 |--------|------------------|
 | orders | order_id       |

## Tabela: Orders

Armazena informações dos pedidos.

Quantidade de registros: 99441

| Campo         | Tipo    | Descrição                       |
|---------------|---------|---------------------------------|
| order_id      | VARCHAR | Identificador único do pedido    |
| customer_id   | VARCHAR | Identificador do cliente        |
| order_status  | VARCHAR | Status do pedido                |
| order_purchase_timestamp | DATETIME | Data da compra               |
| order_approved_at | DATETIME | Data da aprovação do pedido   |
| order_delivered_carrier_date | DATETIME | Data da entrega do pedido     |
| order_delivered_customer_date | DATETIME | Data da entrega ao cliente    |
| order_estimated_delivery_date | DATETIME | Data estimada de entrega ao cliente |

Relacionamentos:
 | Tabela | Campo de Junção |
 |--------|------------------|
 | customers | customer_id   |
 | order_items | order_id    |
 | order_payments | order_id  |
 | order_reviews | order_id   |

## Tabela: Products
Armazena informações dos produtos.

Quantidade de registros: 32951

| Campo         | Tipo    | Descrição                       |
|---------------|---------|---------------------------------|
| product_id    | VARCHAR | Identificador único do produto   |
| product_category_name | VARCHAR | Categoria do produto           |
| product_name_length  | INT | Comprimento do nome do produto   |
| product_description_length | INT | Comprimento da descrição do produto |
| product_photos_qty | DECIMAL | Quantidade de fotos do produto   |
| product_weight_g | DECIMAL | Peso do produto em gramas       |
| product_length_cm | DECIMAL | Comprimento do produto em centímetros |
| product_height_cm | DECIMAL | Altura do produto em centímetros |
| product_width_cm | DECIMAL | Largura do produto em centímetros |

Relacionamentos:
 | Tabela | Campo de Junção |
 |--------|------------------|
 | order_items | product_id   |

## Tabela: Sellers
Armazena informações dos vendedores.

Quantidade de registros: 3095

| Campo         | Tipo    | Descrição                       |
|---------------|---------|---------------------------------|
| seller_id     | VARCHAR | Identificador único do vendedor  |
| seller_zip_code_prefix  | VARCHAR | CEP do vendedor                 |
| seller_city   | VARCHAR | Cidade do vendedor              |
| seller_state  | VARCHAR | Estado do vendedor              |

Relacionamentos:
 | Tabela | Campo de Junção |
 |--------|------------------|
 | products | seller_id     |

## Tabela: Product_category_name_translation
Armazena informações sobre a tradução dos nomes das categorias de produtos.

Quantidade de registros: 100

| Campo         | Tipo    | Descrição                       |
|---------------|---------|---------------------------------|
| language      | VARCHAR | Idioma da tradução              |
| translated_name | VARCHAR | Nome traduzido da categoria     |

Relacionamentos:

