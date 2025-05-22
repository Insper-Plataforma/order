# Entidades

## `OrderIn`

Representa um pedido de entrada.

```java
record OrderIn(
    List<OrderItemIn> items
)
```

- `items`: Lista de itens do pedido.

## `OrderItemIn`

Item individual do pedido de entrada.

```java
record OrderItemIn(
    String idProduct,
    int quantity
)
```

- `idProduct`: ID do produto.
- `quantity`: Quantidade do produto.

## `OrderOut`

Retorno completo de um pedido.

```java
record OrderOut(
    String id,
    Date date,
    List<OrderItemOut> items,
    Double total
)
```

- `id`: ID do pedido.
- `date`: Data do pedido.
- `items`: Lista de itens do pedido.
- `total`: Valor total do pedido.

## `OrderItemOut`

Item do pedido com informações do produto.

```java
record OrderItemOut(
    ProductOut product,
    String id,
    int quantity,
    Double total
)
```

- `product`: Produto associado ao item.
- `id`: ID do item.
- `quantity`: Quantidade do item.
- `total`: Valor total do item.

