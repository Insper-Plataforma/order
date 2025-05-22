## Endpoints

### `POST /order`

Cria um novo pedido para o usuário autenticado.

- **Request body**: [`OrderIn`](./entidades.md#orderin)
- **Header**: `id-account`
- **Response**: [`OrderOut`](./entidades.md#orderout)

---

### `GET /order`

Retorna todos os pedidos da base.

- **Response**: `List<OrderOut>`

---

### `GET /order/{idOrder}`

Busca os detalhes de um pedido específico.

- **Path param**: `idOrder`
- **Header**: `id-account`
- **Response**: [`OrderOut`](./entidades.md#orderout)

---
