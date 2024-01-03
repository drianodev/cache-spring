# CacheSpring - Demonstração de Caching com Spring Boot

Este projeto é uma demonstração simples de como usar o mecanismo de cache do Spring Boot em conjunto com o Redis para melhorar o desempenho de operações de busca repetidas.

## Visão Geral

O projeto consiste em uma aplicação Spring Boot que possui um serviço (`ProductService`) para recuperar informações de produtos. A aplicação possui duas abordagens para obter informações de produtos: uma busca direta (`getById`) e uma busca com suporte a cache (`getByIdWithCache`) usando a anotação `@Cacheable` do Spring.

## Estrutura do Projeto

- **`CacheSpringApplication`:** Classe principal que inicia a aplicação Spring Boot. Contém um `ApplicationRunner` para demonstrar o funcionamento do cache.

- **`Product` Record:** Representa um produto com identificação, nome e descrição.

- **`ProductService` Classe:** Fornece métodos para obter informações sobre produtos. Demonstra a diferença entre busca direta e busca com suporte a cache.

## Configuração do Redis

O projeto está configurado para usar o Redis como provedor de cache. Para executar o Redis em um contêiner Docker, você pode usar os seguintes comandos:

```bash
docker run --name my-redis -p 6379:6379 -d redis
```

## Executando a Aplicação

1. Clone o repositório para a sua máquina local.
2. Execute o Redis em um contêiner Docker usando o comando fornecido acima.
3. Execute o aplicativo Spring Boot.

## Demonstrações

A classe `CacheSpringApplication` contém uma instância de `ProductService` e utiliza o `ApplicationRunner` para realizar demonstrações. Você verá a diferença no tempo de resposta entre as operações com e sem cache.

## Dependências

O projeto utiliza as seguintes dependências principais:

- `spring-boot-starter`: Dependência principal do Spring Boot.
- `spring-boot-starter-cache`: Fornece suporte básico para caching no Spring Boot.
- `spring-boot-starter-data-redis`: Adiciona suporte para integração com o Redis.
- `spring-boot-starter-test`: Dependência para testes no ambiente Spring Boot.

## Configuração do Redis no Projeto

A configuração para usar o Redis como provedor de cache está no arquivo `application.properties`:

```properties
spring.cache.type=redis
```

Isso indica ao Spring Boot para usar o Redis como o provedor de cache.
