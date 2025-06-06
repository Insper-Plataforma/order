# Setup e dependências

Este módulo define apenas a **interface REST `OrderController`** e os DTOs relacionados.

---

## Como compilar

```bash
mvn clean install
```

---

## Requisitos

- Java 17+
- Lombok
- Spring Web
- OpenFeign

---

## Dependências no `pom.xml`

- `spring-boot-starter-web`
- `spring-cloud-starter-openfeign`
- `lombok`

---

## Como usar

Essa interface deve ser **importada** e **implementada por um serviço** como o `order-service`. Em qualquer outro microsserviço, pode ser utilizada como **Feign Client** para acessar endpoints do `order`.

```java
@FeignClient(name = "order", url = "http://order:8080")
public interface OrderController {
    // ...
}
```

---

## Observações

- O header `id-account` deve ser enviado em todas as requisições para identificar o usuário autenticado.
- O DTO `OrderItemOut` depende de `ProductOut`, que deve ser importado do módulo `product`.

---