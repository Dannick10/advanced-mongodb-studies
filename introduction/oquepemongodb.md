# MongoDB — O Não Relacional Mais Popular

O MongoDB é atualmente um dos bancos de dados não relacionais mais utilizados no mundo. Ele é classificado como um banco orientado a documentos, armazenando dados no formato de objetos JSON (na prática, BSON).

- documentação do BSON: https://bsonspec.org/

## Características:

### Os dados são armazenados em formato de objeto JSON

```json
{
  "nome": "Daniel",
  "idade": 25,
  "cidade": "Aracaju"
}
```

### Os comandos são métodos e não queries

```json
db.usuarios.find({})
```

### Podemos criar relações entre entidades (collections)

Mesmo sem o conceito rígido de JOINs como no SQL, conseguimos relacionar documentos utilizando referências (ObjectId) ou incorporando documentos dentro de outros.

### Altamente compatível com várias linguagens de programação

Altamente compatível com várias linguagens de programação

## Conceitos Importantes

### Queries

São comandos usados para consultar, inserir, atualizar ou excluir dados em um banco relacional (SQL).
Exemplo em MySQL:

```json
SELECT * FROM usuarios WHERE idade > 18;
```

### Métodos

No MongoDB (e outros bancos não relacionais), usamos métodos para realizar essas operações.
Exemplo em MongoDB:

```json
db.usuarios.find({ idade: { $gt: 18 } })
```

- $gt significa “greater than” (maior que).

## Entidade

Uma entidade representa qualquer objeto ou conceito do mundo real sobre o qual desejamos armazenar informações no banco de dados.

### Exemplos de entidades:

- usuario

- produto

- pedido

- cliente

## resumo

No MongoDB, uma entidade é representada por um documento JSON dentro de uma collection.

| Banco de Dados           | Estrutura Fixa | Relacionamentos                     | Linguagem              | Comandos |
| :----------------------- | :------------- | :---------------------------------- | :--------------------- | :------- |
| Relacional               | Sim            | Nativos (JOIN)                      | SQL                    | Queries  |
| Não Relacional (MongoDB) | Não            | Possíveis (referência/incorporação) | JSON-like (JavaScript) | Métodos  |
