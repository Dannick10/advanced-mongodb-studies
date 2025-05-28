# comandos

### Mostrar banco

```
show dbs
```

### criar banco

```
use <nome>
```

- O banco é inicializado e é apenas criado quando houver dado nele.

### inserir collection

```
db.<collection>.insertOne(<dados>)
```

- não precisamos explicitamente criar uma collection, basta inserir um dado em alguma.
- A collection será criada automaticamente, e também o banco de dados persistirá no sistema
- O comando db sempre faz referência ao banco de dados selecionado no momento.

### Encontrar dados

```
db.<nome_da_collection>.find()
```

Buscar apenas um documento (o primeiro que encontrar)

```
db.<nome_da_collection>.findOne({ <campo>: <valor> })
```

Buscar e retornar apenas determinados campos (projeção)

```
db.<nome_da_collection>.find(
 { <filtro> },
 { <campo>: 1, <campo>: 1, _id: 0 }
)
```

Ordenar os resultados

```
// ordem crescente
db.<nome_da_collection>.find().sort({ <campo>: 1 })

// ordem decrescente
db.<nome_da_collection>.find().sort({ <campo>: -1 })
```

Limitar a quantidade de resultados

```
db.<nome_da_collection>.find().limit(<quantidade>)
```

Pular documentos

```
db.<nome_da_collection>.find().skip(<quantidade>)

```

### pretty
Ele organiza o retorno no terminal em formato de JSON bem indentado e legível — ideal para leitura rápida enquanto desenvolve.

```
db.usuarios.find({ nome: "Daniel" }).pretty()
```

### Criando uma Collection Explícita no MongoDB
Normalmente, no MongoDB as collections são criadas implicitamente ou seja, basta inserir um dado e a collection nasce.
Mas se você quiser criar explicitamente, usa-se:

```
db.createCollection("<nome_da_collection>", { <opções> })
```

exemplo: 
```
db.createCollection("logs", {
  capped: true,
  size: 1048576,
  max: 1000
})
```

Opções disponíveis para createCollection

| Opção                | Tipo    | Descrição                                                                            |
| :------------------- | :------ | :----------------------------------------------------------------------------------- |
| **capped**           | boolean | Define se a collection será **capped** (tamanho fixo, FIFO). Ex: `true`              |
| **size**             | number  | Tamanho máximo (em bytes) da collection se for capped.                               |
| **max**              | number  | Número máximo de documentos permitidos na collection (para capped).                  |
| **validator**        | object  | Define regras de validação dos dados inseridos.                                      |
| **validationLevel**  | string  | Define o nível da validação: `"off"` (desliga), `"moderate"` ou `"strict"` (padrão). |
| **validationAction** | string  | Ação ao violar a validação: `"error"` (padrão) ou `"warn"`.                          |
| **autoIndexId**      | boolean | (Obsoleto) Definia se deveria criar automaticamente o índice `_id`.                  |
| **storageEngine**    | object  | Permite especificar configurações para o mecanismo de armazenamento.                 |
| **viewOn**           | string  | (Para views) Indica a collection base para a view.                                   |
| **pipeline**         | array   | (Para views) Define as operações de agregação para a view.                           |
| **collation**        | object  | Define regras de ordenação, comparação e case sensitivity para strings.              |
