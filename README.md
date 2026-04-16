# DDD: Implementação de Repository e Testes

## Descrição

Este projeto implementa como exercício prático os conceitos de **Domain Driven Design (DDD)** e **Test Driven Development (TDD)**. O foco principal é completar a implementação da camada de infraestrutura, especificamente o repositório de pedidos (`OrderRepository`) que funciona conforme definido em sua interface.

## Estrutura do Projeto

O projeto segue a arquitetura de DDD com as seguintes camadas:

- **Domain**: Contém as entidades, interfaces de repositório e serviços de domínio
- **Infrastructure**: Contém as implementações de repositórios usando Sequelize ORM

### Diretório Principal

```
src/
├── domain/
│   ├── @shared/
│   ├── checkout/
│   │   ├── entity/
│   │   ├── factory/
│   │   ├── repository/
│   │   └── service/
│   ├── customer/
│   │   ├── entity/
│   │   ├── factory/
│   │   ├── repository/
│   │   └── value-object/
│   └── product/
│       ├── entity/
│       ├── event/
│       ├── factory/
│       ├── repository/
│       └── service/
└── infrastructure/
    ├── customer/
    │   └── repository/
    ├── order/
    │   └── repository/
    └── product/
        └── repository/
```

## Requisitos Técnicos

- **Linguagem**: TypeScript
- **Node.js**: v14 ou superior
- **NPM**: v6 ou superior

## Instalação de Dependências

Para instalar as dependências do projeto, execute:

```bash
npm install
```

## Rodando os Testes

Para rodar todos os testes do projeto, execute:

```bash
npm test
```

Para rodar apenas os testes do OrderRepository, execute:

```bash
npm test -- order.repository.spec.ts
```

### Saída Esperada

Todos os testes devem passar com sucesso:

```
Test Suites: 12 passed, 12 total
Tests:       43 passed, 43 total
Snapshots:   0 total
Time:        2.8s (aproximadamente)
```

## Implementação Realizada

### OrderRepository

A classe `OrderRepository` foi implementada com os seguintes métodos:

- **create(entity: Order)**: Cria um novo pedido no banco de dados
- **update(entity: Order)**: Atualiza um pedido existente
- **find(id: string)**: Busca um pedido pelo ID
- **findAll()**: Retorna todos os pedidos cadastrados

Todos os métodos retornam `Promise<void>` ou `Promise<Order>` conforme definido na interface.

### Testes Implementados

Os testes cobrem os seguintes cenários:

1. **should create a new order**: Valida a criação de um novo pedido
2. **should update an order**: Valida a atualização de um pedido existente
3. **should find an order by id**: Valida a busca de um pedido pelo ID
4. **should find all orders**: Valida a busca de todos os pedidos

## Stack Tecnológico

- **TypeScript**: Linguagem principal
- **Jest**: Framework de testes
- **Sequelize**: ORM para gerenciar dados
- **SQLite**: Banco de dados em memória para testes

## Como Executar

### Pré-requisitos

- Git instalado
- Node.js e npm instalados

### Passos

1. Clone o repositório:
```bash
git clone https://github.com/seu-usuario/fc-ddd-patterns-desafio.git
cd fc-ddd-patterns-desafio
```

2. Instale as dependências:
```bash
npm install
```

3. Execute os testes:
```bash
npm test
```

4. Verifique se todos os testes passam (verde)

## Critério de Aceite

✅ A classe `OrderRepository` implementa totalmente os métodos definidos em `OrderRepositoryInterface`

✅ Todos os testes passam quando executado `npm test`

✅ O código compila sem erros com `tsc`

✅ A implementação segue os padrões de DDD

## Referências

- [Domain Driven Design](https://martinfowler.com/bliki/DomainDrivenDesign.html)
- [Test Driven Development](https://martinfowler.com/bliki/TestDrivenDevelopment.html)
- [Sequelize Documentation](https://sequelize.org/)
- [Jest Documentation](https://jestjs.io/)

## Autor

Implementação realizada como desafio de DDD e TDD em TypeScript.

## Licença

Este projeto está sob a licença fornecida no repositório original.
