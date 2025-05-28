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
