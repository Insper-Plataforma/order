# Order Interface

A interface `OrderController` define os contratos REST do microsserviço de pedidos (`order-service`).

Este módulo funciona como um **Feign Client** e permite operações como:

- Criar um novo pedido
- Buscar todos os pedidos
- Buscar um pedido específico pelo ID

Essa interface deve ser implementada pelo microsserviço `order-service`.

---

## Objetivo

Centralizar os contratos REST relacionados a pedidos, evitando duplicação de lógica HTTP e facilitando a comunicação entre microsserviços.

---

## Pacote

- `store.order` – Pacote principal que contém a interface Feign e os objetos de entrada e saída.

---

## Estrutura dos arquivos

| Arquivo                | Descrição                                                                |
| ---------------------- | ------------------------------------------------------------------------ |
| `OrderController.java` | Interface Feign com os endpoints disponíveis do microsserviço de pedidos |
| `OrderIn.java`         | Objeto de entrada para criação de pedidos                                |
| `OrderOut.java`        | Objeto de resposta contendo dados do pedido retornados pelo serviço      |
| `OrderItemIn.java`     | Objeto de entrada para criação dos itens dos pedidos                     |
| `OrderItemOut.java`    | Objeto de resposta contendo dados do pediso completo                     |

---

## Integração com Jenkins

Este projeto conta com um arquivo Jenkinsfile (na raiz do repositório) que define uma pipeline de integração contínua para compilar automaticamente o módulo sempre que houver alterações no repositório.

### Para que serve?

- Ao efetuar um push no repositório, o Jenkins detecta a mudança e executa esta pipeline.

- A etapa Build faz a compilação do projeto:

  1. Executa mvn clean install em modo batch (parâmetro -B), sem interação de usuário.

  2. Pulando os testes (-DskipTests), gera rapidamente o artefato (JAR) do módulo de interface.

- Caso a compilação falhe, o Jenkins sinaliza erro, impedindo que alterações com problemas sejam mescladas ou implantadas.

Dessa forma, a integração com Jenkins garante que o código da interface Feign esteja sempre compilando corretamente antes de ser utilizado por outros microsserviços.
