# Interface Order

A interface `OrderController` define os contratos REST do microsserviço de pedidos (`order-service`).

Ela é exposta como um **Feign Client** que permite a criação e consulta de pedidos, incluindo:

- Criar um novo pedido
- Buscar todos os pedidos
- Buscar um pedido específico pelo ID

Essa interface é implementada no serviço `order-service`.

---

## Interface Java

```java
@FeignClient(name = "order", url = "http://order:8080")
public interface OrderController {
    //
}
```