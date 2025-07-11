# Spring RabbitMQ Demo

Este projeto é um exemplo básico de integração entre Spring Boot e RabbitMQ, baseado no guia oficial do Spring:  
https://spring.io/guides/gs/messaging-rabbitmq

## O que ele faz?

- Envia mensagens para uma exchange do RabbitMQ.
- Consome mensagens de uma fila vinculada a essa exchange.
- Demonstra o uso de `RabbitTemplate`, `Receiver` e `MessageListenerAdapter`.

## Como rodar

### Pré-requisitos

- Java 17+
- Docker (para rodar o RabbitMQ)
- Maven (ou `mvnw` wrapper)

### Passos

1. Suba o RabbitMQ com Management UI via Docker:

```bash
docker-compose up -d
```

2. Compile e rode o projeto:

```bash
./mvnw clean package
java -jar target/messaging-rabbitmq-0.0.1-SNAPSHOT.jar
```

3. Você verá logs no console indicando que a mensagem foi enviada e recebida.

4. Acesse o painel de administração do RabbitMQ em http://localhost:15672  
Usuário: `myuser`  
Senha: `secret`

## Configurações

As configurações do RabbitMQ estão no arquivo `application.properties` ou via variáveis de ambiente:

```properties
spring.rabbitmq.host=rabbitmq
spring.rabbitmq.port=5672
spring.rabbitmq.username=myuser
spring.rabbitmq.password=secret
```

## Referências

- [Spring RabbitMQ Guide](https://spring.io/guides/gs/messaging-rabbitmq)
- [RabbitMQ Management UI](http://localhost:15672)

---

Feito para estudo e aprendizado sobre mensageria com RabbitMQ e Spring Boot.
